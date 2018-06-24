# 期末報告
## 作品名稱:鋼球循環系統
### 期末報告介紹


### 利用期中以前的抬球機構加入期中後W10至W14的進度完成期末報告，我們把期中前的抬球機構加入W12的齒輪模組，來提升抬球機構扭力方面的問題，並且將初始抬球機構重新設計，並且達到能夠完美配合後，加入W10所設計的三段式抬球機構來進行鋼球循環，並且搭配W14所設計的鋼球搬運車來達成將球載運至其他循環系統的設計與模擬。
<a href="https://imgur.com/5ovC0uu"><img src="https://i.imgur.com/5ovC0uu.png" title="source: imgur.com" /></a>
### YouTube 模擬影片 : https://www.youtube.com/watch?v=xKhb5qzdpbc&feature=youtu.be
### YouTube 模擬影片(0611更改) : https://www.youtube.com/watch?v=70redLIBo4g&t=28s ，此次更改修正了一些干涉，並改善系統流暢度，增加循環的成功率。
### YouTube 解說模擬影片 : https://www.youtube.com/watch?v=oO600U12IWU&t=7s
### 檔案連結 : [cd_w14_ag6.ttt](https://github.com/s40523122/cd2018_hw/blob/master/lifter/cd_w14_ag6.ttt?raw=true)、[cd_w14_ag6.slvs](https://github.com/s40523122/cd2018_hw/tree/master/lifter/6-barLifter)、[其他 CAD 等文件](https://github.com/s40523122/cd2018_hw/tree/master/lifter)
## 各別機構介紹:
### (一)擋球:
### 由於前幾代的機構發生了無法順利接到球的問題，於是這邊我們設計了一個擋球機構來讓球能順利的進入抬球機構，而不會發生滑動或是碰撞造成的鋼球滑落現象

### 由下方圖片可以清楚看到，我們利用類似彈簧的原理，利用三段式抬球機構的勺子向下的力量來碰撞擠壓到擋球機構下方底板，讓球能從軌道順利滑入機構勺子
<a href="https://imgur.com/SnijbUy"><img src="https://i.imgur.com/SnijbUy.png" title="source: imgur.com" /></a>
<a href="https://imgur.com/qnqd6wi"><img src="https://i.imgur.com/qnqd6wi.png" title="source: imgur.com" /></a>
<a href="https://imgur.com/ySJxe99"><img src="https://i.imgur.com/ySJxe99.png" title="source: imgur.com" /></a>
### (二)三段式抬球機構:
### 機構部份我們重新設計抬球、軌道、連接處部分，因為一開始的設計並沒有考慮太多因素，導致在模擬時發生很多預期外的結果，這部份我們花很多時間來調整接球與軌道的配合，最後我們把原本會發生碰撞干涉的部分都一一解決，並且配合v-rep的模擬運算來完成最終版的三段式抬球機構
<a href="https://imgur.com/X7OBAqD"><img src="https://i.imgur.com/X7OBAqD.png" title="source: imgur.com" /></a>
### (三)運送車:
### 運送車這部分牽扯到比較多程式方面的問題，因為我們在Lua這方面技術比較不純熟，所以我們搬運車並沒加入感測器配置設計，而是直接利用軌道限制軌跡並且搭配遙控方式來實現搬運車運作過程初步模擬
<a href="https://imgur.com/VPCsDo3"><img src="https://i.imgur.com/VPCsDo3.png" title="source: imgur.com" /></a>
<a href="https://imgur.com/vGDDiT2"><img src="https://i.imgur.com/vGDDiT2.png" title="source: imgur.com" /></a>
### (四)齒輪送球機構:
### 我們齒輪部分並不是利用碰撞模擬來運行，因為我們有測試過利用碰撞方式來模擬齒輪，但因V-rep模擬上的限制，導致齒輪不如預期進行運作，於是我們採取計算齒輪比來獲得所有齒輪的轉速，並製作出相當真實的齒輪嚙合轉動假象來完成我們齒輪方面的運作
<a href="https://imgur.com/7gL7R9z"><img src="https://i.imgur.com/7gL7R9z.png" title="source: imgur.com" /></a>
### YouTube 模擬影片 : https://youtu.be/3QIIzQWRW-c
### 齒輪細節圖:
<a href="https://imgur.com/4myaMXn"><img src="https://i.imgur.com/4myaMXn.png" title="source: imgur.com" /></a>
<a href="https://imgur.com/rCek7DB"><img src="https://i.imgur.com/rCek7DB.png" title="source: imgur.com" /></a>
### [齒輪檔案連結](https://github.com/s40523122/cd2018_hw/tree/master/lifter/GearLifter)


















