### 期末專案 Week 10 分組任務回報

## 設計 :


利用Pyslvs所製作的兩段式六連桿機構

![](https://blobscdn.gitbook.com/v0/b/gitbook-28427.appspot.com/o/assets%2F-LAgU-7dFCj3b3oIJIST%2F-LD4fj7jNXXe3mNlU6ad%2F-LD4kphPaBjtY9BjT8Iq%2F12344.gif?alt=media&token=66e6695b-8ea6-412b-8b4e-48cb45f5ad97)

將 Pyslvs 檔匯出成Solvespace所使用的 slvs 檔，供後續程序使用。

![](https://blobscdn.gitbook.com/v0/b/gitbook-28427.appspot.com/o/assets%2F-LAgU-7dFCj3b3oIJIST%2F-LD4fj7jNXXe3mNlU6ad%2F-LD4nxlPiNBbN_pE7rAP%2Fcad.gif?alt=media&token=f9b35f42-6616-4d83-9edc-45824bc589ea)


## 組立 :

透過輸出的CAD檔，依尺寸繪製立體零件與組立

![](https://blobscdn.gitbook.com/v0/b/gitbook-28427.appspot.com/o/assets%2F-LAgU-7dFCj3b3oIJIST%2F-LD4fj7jNXXe3mNlU6ad%2F-LD4n0Y7w5ROHKuZ6DBf%2Fqqq.gif?alt=media&token=1ddd1094-9794-49ff-9a98-b3261c8b88ae)

## 模擬 :

組立好的零件導入 V-REP軟體，進行動態模擬運作。

![](https://blobscdn.gitbook.com/v0/b/gitbook-28427.appspot.com/o/assets%2F-LAgU-7dFCj3b3oIJIST%2F-LD4fj7jNXXe3mNlU6ad%2F-LD4oSH8FHSRBUmiJzjK%2F12355.gif?alt=media&token=cff62dfa-4c75-4897-862d-9e594e072e57)

## 心得 :

1.本次六連桿機構並非本組學員們設計，是由課程倉儲中所提供，對於多連桿之設計與要求，並未完全的了解，仍為加強知識的部分之一。

2.組立零件得先用CAD軟體先做完初步設計與位置配合，了解相對位置後，在設計3D零組件時，才不會發生干涉。

3.從V-REP模擬軟體了解到

        (1) 有關Dummy的應用。

        (2) 一個實體可以裝很多Revolute joint，但一個​Revolute joint只能裝一個實體。

4.在V-rep模擬中，由於零件可能過於複雜，若將實體加入碰撞，則軟體較難計算，導致模擬緩慢

或發生錯誤，對於精簡化的部分還需要更加了解。

Files:

​[CAD](https://github.com/s40523120/cd2018/blob/master/simulation/cd_w11_ag9.slvs) (Type for Solvespace)

​[Pyslvs​](https://github.com/s40523120/cd2018/blob/master/simulation/Ball_lifter_ag9.pyslvs)

​[V-rep​](https://github.com/s40523120/cd2018/blob/master/simulation/linkforvrep_ag9.ttt)

​[Assembly](https://github.com/s40523120/cd2018/blob/master/simulation/six_link_ag9.stl)

​[Assembly for Onshape](https://cad.onshape.com/documents/95fad782dbee89083d2c623d/w/9341a39e3ced12a442199193/e/b14ea431517f58f62c9286b4)
