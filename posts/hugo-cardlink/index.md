# Hugo 添加知乎卡片式链接 Shortcodes


{{< cardlink href="https://github.com/Lruihao/hugo-blog/commit/089c303693e806bff855ecf3fee110baa62b870b" content="知乎卡片式链接 Git 記錄" >}}

{{< admonition quote "回顧" >}}
  之前在使用 hexo 的時候也有用到，[模仿知乎卡片式链接](/posts/linkcard/)  
  和之前的相比，優化之前是后加載，由 JS 在 瀏覽器處理，  
  使用 shortcodes 方式后，則是在 GO 構建頁面的時候處理，效能上會好很多。  
{{< /admonition >}}

<!--more-->
## 源碼
基於 LoveIt 主題的 Link Shortcodes, 主要改到以下幾個文件，[完整提交記錄](https://github.com/Lruihao/hugo-blog/commit/089c303693e806bff855ecf3fee110baa62b870b)  

    assets/css/custom.scss
    assets/css/partial/cardlink.scss          # 卡片式鏈接樣式
    layouts/partials/plugin/cardlink.html     # 卡片式鏈接模板
    layouts/shortcodes/cardlink.html
    static/images/card-link-bg.jpg

## 使用
使用參數同 [LoveIt 擴展 Shortcodes - Link](https://hugoloveit.com/zh-cn/theme-documentation-extended-shortcodes/#2-link)
```markdown
{{</* cardlink href="https://github.com/Lruihao/hugo-blog/commit/089c303693e806bff855ecf3fee110baa62b870b" content="知乎卡片式链接 Git 記錄" */>}}
```
