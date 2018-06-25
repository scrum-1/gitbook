第一節進行點名

缺課名單



W7a第一節點名時未到者:

40523105

40523109

40523112

40523115

我還在睡

母湯

40523121

40523125

40523131

40523140

40523142

40523144

40523148

### **利用 Python3 找出缺席名單**

```
with open("cd_w7a.txt", "r", encoding="utf-8") as fh:
```

```
    # 逐行讀出檔案資料, 並放入數列中
    lines = fh.readlines()
    raw_data = lines[1:]
    #print(raw_data)
    # 設法用迴圈逐數列內容取出字串
    # k 為集合所有檔案中的學號字串, 先設為空字串
    k = []
    for i in range(len(raw_data)):
        # 利用 strip() 去除各行字串最末端的跳行符號
        raw_line = raw_data[i].strip()
        # 利用 split() 將以 \t 區隔的字串資料分離後納入 groups 字串
        groups = raw_line.split("\t")
        #print(groups)
        # 逐一進入各行中的各字串去除空字串
        for j in range(len(groups)):
            if groups[j] != "":
                # 除了空字串外, 其餘字串放入 k 數列中
                k.append(groups[j])
# 將 k 中只出現一次的字串印出, 即為缺席者名單
absent = [x for x in k if k.count(x) == 1]
print(absent)
```

結果如下:

> \['40523105', '40523109', '40523112', '40523115', '40523121', '40523125', '40523131', '40523140', '40523142', '40523144', '40523148'\]



