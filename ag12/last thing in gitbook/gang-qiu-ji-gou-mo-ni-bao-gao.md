# 一、前言:

### 這次我們沿用case3的方案並將內部做了一些調整，像是將上次軌道的斜度變小以防止速度太快的球會從軌道上脫離，以及離開軌道後到主動軸的這段直線也把斜度增加了，詳細的內容在下面會說到。

![](/assets/1.png)

# 二、遇到的問題:

![](/assets/軌道1.png)

### 因為上次的軌道略為簡單，所以我們重做了一個不過因為太久沒畫圖了忘記要掃出的草圖不能和實體重疊，導致無法掃出，還因此思考了一陣子。

![](/assets/軌道二.png)

### 做完軌道後放到V-rep模擬後發現，因為原本的軌道不是那麼順利能讓球持續碰撞，所以改讓球緩慢進入送球軌道上，下圖送球軌道斜度不需要太多就可讓球持續滾動，而新做的軌道會讓球進入軌道的速度太快導致直接撞上送球軌道而停住，所以將送球軌道的斜度再調大一些。

![](/assets/運球軌道.png)

# 三、頂球機構的位移、速度與加速度分析

## 手算部分

#### 位移為:151.52941

#### ![](/assets/2.jpg)

#### 因為我們的機構是利用螺旋讓球往上移動

#### 所以在上升的過程中速度保持定值

#### 又因為速度=位移/時間

#### 速度=151.52941/24.8=6.11005\(m/s\)

## 模擬部分

![](/assets/3.png)

#### V-rep主軸轉速設定-100 deg/s，所以轉一圈所花費的時間是3.6秒\(360/100=3.6\)

#### 從底部開始送球到最上方旋轉了大約7圈，因此所花的時間是3.6\*7=25.2，與模擬時間僅相差0.4秒

#### 以下為球上升到最高點所花費時間的影片

[https://www.youtube.com/watch?v=TQ4aQIOuKsg&feature=youtu.be](https://www.youtube.com/watch?v=TQ4aQIOuKsg&feature=youtu.be)

# 四、各零件材料與工程圖連結

#### [零件工程圖](https://cad.onshape.com/documents/4e4bf2fc0c83eb85ac7dbd09/w/66305d5ec61f7e702f95cb19/e/257252c3b4b7940a7d2d69ce)

#### [軌道](https://cad.onshape.com/documents/34135b585923f068c64e636d/w/e4622d2e6695b6f8e27613b4/e/188655490f6853ba60935a87)

#### [送球軌道](https://cad.onshape.com/documents/4e4bf2fc0c83eb85ac7dbd09/w/66305d5ec61f7e702f95cb19/e/e4dc8a20e1fe43e974ebbe5e)

#### [底板](https://cad.onshape.com/documents/60e054344ad0c31cf5998bcf/w/703aa498b5ab4c0cb4020e6c/e/b19b3dd59e8bbc1087e1a357)

#### [機構](https://cad.onshape.com/documents/c3db732e372f78e9d4bf49b2/w/e55eac7cd4fbbe87b141ce6a/e/3030aab0a6c780c08b60b44a)

#### [抬球機構相關零件檔案](https://github.com/s40523139/cd2018/tree/gh-pages/w7%E9%9B%B6%E4%BB%B6%E5%8F%8A%E5%B7%A5%E7%A8%8B%E5%9C%96)


#### 下方為鋼球機構循環兩周的影片

[https://www.youtube.com/watch?v=B7ac78zil7o&feature=youtu.be](https://www.youtube.com/watch?v=B7ac78zil7o&feature=youtu.be)

# 零件表

| 件號 | 品名 | 數量 |
| :---: | :---: | :---: |
| 1 | 底平台 | 1 |
| 2 | 主軸 | 1 |
| 3 | 輔助軌道 | 1 |
| 4 | 軌道 | 1 |

# 工作分配

#### 40523130: gitbook撰寫、零件與工程圖繪製

#### 40523133: gitbook撰寫、作業演練

#### 40523139: gitbook撰寫、V-rep模擬、作業演練

# 自評:

#### 40523130:75

#### 40523133:75

#### 40523139:75



