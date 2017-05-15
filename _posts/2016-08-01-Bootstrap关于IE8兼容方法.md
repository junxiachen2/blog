---
title:        "Bootstrap关于IE8兼容方法"
# jekyll-seo-tag
description:  "Bootstrap关于IE678兼容方法"
author:       "junxiachen"
---
搞前端以来一直没有遇到过比较大的兼容问题，在上个星期开发一个用 Bootstrap 的网站时终于遇到了/(ㄒoㄒ)/~~特此记录一下      

这次的项目网站采用 Bootstrap 作为样式库，因为开发前没有先仔细了解 Bootstrap 对浏览器的支持，导致到了测试阶段才发现这个框架居然是不支持 IE678 的。这里需要自我反省下，也提醒像我一样的新手们。还好， Bootstrap 在国内已经有很多前辈们使用过，有了兼容的方法。       

首先，对于 IE8 其实还是可以支持的，只是还有一些 CSS3 属性和 HTML5 元素不被支持，因此只需要配合 [Response.js](https://github.com/scottjehl/Respond) 就可以完美展现了，respond.js 是用于支持媒体查询的文件。另外，respond.js 要和需要进行媒体查询的文件放在同一域中。不然CDN部署的需要更改一些选项，这里官网也有给出说明。 
    
然后，就是引入 html5.js 使得一些不支持 html5 标签的浏览器可以支持 html5 。      

总结一下，其实很简单，只需要在 head 标签中加入以下这段代码就可以了。    

```
<!--[if lte IE 9]>  
<script src="lib/respond.js"></script>  
<script src="lib/html5.js"></script>  
<script src="http://libs.baidu.com/jquery/1.10.2/jquery.js"></script>  
<![endif]--> 
```




