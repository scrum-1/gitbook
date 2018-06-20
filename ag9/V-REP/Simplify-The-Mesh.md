> 簡化模型

此教學文檔，為參照V-REP官方文件整理之心得。

## Why Do We Need To Simplify?
在V-REP當中，我們所匯入的模型檔案是基於三角形所呈現的(e.g. .stl)，因此零件當中擁有許多複雜精細的特徵，將會嚴重影響V-REP的運算(e.g. 最小距離或是動態模擬)，所以我們勢必簡化模型，減少運算負擔，在不影響模擬真實程度之下，提升工作速度，減少動態模擬衝突。

以下三點為簡化模型之方法:

- Automatic mesh division 自動分割:

它會將所有未相互連接的元素自動分割。
我們可以特過以下步驟為模型簡化:

 [Menu bar --> Edit --> Grouping/Merging --> Divide selected shapes]

但有時候會產生多餘的網格項目，這時我們就得將應屬於同一個元素的部分選取，將它合併:

 [Menu bar --> Edit -> Grouping/Merging --> Merge selected shapes]

-  Extract the convex hull 提取凸包:

 將三角形網格變換為凸包來簡化模型。

 [Menu bar --> Edit --> Morph selection into convex shapes]

- Decimate the mesh 抽取

 減少模型中包含的三角形的數量。

 [Menu bar --> Edit --> Decimate selected shape...]

- Remove the inside of the mesh 去除模型內部

 通過去除其內部來簡化模型。

 [Menu bar --> Edit --> Extract inside of selected shape]
