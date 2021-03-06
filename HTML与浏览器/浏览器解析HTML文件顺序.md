# 解析组成文件的顺序
 当浏览器向服务器发送请求获取 HTML 文件时，HTML 文件通常包含 "link" 和 "script" 元素，这些元素分别指向了外部的 CSS 样式表文件和 JavaScript 脚本文件。了解这些文件被浏览器解析的顺序是很重要的：

1. 浏览器首先解析 HTML 文件，并从中识别出所有的 "link" 和 "script" 元素，获取它们指向的外部文件的链接。
2. 继续解析 HTML 文件的同时，浏览器根据外部文件的链接向服务器发送请求，获取并解析 CSS 文件和 JavaScript 脚本文件。
3. 接着浏览器会给解析后的 HTML 文件生成一个 DOM 树（在内存中），会给解析后的 CSS 文件生成一个 CSSOM 树（在内存中），并且会编译和执行解析后的 JavaScript 脚本文件。
4. 伴随着构建 DOM 树、应用 CSSOM 树的样式、以及执行 JavaScript 脚本文件，浏览器会在屏幕上绘制出网页的界面；用户看到网页界面也就可以跟网页进行交互了。

 script 元素没必要非要放在文档的 head 中，并包含 src 属性来指向需要加载的 JavaScript 文件路径，同时最好加上 defer 以告诉浏览器在解析完成 HTML 后再加载 JavaScript。这样可以确保在加载脚本之前浏览器已经解析了所有的 HTML 内容（如果脚本尝试访问某个不存在的元素，浏览器会报错）。