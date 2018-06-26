學習將先前做出的網頁佈屬至雲端平台—Heroku。

## **步驟一** 

下載 Heroku Command Line Interface \(CLI\)，安裝完後，使用 cmd.exe 輸入以下指令。

```
heroku --version
```

如安裝正確，會跳出安裝的 Heroku CLI 版本

![](https://blobscdn.gitbook.com/v0/b/gitbook-28427.appspot.com/o/assets%2F-LCwJ8pTIK-At32L1Yte%2F-LCwymsTkLzJzF89x_iZ%2F-LCwyuTg8qVbYT8wMcfn%2Fimage.png?alt=media&token=9fc0686e-f801-428b-b3fc-08558f42f72a)

接著再用 cmd.exe 輸入你的[Heroku](https://dashboard.heroku.com/)帳號 和 密碼。

```
heroku logi
```

![](https://blobscdn.gitbook.com/v0/b/gitbook-28427.appspot.com/o/assets%2F-LCwJ8pTIK-At32L1Yte%2F-LCwymsTkLzJzF89x_iZ%2F-LCwz-eIDMBo5hg7ijzC%2Fimage.png?alt=media&token=733fc023-22ea-4fb6-b6a8-f279defcfec3)

## **步驟二** 

新增3個檔案 :

1. requirements.txt

   這個檔案是要告訴[Heroku](https://dashboard.heroku.com/)，需要用到那些套件。

   我們使用了 : Jinja2、gunicorn、Flask。

   \*可以使用 cmd 輸入以下指令查看目前電腦所安裝的套件

```
pip freeze
```

1. Procfile

   這個檔案是要告訴[Heroku](https://dashboard.heroku.com/)要如何啟動我的網頁，在[Heroku](https://dashboard.heroku.com/)裡，官方使用[Gunicorn](http://gunicorn.org/)來啟動網頁，可參考[python-gunicorn Heroku](https://devcenter.heroku.com/articles/python-gunicorn)​

   所以在**requirements.txt**裡，請記得要輸入[gunicorn](http://gunicorn.org/)​

   \*Procfile 檔案，基本使用方法如下

```
web gunicorn app_run:app
```

app\_run 就是自己的的 app\_run.py，請依照自己設定的名稱自行修改

1. runtime.txt

   runtime.txt 檔案裡，只需要簡單的填入你想要指定的 python 版本

```
python-3.4.3
```

可參考[Heroku python-runtimes](https://devcenter.heroku.com/articles/python-runtimes)​

## **步驟三** 

先創造 Heroku application \(因 Flask 進入 Heroku 會是一個應用程式\)

方法一 :

輸入以下指令

```
heroku creat
```

![](https://blobscdn.gitbook.com/v0/b/gitbook-28427.appspot.com/o/assets%2F-LCwJ8pTIK-At32L1Yte%2F-LCwymsTkLzJzF89x_iZ%2F-LCwyr7vH2mx2Xfv_dF3%2Fimage.png?alt=media&token=65a3e915-168f-4d18-b62e-e40ab4214746)

方法二 :

到網頁上新增一個[Heroku applicatio](https://dashboard.heroku.com/new?org=personal-apps)​

![](https://blobscdn.gitbook.com/v0/b/gitbook-28427.appspot.com/o/assets%2F-LCwJ8pTIK-At32L1Yte%2F-LCwyRTIMyMt5VIMGyG4%2F-LCwyk-pT3wYy8DnZmgp%2Fimage.png?alt=media&token=d5a1bca5-d90a-40dc-bca3-c2710cb5c52d)

* **初始化**

用 cmd.exe 切換到目錄底下，初始化

```
git init
```

* **佈署**

指定 remote

```
heroku git:remote -a kuanru
```

kuanru 這是我自己的，請輸入自己的。

這些指令你可以在 web 裡的 deploy 看到。

* **畫面**

如果佈署成功，網址會是[https://kuanru.herokuapp.com/](https://kuanru.herokuapp.com/)。

