# 如何在 Gitbook 嵌入影片

由於 Gitbook 中的 README.md 就是整本電子書內定的 introduction, 而 SUMMARY.md 則是 Table of Content, 用來設定各章節標題與對應檔案名稱.
因此, 本頁檔名為 demo.md, 只要在 SUMMARY.md 中納入 demo.md 章節, 並在 Github 倉儲 https://github.com/scrum-1/gitbook 中編輯 Markdown 檔案 dmoo.md 內容時, 將 Youtube 影片中的 embedded html 放入, 就可以得到如下的嵌入影片:

<iframe width="560" height="315" src="https://www.youtube.com/embed/VI-d1C9MkOU" frameborder="0" allow="autoplay; encrypted-media" allowfullscreen></iframe>

但是, 由於上述影片只有在 html 模式下才可檢視, 因此建議除了 iframe 外, 也要提供影片連結: https://www.youtube.com/watch?v=VI-d1C9MkOU, 讓使用者可以透過 pdf 檔案時, 連結到對應的影片.

# 如何利用 Pandoc 與 MikTeX 轉換檔案

https://pandoc.org/ 是一個能夠將 Markdown 檔案轉換為 html 與 LaTeX 格式的工具, 而 LaTeX 格式又可以透過 https://miktex.org/ 轉為 pdf 檔案, 因此目前 https://github.com/scrum-1/gitbook 倉儲中的所有 .md 檔案, 可以在 Pandoc 與 MikTeX 的配合下, 完成 Gitbook 所提供的服務.
