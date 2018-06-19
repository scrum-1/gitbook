> ## Week2 2018/03/06

Proxy改為

位置：140.130.17.42

連接埠：3128

Justify

Legacy

Python –m pip install Flask

\(Flack a模組名稱\)

程式jpg. 結果jpg.

### `課程練習:`

請練習利用 Ethercalc: [https://ethercalc.org](https://ethercalc.org) 擷取各組學員座位表與分組名單後，簡要說明資料處理方法與流程後，上傳至各組組長的 cd2018 倉儲中。

1.在 cd2018 倉儲的 gh-pages 分支中，設法以 Brython 程式庫，將上述分組或列出各學員座位的程式，改寫為 HTML 程式，可以處理同一倉儲或給定原始學員座位資料檔 URL，然後列出分組名單及座次表，好處是無需自建伺服器，只利用 html 及 javascript 處理資料。

2.利用 Flask 網際程式框架及自建伺服器，讓使用者上傳原始資料檔後，根據參數或格式設定，完成所需要的資料處理程序。

各組有空可以看一下[http://lab.kmol.info/blog/brython-programming-environment.html](http://lab.kmol.info/blog/brython-programming-environment.html)假如能將機電資整合專案中的設計或分析流程寫在各組的cd2018倉儲中的gh-page分支，將可用於協同產品設計方案的展示及篩選，而且可以直接在手機或平板的瀏覽器中使用。

第10組40523105練習利用python將座位表分組

`with open("01.txt") as fh:  
 lines = fh.readlines()  
 #print(len(lines))  
 print(lines)`

`with open("01.txt") as fh:  
 #逐行讀出檔案資料,並放入數列中  
 lines = fh.readlines()  
 #設法用迴圈逐數列內容取出字串  
 #組序變數g起始值設為0  
 g = 0  
 for i in range(len(lines)):  
 #利用strip()去除各行字串最末端的跳行符號  
 #print(lines[i].strip())  
 line = lines[i].strip()  
 #利用split()將以\t區隔的字串資料分離後納入groups字串  
 groups = line.split("\t")  
 #print(groups)  
 for i in range(len(groups)):  
 #每組有三名組員  
 if i%3 == 0:  
 #每三位組員組序增量1  
 g += 1  
 print()  
 print("第" + str(g) + "組:")  
 print(groups[i])  
 else:  
 print(groups[i])`

`y:/python36/pythonw -u "01.py"`

第1組:  
 40523115  
 40523108  
 40523116

第2組:  
 40523144  
 40523111  
 40523141

第3組:  
 40523104  
 40523102  
 40523123

第4組:  
 40523137  
 40523117  
 40523135

第5組:  
 40523147  
 40523146  
 40523145

第6組:  
 40523122  
 40523136  
 40523132

第7組:  
 40523127  
 40523126  
 40523125

第8組:  
 40523124  
 40523118  
 40523131

第9組:  
 40523121  
 40523120  
 40523119

第10組:  
 40523105  
 40523106  
 40523107

第11組:  
 40523143  
 40523128  
 40523129

第12組:  
 40523130  
 40523139  
 40523133

第13組:  
 40523142  
 40523148  
 40523140

第14組:  
 40523113  
 40523138  
 40523134

