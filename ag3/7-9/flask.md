學習利用網站創建軟件—Flask在近端做出一個屬於自己的網頁。

可以做到的功能有：

* 登入登出\(只有一組帳號密碼\)

* 輸入title以及text

## step 0. creating the folders 

```
/flaskr
    /flaskr
        /static
        /templates
```

創建一個可以讓我們放置文件的文件夾

這個除了可以使用PYTHON，也能用CSS跟JAVA

這裡我們使用的是PYTHON

## step 1. database schema

```
drop table if exists entries;
create table entries (
  id integer primary key autoincrement,
  title text not null,
  'text' text not null
);
```

建立數據庫模式，將以上內容放進flaskr裡面的schema.sql.

裡面包含entries，表裡面的每一行都有一個id/title/text

id為會自動遞增的整數，也是主鍵

title跟text為一串不為空的值

## step 2. application setup code

在有了數據庫模式之後，我們必須建立應用模組：flaskr.py

並放置在flaskr目錄裡

首先在flaskr.py輸入

```
# all the imports
import os
import sqlite3
from flask import Flask, request, session, g, redirect, url_for, abort, \
  render\_template, flash
app = Flask(__name__) # create the application instance :)
app.config.from_object(__name__) # load config from this file , flaskr.py
​
# Load default config and override config from an environment variable
app.config.update(dict(
    DATABASE=os.path.join(app.root_path, 'flaskr.db'),
    SECRET_KEY='development key',
    USERNAME='admin',
    PASSWORD='default'
))
```

上面的有輸入帳號密碼的地方，就是們前面提到的只有一組帳號密碼可被使用

介紹一下database path:

因為操作程式的時候，可能會同一個過程中進行多個應用，但在WEB應用裡面沒有這個概念

所以我們可以用"app.root\_path"來取得應用路徑，配合"os.path"模式，讓我們可以輕鬆找到文件

在此我們' 數據庫放在目錄下

```
app.config.from_envvar('FLASKR_SETTINGS', silent=True)
```

最後要加上一個模式使我們可以連結到數據庫

```
def connect_db():
    """Connects to the specific database."""
    rv = sqlite3.connect(app.config['DATABASE'])
    rv.row_factory = sqlite3.Row
    return rv
```

## step 3. installing flaskr as a package

安裝一個flaskr組件

首先需要先給我們的模式一個結構

```
/flaskr
    /flaskr
        __init__.py
        /static
        /templates
        flaskr.py
        schema.sql
    setup.py
    MANIFEST.in
```

再來如下

```
from setuptools import setup
​
setup(
    name='flaskr',
    packages=['flaskr'],
    include_package_data=True,
    install_requires=[
        'flask',
    ],
)
graft flaskr/templates
graft flaskr/static
include flaskr/schema.sql
from .flaskr import app
pip install --editable .
export FLASK_APP=flaskr
export FLASK_DEBUG=true
flask run
```

## step 4.database connections

建立一個數據庫的連接

```
def get_db():
    """Opens a new database connection if there is none yet for the
    current application context.
    """
    if not hasattr(g, 'sqlite_db'):
        g.sqlite_db = connect_db()
    return g.sqlite_db
    @app.teardown_appcontext
def close_db(error):
    """Closes the database again at the end of the request."""
    if hasattr(g, 'sqlite_db'):
        g.sqlite_db.close()
```

## step 5.creating the database

flasKr是一個由數據庫系統驅動的應用程式

所以我們需要一個模式來告訴它如何儲存資訊

```
sqlite3 /tmp/flaskr.db < schema.sql
def init_db():
    db = get_db()
    with app.open_resource('schema.sql', mode='r') as f:
        db.cursor().executescript(f.read())
    db.commit()
​
@app.cli.command('initdb')
def initdb_command():
    """Initializes the database."""
    init_db()
    print('Initialized the database.')
flask initdb
Initialized the database.
```

## step 6.the view functions

建立完數據庫並確定可以使用後，需要一些視圖功能

需要以下四個:

* **show entries 顯示條目**

顯示所有數據庫裡面所儲存的資訊

```
@app.route('/')
def show_entries():
    db = get_db()
    cur = db.execute('select title, text from entries order by id desc')
    entries = cur.fetchall()
    return render_template('show_entries.html', entries=entries)
```

**add new entry 新增條目**

讓登入的使用者可以新增條目

```
@app.route('/add', methods=['POST'])
def add_entry():
    if not session.get('logged_in'):
        abort(401)
    db = get_db()
    db.execute('insert into entries (title, text) values (?, ?)',
                 [request.form['title'], request.form['text']])
    db.commit()
    flash('New entry was successfully posted')
    return redirect(url_for('show_entries'))
```

**login & logout 登入以及登出**

讓使用者登入以及登出，帳號密碼需使用創建者設定的

只有一組帳號密碼

```
@app.route('/login', methods=['GET', 'POST'])
def login():
    error = None
    if request.method == 'POST':
        if request.form['username'] != app.config['USERNAME']:
            error = 'Invalid username'
        elif request.form['password'] != app.config['PASSWORD']:
            error = 'Invalid password'
        else:
            session['logged_in'] = True
            flash('You were logged in')
            return redirect(url_for('show_entries'))
    return render_template('login.html', error=error)
@app.route('/logout')
def logout():
    session.pop('logged_in', None)
    flash('You were logged out')
    return redirect(url_for('show_entries'))
```

## step 7.the templates

如果我們使成始開始啟動，可能會讓flask找不到模板

這裡的模板是使用jinja2語法並且默認一個自動啟用功能

以下是需要使用的模板

* **layout.html**

```
<!doctype html>
<title>Flaskr</title>
<link rel=stylesheet type=text/css href="{{ url_for('static', filename='style.css') }}">
<div class=page>
  <h1>Flaskr</h1>
  <div class=metanav>
  {% if not session.logged_in %}
    <a href="{{ url_for('login') }}">log in</a>
  {% else %}
    <a href="{{ url_for('logout') }}">log out</a>
  {% endif %}
  </div>
  {% for message in get_flashed_messages() %}
    <div class=flash>{{ message }}</div>
  {% endfor %}
  {% block body %}{% endblock %}
</div>
```

**show\_entries.html**

```
{% extends "layout.html" %}
{% block body %}
  {% if session.logged_in %}
    <form action="{{ url_for('add_entry') }}" method=post class=add-entry>
      <dl>
        <dt>Title:
        <dd><input type=text size=30 name=title>
        <dt>Text:
        <dd><textarea name=text rows=5 cols=40></textarea>
        <dd><input type=submit value=Share>
      </dl>
    </form>
  {% endif %}
  <ul class=entries>
  {% for entry in entries %}
    <li><h2>{{ entry.title }}</h2>{{ entry.text|safe }}
  {% else %}
    <li><em>Unbelievable.  No entries here so far</em>
  {% endfor %}
  </ul>
{% endblock %}
login.html
```

**login.html**

```
{% extends "layout.html" %}
{% block body %}
  <h2>Login</h2>
  {% if error %}<p class=error><strong>Error:</strong> {{ error }}{% endif %}
  <form action="{{ url_for('login') }}" method=post>
    <dl>
      <dt>Username:
      <dd><input type=text name=username>
      <dt>Password:
      <dd><input type=password name=password>
      <dd><input type=submit value=Login>
    </dl>
  </form>
{% endblock %}
```

## The Last

做完以上步驟就可以在近端完成我們的網頁，再來配合下一篇章所講的內容將近端完成的網頁推回遠端，

即可完成。

