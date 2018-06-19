> # Week5 2018/03/27

### _課程內容_

## 1.V-rep 簡介

V-rep 全稱為 Virtual Robot Experimentation Platform \(虛擬機器人實驗平台\)

### 特性

跨操作系統平台 \(以 Qt/C++ 編寫, 可在 Windows, Linux 與 MacOSX 中執行\)

[http://www.coppeliarobotics.com/helpFiles/en/writingCode.htm](http://www.coppeliarobotics.com/helpFiles/en/writingCode.htm)

提供[多種物件模擬](http://www.coppeliarobotics.com/helpFiles/en/objects.htm)功能

提供 400 個以上的 API 程式方法

支援 [ROS](http://www.ros.org/)

支援 [ODE](http://www.ode.org/) 與 [Bullet ](http://bulletphysics.org/wordpress/)開放源動態程式庫

支援正向與逆向運動學\([Forward](https://en.wikipedia.org/wiki/Forward_kinematics) and [Inverse Kinematics](https://en.wikipedia.org/wiki/Inverse_kinematics)\) 分析

提供[視覺感測器](http://www.coppeliarobotics.com/helpFiles/en/visionSensors.htm)功能

提供[路徑與運動規劃](http://www.coppeliarobotics.com/helpFiles/en/pathAndMotionPlanningModules.htm)功能

提供[碰撞檢測](http://www.coppeliarobotics.com/helpFiles/en/collisionDetection.htm)功能

提供[距離運算](http://www.coppeliarobotics.com/helpFiles/en/distanceCalculation.htm)功能

提供[距離感測](http://www.coppeliarobotics.com/helpFiles/en/proximitySensors.htm)功能

提供 [Qt 使用者界面](http://www.coppeliarobotics.com/helpFiles/en/customUIPlugin.htm)延伸

提供數據除存與[繪圖](http://www.coppeliarobotics.com/helpFiles/en/graphs.htm)功能

提供[影片錄製](http://www.coppeliarobotics.com/helpFiles/en/aviRecorder.htm)功能

提供[模型編修](http://www.coppeliarobotics.com/helpFiles/en/shapeEditModes.htm)功能

提供[模型瀏覽器](http://www.coppeliarobotics.com/helpFiles/en/userInterface.htm#ModelBrowser)功能

提供[模型銑切](http://www.coppeliarobotics.com/helpFiles/en/mills.htm)功能

## 2.V-rep Lua 指令

[查詢目前所在工作目錄](https://stackoverflow.com/questions/6032268/get-current-working-directory-in-lua):

```
current_dir=io.popen"cd":read'*l'
```

```
simAddStatusbarMessage("current directory"..current_dir)
```

### V-rep main client application

[http://www.coppeliarobotics.com/helpFiles/en/mainClientApplication.htm](http://www.coppeliarobotics.com/helpFiles/en/mainClientApplication.htm)

## V-rep API

[http://www.coppeliarobotics.com/helpFiles/en/apisOverview.htm](http://www.coppeliarobotics.com/helpFiles/en/apisOverview.htm)

## V-rep scripts

[http://www.coppeliarobotics.com/helpFiles/en/scripts.htm](http://www.coppeliarobotics.com/helpFiles/en/scripts.htm)

[http://www.coppeliarobotics.com/helpFiles/en/simulationScripts.htm](http://www.coppeliarobotics.com/helpFiles/en/simulationScripts.htm)

[http://www.coppeliarobotics.com/helpFiles/en/customizationScripts.htm](http://www.coppeliarobotics.com/helpFiles/en/customizationScripts.htm)

## V-rep regular API

[http://www.coppeliarobotics.com/helpFiles/en/apiFunctionListCategory.htm](http://www.coppeliarobotics.com/helpFiles/en/apiFunctionListCategory.htm)

[http://www.coppeliarobotics.com/helpFiles/en/apiFunctionListAlphabetical.htm](http://www.coppeliarobotics.com/helpFiles/en/apiFunctionListAlphabetical.htm)

參考資料:

[https://blog.robotiq.com/bid/65946/Robotic-Simulation-Software-V-REP](https://blog.robotiq.com/bid/65946/Robotic-Simulation-Software-V-REP)

[第五週課程規劃議題](https://github.com/mdecourse/cd2018/issues/21)

## `課程練習:`

##### 在各組 gh-pages 網頁或雲端主機上列出第一堂課缺席名單

with open\("cd\_w7a.txt", "r", encoding="big5"\) as fh:

```
\# 逐行讀出檔案資料, 並放入數列中

lines = fh.readlines\(\)

raw\_data = lines\[1:\]

\#print\(raw\_data\)

\# 設法用迴圈逐數列內容取出字串

\# k 為集合所有檔案中的學號字串, 先設為空字串

k = \[\]

for i in range\(len\(raw\_data\)\):

    \# 利用 strip\(\) 去除各行字串最末端的跳行符號

    raw\_line = raw\_data\[i\].strip\(\)

    \# 利用 split\(\) 將以 \t 區隔的字串資料分離後納入 groups 字串

    groups = raw\_line.split\("\t"\)

    \#print\(groups\)

    \# 逐一進入各行中的各字串去除空字串

    for j in range\(len\(groups\)\):

        if groups\[j\] != "":

            \# 除了空字串外, 其餘字串放入 k 數列中

            k.append\(groups\[j\]\)
```

\# 將 k 中只出現一次的字串印出, 即為缺席者名單

absent = \[x for x in k if k.count\(x\) == 1\]

print\(absent\)

這樣就可以列出未出席的名單了

