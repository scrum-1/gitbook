```
<!-- 導入 Brython 標準程式庫 -->
<script src="../data/Brython-3.3.1/brython.js"></script>
<script src="../data/Brython-3.3.1/brython_stdlib.js"></script><p></p>
<!-- 啟動 Brython -->
 
<script>
window.onload=function(){
// 設定 data/py 為共用程式路徑
brython({debug:1, pythonpath:['./../data/py']});
}
</script>
 
<!-- Cango 程式庫 -->
 
<script type="text/javascript" src="../data/cango/Cango-8v03.js"></script>
 
<script type="text/javascript" src="../data/cango/Cango2D-7v01-min.js"></script>
 
<script type="text/javascript" src="../data/cango/CangoAxes-1v33.js"></script>
 
<script type="text/javascript" src="../data/cango/CangoAnimation-4v01.js"></script>
 
<script type="text/javascript" src="../data/cango/gearUtils-05.js"></script>
 
<canvas id="cango_gear" width="800" height="750"></canvas>
 
<!-- 以下製作 button-->
 
<div id="cango_gear_div" width="800" height="20"></div>
 
<p><input id="cn" value="19"><br>
<button id="button_a">Set Number of Gears</button></p>
<script type="text/python">
# 將 導入的 document 設為 doc 主要原因在於與舊程式碼相容
from browser import document as doc
# 由於 Python3 與 Javascript 程式碼已經不再混用, 因此來自 Javascript 的變數, 必須居中透過 window 物件轉換
from browser import window
import math
 
# 主要用來取得畫布大小
canvas = doc["cango_gear"]
# 此程式採用 Cango Javascript 程式庫繪圖, 因此無需 ctx
#ctx = canvas.getContext("2d")
cango = window.Cango.new
# 針對變數的轉換, shapeDefs 在 Cango 中資料型別為變數, 可以透過 window 轉換
shapedefs = window.shapeDefs
# 目前 Cango 結合 Animation 在 Brython 尚無法運作, 此刻只能繪製靜態圖形
# in CangoAnimation.js
#interpolate1 = window.interpolate
# Cobi 與 createGearTooth 都是 Cango Javascript 程式庫中的物件
cobj = window.Cobj.new
creategeartooth = window.createGearTooth.new
# 經由 Cango 轉換成 Brython 的 cango, 指定將圖畫在 id="cango_gear" 的 canvas 上
cgo = cango("cango_gear")
 
######################################
# 畫正齒輪輪廓
#####################################
 
# 以 button 驅動的事件函式
def draw(e):
    cgo.clearCanvas()
    cx = (canvas.width)/2
    cy = (canvas.height)/2
    if doc["cn"].value.isdigit():
        cn1 = int(doc["cn"].value)
    else:
        cn1= 19
# pa 為壓力角
    pa = 25
# m 為模數, 根據畫布的寬度, 計算適合的模數大小
# Module = mm of pitch diameter per tooth
    m = 0.5*canvas.width/cn1
# pr 為節圓半徑
    pr = cn1*m/2 # gear Pitch radius
# generate gear
    data = creategeartooth(m, cn1, pa)
# Brython 程式中的 print 會將資料印在 Browser 的 console 區
#print(data)
    gearTooth = cobj(data, "SHAPE", {
            "fillColor":"#ddd0dd",
                    "border": True,
           "strokeColor": "#606060" })
    gearTooth.rotate(180/cn1) # rotate gear 1/2 tooth to mesh
# 單齒的齒形資料經過旋轉後, 將資料複製到 gear 物件中
    gear = gearTooth.dup()
# gear 為單一齒的輪廓資料
#cgo.render(gearTooth)
 
# 利用單齒輪廓旋轉, 產生整個正齒輪外形
    for i in range(1, cn1):
    # 將 gearTooth 中的資料複製到 newTooth
        newTooth = gearTooth.dup()
    # 配合迴圈, newTooth 的齒形資料進行旋轉, 然後利用 appendPath 方法, 將資料併入 gear
        newTooth.rotate(360*i/cn1)
    # appendPath 為 Cango 程式庫中的方法, 第二個變數為 True, 表示要刪除最前頭的 Move to SVG Path 標註符號
        gear.appendPath(newTooth, True) # trim move command = True
 
# 建立軸孔
# add axle hole, hr 為 hole radius
    hr = 0.6*pr # diameter of gear shaft
    shaft = cobj(shapedefs.circle(hr), "PATH")
    shaft.revWinding()
    gear.appendPath(shaft) # retain the 'moveTo' command for shaft sub path
 
# render 繪出靜態正齒輪輪廓
    gear.translate(cx, cy)
    cgo.render(gear)
    r = 0.6*(canvas.height/2)
draw(True)
doc['button_a'].bind('click',draw)
</script>
```



