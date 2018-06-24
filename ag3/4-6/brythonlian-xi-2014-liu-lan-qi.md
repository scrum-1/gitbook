※本篇在學習[Brython](https://www.brython.info/static_doc/en/intro.html)的大致使用後，進行實際執行。

這次將把前一篇文章的分組內容利用Brython作呈現，在這一一把步驟試著列出。 在此之前，說明若想要利用Brython，執行的方法： 

1.載入腳本[Brython.js](https://github.com/brython-dev/brython)。 

2.寫入`brython()`。 

3.寫入`<script type=”text/python”>`。

讓我們開始實際操作：

## 步驟一 

首先在加入套件及有關Brython的部分前，這是我們Python分組的程式\(第二點開始簡寫成\#content\)：

```
with open("2a raw.txt") as fh:
    rea = fh.readlines()
    #print (rea)
​
no_list = lambda list: int((sum([(len(list[i])) for i in range(len(list))]))/3)
#簡寫一個for迴圈命名為no_list,目的為求出迴圈執行次數(14次)
​
t = list()#命名空清單t
for k in range(len(rea)):
    a = rea[k]
    b = a.split()#分割每一行第k位
    #print(b)
    for i in range(0,len(b),3):
        c = b[i:i+3]#每三字串為一次進行迴圈
        t.append(c)#加入清單t
        
for g in range(no_list(t)):#range = 14
    print("第" + str(g+1) + "組:" + str(t[g]))
```

列出後，開始從[Bython官方網站](https://www.brython.info/static_doc/en/intro.html)中，一一找尋能達成我們目的的步驟，首先來到[Brython下載倉儲](https://github.com/brython-dev/brython)，第一步必須將Brython.js檔案載入程式中進行使用，利用內容中寫道的Zero install !部分，我們在上述程式碼的最上方寫入下列程式碼：

```
<script type="text/javascript"
    src="https://cdn.rawgit.com/brython-dev/brython/3.4.0/www/src/brython.js">
</script>
```

完成第一步。

## 步驟二 

為了在編輯中寫入函數`brython()`，需要建立`<body>`，程式碼寫法為：

```
<body onload="brython()">
    #content
</body>
```

### 步驟二-\(2\) 

接著，還需要利用`<div>`[區塊標籤](http://www.wibibi.com/info.php?tid=112)的功能，讓我們寫的Python程式內容包起來：

```
<body onload="brython()">
    <div id="test">
    #content
    </div>
</body>
```

### 步驟二-\(3\) 

而文章一開始說明想利用Brython的第三點，必須在`<script type=”text/python”>`中寫入Python代碼或將其連接，所以我們再加入一層`<script>`：

```
<body onload="brython()">
    <div id="test">
        <script type="text/python">
        #content
        </script>
    </div>
</body>
```

完成第二步，大致上的Brython載入使用都已經妥當，並繼續進行剩下步驟。

## 步驟三 

接著我們要賦予它兩個按鈕，分別是執行程式及清除輸出內容。想要在網頁中生成按鈕，參照[Brython\_Documentatoin\_Events](https://www.brython.info/static_doc/en/events.html)，內容介紹使用按鈕的方法：

```
@btn.bind("click")
def show(ev):
    print('ok')
```

在給予一個按鈕功能後，需寫入`<button id=”test”>test</button>`將它生成。

### 步驟三-\(2\) 

成功做出按鈕，試著放入我們要執行的程式中，直接用其將\#content給上下包住\(按鈕取名為but及but2\)：

```
<body onload="brython()">
    <div id="one">
        <script type="text/python">{% raw %}
            from browser import document, html
​
            @document["but1"].bind("click")
            def echo(ev):
                #content
            @document["but2"].bind("click")
            def delete(ev):
                for row in document['one']:
                    row.remove()
{% endraw %}</script>
    </div>
<button id="but">執行</button><button id="but2">清除</button>
</body>
```

※按鈕二為清除用途，以下將它分割出來提供讀者觀察：

```
@document["but2"].bind("click")
    def delete(ev):
        for row in document['one']:
            row.remove()
```

第三步按鈕的設置即完成。

## 步驟四 

實際看向近端瀏覽器，我們發現按下按鈕後還是無法執行，這時的問題參考[Brython documentation](https://www.brython.info/static_doc/en/cookbook/read_file.html)文章，內容說明讀取檔案內容時會因為讀取時間而無法正常輸出，其解為利用函數`<open()>`將時間設置忽略\(給予一個假\(fake\)的時間\)，使用方法為：

```
fake_qs = '?foo=%s' %time.time()
```

再來給予檔案名稱後方加上假的時間代碼：

```
with open('./../../../../data/2a.txt'+fake_qs) as fh:
```

接著需要利用import來輸入time以及document以利執行，寫法為：

```
import time
from browser import document
```

## 步驟五

最後整理好經過加工的分組程式碼，就可以進行執行的測試，以下為最後的程式：

```
<script type="text/javascript" src="https://cdn.rawgit.com/brython-dev/brython/3.4.0/www/src/brython.js"></script>
​
<body onload="brython()">
    <div id="one">
        <script type="text/python">{% raw %}
            from browser import document, html
            import time
​
            @document["mybutton"].bind("click")
            def echo(ev):
                fake_qs = '?foo=%s' %time.time()
                with open("./../../../../2a.txt"+fake_qs) as fh:
                    rea = fh.readlines()
                    #print (rea)
​
                no_list = lambda list: int((sum([(len(list[i])) for i in range(len(list))]))/3)
                #簡寫一個for迴圈命名為no_list,目的為求出迴圈執行次數(14次)
​
                t = list()#命名空清單t
                for k in range(len(rea)):
                    a = rea[k]
                    b = a.split()#分割每一行第k位
                    #print(b)
                    for i in range(0,len(b),3):
                        c = b[i:i+3]#每三字串為一次進行迴圈
                        t.append(c)#加入清單t
                        
                for g in range(no_list(t)):#range = 14
                    document["one"] <= ("第" + str(g+1) + "組:" + str(t[g])) + html.BR()
            @document["mybutton2"].bind("click")
            def delete(ev):
                for row in document['one']:
                    row.remove()
{% endraw %}</script>
    </div>
<button id="mybutton">執行</button><button id="mybutton2">清除</button>
</body>
```





是不是都學會了呢？

也可以觀看網誌：[https://s40523123.github.io/cd2018/2018/03/13/group3-W2/](https://s40523123.github.io/cd2018/2018/03/13/group3-W2/)​

實際執行網址：[https://s40523123.github.io/cd2018/2018/03/24/group3-W5/](https://s40523123.github.io/cd2018/2018/03/24/group3-W5/)​

