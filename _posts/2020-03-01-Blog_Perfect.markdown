---
title: 搭建个人博客历程
tags: [杂项note]
background_music: <iframe frameborder="no" border="0" marginwidth="0" marginheight="0" width=100% height=86 src="//music.163.com/outchain/player?type=2&id=1424523772&auto=1&height=66"></iframe> 
date: 2020-03-01
---

好久之前就看到别人搭建的这种博客(~~羡慕，想拥有，得不掉就毁到~~) ，然后刚刚好大一寒假因为疫情变得超级长，所以就看着网上的教程开始了折腾

开发过程得益于谷歌搜索  
(等有无聊的时间就更新详细教程)

各种功能前人都有完整教程，跟着做就行了  
这里列出我的所有参考资料，感谢

>参考资料
[Jekyll + Github Pages 博客搭建入门](https://www.jianshu.com/p/9f198d5779e6)   
[Jekyll博客Next主题超深度配置](https://blog.csdn.net/ds19991999/article/details/81516568)   
[应用软件:Jekyll 配置](https://www.jianshu.com/p/bb184f61c9ae)   

基本构建完成后就可以开始添加一些自己想要的功能，想要什么功能就用谷歌搜，应有尽有

## **DIY**

> 2020-01-20-----

### 🥇**已完成的功能模块**🥇



- [x] **绑定域名**  
>有需要时续费即可

https://fearlessroy.net/2018/01/29/binddomain/

[https://cloud.tencent.com/developer/article/1421879](https://cloud.tencent.com/developer/article/1421879)

使用腾讯云购买域名


- [x] **加入 Live2D 看板娘**
>这里给出我的参考链接，之后会自定义一个属于自己的模板
>[网页添加 Live2D 看板娘。](https://www.fghrsh.net/post/123.html)
>[](https://imjad.cn/archives/lab/add-dynamic-poster-girl-with-live2d-to-your-blog-02/)
>第二个链接的博客弄的非常好看



- [x] **$katex$ 行间公式渲染**

```html
<link rel="stylesheet" href="//cdn.jsdelivr.net/npm/katex/dist/katex.min.css" />
<script
  src="//cdn.jsdelivr.net/npm/katex/dist/katex.min.js"
  defer="defer"
></script>
<script
  src="//cdn.jsdelivr.net/npm/katex/dist/contrib/auto-render.min.js"
  defer="defer"
  onload='renderMathInElement(document.body, { delimiters: [{ left: "$", right: "$", display: false }] })'
></script>
```
```html
<script
  src="//cdn.jsdelivr.net/npm/katex/dist/contrib/mathtex-script-type.min.js"
  defer="defer"
></script>
```

- [x] **mermaid 流程图**

```html
<link
  rel="stylesheet"
  href="//cdn.jsdelivr.net/npm/mermaid/dist/mermaid.min.css"
/>
<script
  src="//cdn.jsdelivr.net/npm/mermaid/dist/mermaid.min.js"
  defer="defer"
  onload='
    for(let x=document.getElementsByClassName("language-mermaid"), i=0;i<x.length;i++)
    {
      x[i].classList.add("mermaid");
      x[i].classList.remove("language-mermaid");
    }'
></script>
```



- [x] **字体样式：**
- 采用 Source Code Pro 加等宽字体构建
```css
.sidebar {
  font-family: Menlo, Monaco, "Source Code Pro", Microsoft JhengHei, monospace;
} 
```


- [x] **雾化效果**
>防止背景影响阅读体验
```css
.container {
      background-color: rgba(255, 255, 255, 0.7);
      box-shadow: 0 0 1rem 1rem rgba(255, 255, 255, 0.7);
      text-shadow: 1px 1px 1px rgba(255, 255, 255, 0.021);
      min-height: 3vh;
    }
```



- [x] **评论系统gitalk**

>使用GitHub账户即可直接进行评论储存在 comment 里的 issue 中

>但是不能DIY样式并且时不时的会崩掉(因为汉字转换后的 url 有时太长所以会崩掉 )

>以后会更换 valine 可能 -03-01 -2020

>缩短文件名字为50字符以下后gitalk就能用了 ~~以后用纯英文定义我的文件名 -03-02 -2020

[https://aerolith.ink/2018/08/25/Gitalk/](https://aerolith.ink/2018/08/25/Gitalk/)

[https://draveness.me/git-comments-initialize](https://draveness.me/git-comments-initialize)



- [x] **兼容emoji表情**

> 使用快捷键`win+;`可以直接召唤表情库



- [x] **添加网易云模块**

```html
 网易云官方接口： 大歌单类型插入
<iframe frameborder="0" border="1" 
            marginwidth="0" marginheight="0"
            width="100%" height="450" 
            src="//music.163.com/outchain/player?type=2&amp;id=553795744&amp;auto=1&amp;height=80">
    </iframe>
                标题类型插入
<iframe frameborder="no" border="0" marginwidth="0" marginheight="0" width=100% height=86 src="//music.163.com/outchain/player?type=2&id=(------)&auto=1&height=66"></iframe>  
id从网易云网址即可获得
```
> auto：0/1 1表示打开网页的时候自动播放。0表示打开网页的时候不自动播放；



- [x] **彩色滚动条**
>花里胡哨+1
```css
::-webkit-scrollbar {
      width: 3px;
      height: 7px;
    }
  ::-webkit-scrollbar-thumb {
    background: linear-gradient(-45deg, #ee7752, #e73c7e, #23a6d5, #23d5ab);
  }
```



- [x] **动画淡入淡出效果**
>花里胡哨+2
```css
.masthead,
          .content,
          .sidebar-toggle,
          .pio-container {
            animation: animationAppear 2s;
          }
          @keyframes animationAppear {
            0% {
              opacity: 0;
            }
            33% {
              opacity: 0;
            }
            100% {}
          }
```
- [x] **github** **仓库徽标**
- 2020-03-01
>之前没有记录时间..
```https://img.shields.io/badge/{徽标标题}-{徽标内容}-{徽标颜色}.svg```

如果我们在写markdown的时候想为我们的徽章或者进度条添加点击跳转的超链接,可以使用超链接和图片的语法嵌套来写,具体可以参照markdown标准语法.
[![](徽章/进度条URL)](点击超链接)

- [x] **采用js为我的博客添加了点击效果**
- 2020-03-02
>花里胡哨+3
在我的 js/click.js 里面存在源码
然后在</body>结束前引用一次就ok了















***
### 💎**未完成的功能模块**💎
>需求与日俱增

- [ ] 翻页功能,按照时间线查询前后文章翻页
> 上一篇，下一篇那种 ，博文多了后还可以按照标题在文章末尾推荐猜你喜欢
- [ ] 想弄一个顶部显示实时播报的进度条
>这样：
>![46AE5778012E9A0825C0CA51EEB3A56A.jpg](https://raw.githubusercontent.com/fengwei2002/picture/master/picture46AE5778012E9A0825C0CA51EEB3A56A.jpg)

- [ ] 赞赏模块(没用)
>写博客又不是为了得到 ￥ ，但应该尝试模块化这个功能，失陷后关闭即可

- [ ] 归档所有文章那里按照每个月的博文进行时间线划分  
>这样：
>![7150A4ACCCDC70EF14CF55CA15E58F1D.jpg](https://raw.githubusercontent.com/fengwei2002/picture/master/picture7150A4ACCCDC70EF14CF55CA15E58F1D.jpg)
- [ ] tags 的每个分类后面添加这种图标
>这样：
>![491DF35BE214CCF6D453FD1984D08549.jpg](https://raw.githubusercontent.com/fengwei2002/picture/master/picture491DF35BE214CCF6D453FD1984D08549.jpg)
- [ ] 首页展示图片当点开博文时，文字下面不应该存在图片
> 这样
> ![36D86354C88A093D009CC82EC44D50E7.jpg](https://raw.githubusercontent.com/fengwei2002/picture/master/picture36D86354C88A093D009CC82EC44D50E7.jpg)
> 这种效果比较稳重，且便于查看，目前模式有点花里胡哨
- [ ] 自己完成一个自定义的live2D模块
- [ ] 弄一个那种不用登录的评论系统
>上次见到别人博客中有，是真的方便啊(我应该加个邮箱地址以便我的回复评论者可以收到)
- [ ] 鼠标指针预览动画
>JavaScript 可以实现 (这个功能好看)
- [ ] 鼠标指针点击动画
> 每次鼠标右键点击出现击碎砖块的烟花效果
- [ ] 图片悬浮放大特效

## 结尾

本来把博客部署在Github就是为了省事，没想到却越来越折腾了。

人生真是充满了矛盾。