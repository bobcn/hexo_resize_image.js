# hexo_resize_image.js

在使用 Hexo 的过程中发现 Markdown 的原生语法貌似没办法设置图片的大小。

在网上搜索了一下，貌似比较好的做法是：

```html
<img src="/image/test.jpg" width="50%" height="50%">
```

不过我还是想用 Markdown 的原生语法,于是用我抠脚的 JS 写了一个，源码附在底端。

## 语法

扩展了 Markdown 的插图语法如下：

1. 可指定像素

    方法是在 URL 后面添加 `?<width>x<height>` 

    ```markdown
    ![指定像素](/image/test.jpg?200x200)
    ```

2. 可指定缩放比例

    方法是在 URL 后面添加 `?<scale>`

    ```markdown
    ![指定比例](/image/test.jpg?40)
    ```

## 添加到页面中

在模板中为页面添加 js 脚本。

我使用的是 huno 主题，在 `theme/huno/layout/layout.ejs` 中 `</body>` 前添加了如下语句：

```html
<script src="<%- config.root %>js/hexo_resize_image.js"></script>
```
