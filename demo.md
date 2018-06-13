# 測試電子書的改版

設法修正錯誤

# 如何在 Gitbook 嵌入影片

由於 Gitbook 中的 README.md 就是整本電子書內定的 introduction, 而 SUMMARY.md 則是 Table of Content, 用來設定各章節標題與對應檔案名稱.

因此, 本頁檔名為 demo.md, 只要在 SUMMARY.md 中納入 demo.md 章節, 並在 Github 倉儲 https://github.com/scrum-1/gitbook 中編輯 Markdown 檔案 dmoo.md 內容時, 將 Youtube 影片中的 embedded html 放入, 就可以得到如下的嵌入影片:

<iframe width="560" height="315" src="https://www.youtube.com/embed/VI-d1C9MkOU" frameborder="0" allow="autoplay; encrypted-media" allowfullscreen></iframe>


但是, 由於上述影片只有在 html 模式下才可檢視, 因此建議除了 iframe 外, 也要提供影片連結: https://www.youtube.com/watch?v=VI-d1C9MkOU, 讓使用者可以透過 pdf 檔案時, 連結到對應的影片.

# 如何輸入數學方程式

## 啟用 math plugin:

啟用數學方程式轉檔, 必須在倉儲中加入檔案 book.json, 且內容為:

    {
        "plugins": ["mathjax"]
    }

在文章中加入數學符號式, 當 $$a \ne 0$$, 一元二次方程式 $$(ax^2 + bx + c = 0)$$ 有兩組解, 可以寫成: 

$$x = {-b \pm \sqrt{b^2-4ac} \over 2a}.$$

原始內容為:

    在文章中加入數學符號式, 當 $$a \ne 0$$, 一元二次方程式 $$(ax^2 + bx + c = 0)$$ 
    有兩組解, 可以寫成: 

    $$x = {-b \pm \sqrt{b^2-4ac} \over 2a}.$$
    
注意: 在 Gitbook 第一版中使用 mathjax plugin, inline 必須使用兩個 dollar signs 才能正確顯示, 而在 pandoc 與 LaTeX 或原始版本的 mathjax, inline 只需要使用一個 dollar sign.

# 如何利用 Pandoc 與 MikTeX 轉換檔案

https://pandoc.org/ 是一個能夠將 Markdown 檔案轉換為 html 與 LaTeX 格式的工具, 而 LaTeX 格式又可以透過 https://miktex.org/ 轉為 pdf 檔案, 因此目前 https://github.com/scrum-1/gitbook 倉儲中的所有 .md 檔案, 可以在 Pandoc 與 MikTeX 的配合下, 完成 Gitbook 所提供的服務.

當 kmol_level2 納入 pandoc 與 MikTeX 工具之後, 可以使用下列指令, 將 md 檔案轉換為 pdf 檔案:

pandoc README.md chapter1.md cd.md cp.md lua-programming.md wcms.md demo.md -o report.pdf --pdf-engine=xelatex -V CJKmainfont="SimSun" -V documentclass=report -V lang=zh-cmn -N --toc

# Pyslvs 平面機構模擬與合成套件

https://github.com/KmolYuan/Pyslvs-PyQt5 是一套由國立虎尾科技大學機械設計工程系自行開發的平面多連桿機構的模擬與合成套件, 可以用於 KMOLab 所開列的課程中.

[pyslvs-18.4.0.mscv1900-amd64.7z](pyslvs-18.4.0.mscv1900-amd64.7z) 版本下載.

# Gitbook 舊版 Documentation

https://github.com/GitbookIO/documentation
