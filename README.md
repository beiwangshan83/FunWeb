# FunWeb基于奇趣网站收藏家fuun.fun二次修改版

此版本为**::name_badge:开发版:name_badge:**，部署请使用**:hamburger:FunWeb-min:hamburger:**   

## :walking:预览

**FunWeb be based on fuun.fun Template 奇趣网站收藏家 二次修改版**

:earth_africa:原作者网站：**[奇趣网站收藏家](https://fuun.fun)**

:waning_crescent_moon:预览站点：**[Fun's Web有趣网站](https://www.beiwangshan.com/fw/index.html)**

:waning_gibbous_moon:我的博客站：**[北忘山の博客](https://www.beiwangshan.com)**



图片



## :rainbow_flag:修改点

- PC端增加返回顶部按钮，移动端正在适配
- 修改浏览器滚动条样式
- 静态资源使用JsDriver加速引入
- 随机壁纸



## :tada:部署使用

### 站点使用

:taxi:移步至最新发布版本:**[Release 第一次修改版 · beiwangshan83/FunWeb (github.com)](https://github.com/beiwangshan83/FunWeb/releases/tag/1.0.0)**

:taxi:解压后上传FunWeb里面的所有内容至网站根目录，站点使用纯静态



:taxi:访问站点即可



## :dart:修改配置

### :calling:评论系统

网站评论系统使用**[valine](https://valine.js.org/)**

**[valine申请教程](https://valine.js.org/quickstart.html)**

自行去该网站注册用户，获取appId和appKey，申请好之后，编辑share.html

在share.html文件中搜索`推荐有趣的网站吧`定位到appId和appKey的位置，具体代码如下：

```javascript
<script
            type="text/javascript"> loadComments(); function loadComments() { if (typeof Valine === 'undefined') { var getScript = (options) => { var script = document.createElement('script'); script.defer = true; script.crossOrigin = 'anonymous'; Object.keys(options).forEach((key) => { script[key] = options[key]; }); document.body.appendChild(script); }; getScript({ src: 'https://cdn.jsdelivr.net/npm/valine@1.4.14/dist/Valine.min.js', onload: () => { newValine(); } }); } else { newValine(); } } function newValine() { new Valine({ el: '#vcomments', appId: 'u0EtQJ6KPs4kEw0nptbhYOrp-gzGzoHsz', appKey: 'peanhvXypOBhozptvLzQ0kkg', placeholder: '推荐有趣的网站吧~', avatar: 'wavatar', meta: ['nick', 'mail'], requiredFields: ['nick'] }); }</script>
    
```

修改其中的appId和appKey即可



### :pager:图床选择

页面中的所有图片均使用https://sm.ms/，你也可以把图片上传到此



### :v:添加网站

添加比较麻烦，因为是纯静态，但是目前系统已经有192个网站，坚持做收藏。

#### :bee:添加导航块

除了share.html，其他文件中均有以下模块，这部分会在页面的左侧输出

```html
<header>
...
</header>
```

如果你想添加一个导航块，在`<header></header>`中按照格式添加`<li><li>`即可

```html
<li>
...
<li>
```

>**特别注意：**
>
>以上所有添加的内容都需要除了share.html的每个页面添加

#### :bee:添加网站

除了share.html，其他文件中均有以下模块，这部分会在页面的右侧输出

```html
<section class="main">
...
</section>
```

如果你想添加一个网站，只需要在`<section class="main"></section>`添加`<div class="link_item"></div>`即可

```html
    <div class="link_item">
        <div class="content"> <img src="https://i.loli.net/2021/03/16/KYdyCkliMjagrSV.png" alt="" class="logo"
                loading=lazy>
            <div class="title a_animation"> <a href="https://digicol.dpm.org.cn/" target="_blank">故宫博物院数字文物库 <svg
                        xmlns="http://www.w3.org/2000/svg" width="18" height="18" viewBox="0 0 24 24" fill="none"
                        stroke="#000000" stroke-width="2" stroke-linecap="round" stroke-linejoin="round">
                        <g fill="none" fill-rule="evenodd">
                            <path
                                d="M18 14v5a2 2 0 0 1-2 2H5a2 2 0 0 1-2-2V8c0-1.1.9-2 2-2h5M15 3h6v6M10 14L20.2 3.8" />
                        </g>
                    </svg> </a></div>
            <div class="description">在线查看故宫博物院众多藏品，可根据分类和年代浏览</div>
            <div class="category" style="background-color:#316AF1;color:#316AF1"> 世界</div>
        </div>
    </div>
```

> **特别注意：**
>
> 你在index.html页面添加之后，还需要到特定的分类页面进行添加，添加方式如上