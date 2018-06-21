> # Week7 2018/04/10

## `何謂Flask:`

[Flask](http://flask.pocoo.org/)

是一個使用 Python 撰寫的輕量級 Web 應用程式框架，由於其輕量特性，也稱為 micro-framework（微框架）。Flask 核心十分簡單，主要是由[Werkzeug WSGI 工具箱](http://werkzeug.pocoo.org/)和[Jinja2 模板引擎](http://jinja.pocoo.org/docs/2.9/)所組成，Flask 和 Django 不同的地方在於 Flask 給予開發者非常大的彈性（當然你也可以說是需要思考更多事情），可以選用不同的用的 extension 來增加其功能。相比之下，Django 雖然完善但技術選擇相對不彈性，不論是 ORM、表單驗證或是模版引擎都有自己的作法。事實上沒有最好的框架，只有合適的使用情境，Django 相比之下適合需要快速的開發大型的應用程式，和 Ruby 中的[Ruby on Rails](http://rubyonrails.org/)相似，而 Flask 則是相對輕量彈性，更像是 Ruby 界的[Sinatra](http://www.sinatrarb.com/)。若讀者想先體驗看看 Flask 的程式狀況，以下是 Flask 簡易運行的程式，啟動測試伺服器後，可以在瀏覽器（[http://localhost:5000/）印出](http://localhost:5000/）印出)`Hello World!`。

# `Matlab簡介`

## 1 常用指令\(General Purpose Commands\)

#### 1.1 通用資訊查詢\(General information\)

demo 演示程式 help 線上幫助指令 helpbrowser 超文本文檔幫助資訊 helpdesk 超文本文檔幫助資訊 helpwin 打開線上幫助窗 info MATLAB 和MathWorks 公司的資訊 subscribe MATLAB 用戶註冊 ver MATLAB 和TOOLBOX 的版本資訊 version MATLAB 版本 whatsnew 顯示版本新特徵

#### 1.2 工作空間管理\(Managing the workspace\)

clear 從記憶體中清除變數和函數 exit 關閉MATLAB load 從磁片中調入資料變數 pack 合併工作記憶體中的碎塊 quit 退出MATLAB save 把記憶體變數存入磁片 who 列出工作記憶體中的變數名 whos 列出工作記憶體中的變數細節 workspace 工作記憶體流覽器

#### 1.3 管理指令和函數\(Managing commands and functions\)

edit 矩陣編輯器 edit 打開M 文件 inmem 查看記憶體中的P 碼檔 mex 創建MEX 文件 open 打開文件 pcode 生成P 碼檔 type 顯示檔內容 what 列出當前目錄上的M、MAT、MEX 文件 which 確定指定函數和檔的位置

#### 1.4 搜索路徑的管理\(Managing the seach patli\)

addpath 添加搜索路徑 rmpath 從搜索路徑中刪除目錄 path 控制MATLAB 的搜索路徑 pathtool 修改搜索路徑

#### 1.5 指令窗控制\(Controlling the command window\)

beep 產生beep 聲 echo 顯示命令檔指令的切換開關 diary 儲存MATLAB 指令窗操作內容 format 設置資料輸出格式 more 命令視窗分頁輸出的控制開關

#### 1.6 作業系統指令\(Operating system commands\)

cd 改變當前工作目錄 computer 電腦類型 copyfile 檔拷貝 delete 刪除檔 dir 列出的文件 dos 執行dos 指令並返還結果 getenv 給出環境值 ispc MATLAB 為PC\(Windows\)版本則為真 isunix MATLAB 為Unix 版本則為真 mkdir 創建目錄 pwd 改變當前工作目錄 unix 執行unix 指令並返還結果 vms 執行vms dcl 指令並返還結果 web 打開web 流覽器 ! 執行外部應用程式

#### 2.1 算術運算符\(Arithmetic operators\)

* 加 - 減 \* 矩陣乘 .\* 陣列乘 ^ 矩陣乘方 .^ 陣列乘方  反斜杠或左除 / 斜杠或右除 ./或. 陣列除 張量積 \[注\]本表第三欄括弧中的字元供線上救助時help 指令引述用

#### 2.2 關係運算符\(Relational operators\)

= = 等號

~= 不等號

&lt;小於

&gt;大於

&lt;= 小於或等於

&gt;= 大於或等於

#### 2.3 邏輯操作\(Logical operators\)

&邏輯與 \| 邏輯或 ~ 邏輯非 xor 異或 any 有非零元則為真 all 所有元素均非零則為真

#### 2.4 特殊算符\(Special characters\)

1. ： 冒號 \( \) 圓括號 \[ \] 方括號 { } 花括弧 @ 創建函數控制碼 . 小數點 . 構架域的關節點 .. 父目錄 ? 續行號 , 逗號 ; 分號 % 注釋號 ! 調用作業系統命令 = 賦值符號 ˊ 引號 ˊ 複數轉置號 .ˊ 轉置號 \[,\] 水準串接 \[;\] 垂直串接 \( \),{ },. 下標賦值 \( \),{ },. 下標標識 subsindex 下標標識

## 2下載[`Matlab`](https://www.mathworks.com/products/matlab.html)



