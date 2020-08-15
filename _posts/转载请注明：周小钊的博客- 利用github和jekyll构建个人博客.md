> 本文由 [简悦 SimpRead](http://ksria.com/simpread/) 转码， 原文地址 https://www.jianshu.com/p/ea8cdecc4ce6

我们知道，一个网站要能够在任何地方都能够被访问，那么需要部署到服务器上，但是对于我们来说，构建服务器的花销是巨大的。幸运的是，github 就提供了这样的功能，只要按照 github 格式要求，新建一个仓库，把你的网站代码上传到里面，你就有一个自己的免费网站了。

废话不多说，让我们利用 jekyll 和 github 来构建自己的博客吧！！

jekyll 支持 mac、linux、windows 等，鉴于大部分童鞋使用的是 windows 系统，那我就用 windows 构建

1. 下载安装 ruby installer
----------------------

[https://rubyinstaller.org/](https://links.jianshu.com/go?to=https%3A%2F%2Frubyinstaller.org%2F) ，点击相应的版本进入下载页面即可下载

![](http://upload-images.jianshu.io/upload_images/16572814-fccfc722e51f490d.png)

ruby installer

2. 下载 rubygems
--------------

[https://rubygems.org/pages/download](https://links.jianshu.com/go?to=https%3A%2F%2Frubygems.org%2Fpages%2Fdownload) ，可以选择相应版本下载  

![](http://upload-images.jianshu.io/upload_images/16572814-00cb8fe07ff2871e.png)

rubygems

下载完成后解压到你想放的位置，比如我放在了 “D:/soft/rubygems3-1.4” 下, 打开 cmd 用命令执行

```
D:
cd soft/rubygems3-1.4
ruby setup.rb
gem install jekyll


```

二：网站构建
------

首先你要到 [GitHub](https://links.jianshu.com/go?to=http%3A%2F%2Fgithub.com) 上注册一个账号, 例如 jungleblack007（用户名可以在设置里改），创建完成后可以去 [jekyll 主题网站](https://links.jianshu.com/go?to=http%3A%2F%2Fjekyllthemes.org%2F)选择自己喜欢的主题，然后在这个主题基础上修改到满足自己需求的博客.

我选择的是[潘柏信](https://links.jianshu.com/go?to=https%3A%2F%2Fgithub.com%2Fleopardpan%2Fleopardpan.github.io)的博客主题，因为这个主题有中文说明，而且有个 B 站 up 主对该主题进行了详细的操作，适合我们入门，先让我们看一下该博客的外貌！  

![](http://upload-images.jianshu.io/upload_images/16572814-165fca77413c3a9d.png)

https://leopardpan.cn/

我们找到作者的[源代码块](https://links.jianshu.com/go?to=https%3A%2F%2Fgithub.com%2Fleopardpan%2Fleopardpan.github.io), 点击右上角的 fork 可以将它拷到我们自己的 github 中，顺便 star 一下支持作者。  
拷到自己的 github 后，我们点击 setting，先进行改名，推荐：你的用户名. github.io  

![](http://upload-images.jianshu.io/upload_images/16572814-ce2f8a57c739f350.png)

rename

然后下拉找到 GitHub Pages，source 选择 master branch，我已经点了所以看不到，然后上方出现一个网址，这个就是你的域名了，可以先看看和原博客有没有区别

![](http://upload-images.jianshu.io/upload_images/16572814-6a782eb2ae328f0f.png)

![](http://upload-images.jianshu.io/upload_images/16572814-1f95655fa39591aa.png)

三：运行 jekyll 生成静态网页
------------------

把别人的主题 fork 以后，我们可以利用 [atom](https://links.jianshu.com/go?to=https%3A%2F%2Fatom.io%2F) 把主题代码转到自己的电脑上

打开 atom，按 ctrl+shift+p，输入 github clone，选择要克隆的网址和要保存的路径。点 clone 即可

![](http://upload-images.jianshu.io/upload_images/16572814-3550aa3d6867fa59.png)

clone 完成后，就会有如下界面

![](http://upload-images.jianshu.io/upload_images/16572814-e96e299249ee80af.png)

修改_config.xml, 把一些信息修改为自己的

![](http://upload-images.jianshu.io/upload_images/16572814-f2e9af2bf5b7e460.png)

图像也可以换，根据 images 的文件夹的图片名称可以换成你想要的，名字要一致，images/posts 主要放置的是笔记中的图片，可以删掉，以后写笔记的时候想插入图片需要把图片路径设置成 images/posts/XXXX。赞赏功能的图片在 paying 里，需要赞赏就改成自己的二维码，不需要赞赏就删掉 new-old.html 里的所有内容

![](http://upload-images.jianshu.io/upload_images/16572814-476e918a00874950.png)

此时，我们可以用 jekyll 来生成一个静态网页查看

```
D
cd data/git
bundler install
bundle exec jekyll serve


```

[http://127.0.0.1:4000](https://links.jianshu.com/go?to=http%3A%2F%2F127.0.0.1%3A4000) 这是我们生成的一个静态页面，浏览器输入即可查看  

![](http://upload-images.jianshu.io/upload_images/16572814-061b4ec4b8eb313f.png)

可以看到背景和个人信息都已经改为了自己的，说明修改成功！

四：写一篇自己的博客
----------

jekyll 比较好的一点是可以识别笔记文件，我们可以把写好的文件放到_post 文件夹下，然后在 md 文件前面加一串代码。

![](http://upload-images.jianshu.io/upload_images/16572814-3856e76d20aa7d4a.png)

写好后可以再运行 bundle exec jekyll serve 查看自己写的博客是否已经能在静态网页上查看

![](http://upload-images.jianshu.io/upload_images/16572814-7505022e52e60ec7.png)

五：添加网站统计功能
----------

我们可以给自己的网站添加统计功能，在这个主题中也支持该功能，推荐使用百度统计，首先注册账号

注册结束后添加新的域名统计

![](http://upload-images.jianshu.io/upload_images/16572814-fa6a8cdbb185aa8a.png)

添加结束后点击管理—代码获取，会看到一串代码。

```
<script>
var _hmt = _hmt || [];
(function() {
  var hm = document.createElement("script");
  hm.src = "https://hm.baidu.com/hm.js?60e2d4433f4c77b3ae5db5cac1b62829";
  var s = document.getElementsByTagName("script")[0]; 
  s.parentNode.insertBefore(hm, s);
})();
</script>



```

? 后面的 60e2d4433f4c77b3ae5db5cac1b62829 可以粘贴替换掉_config.yml 文件中的百度统计

![](http://upload-images.jianshu.io/upload_images/16572814-b86c6fb601e80368.png)

这样统计功能就添加上了

六：添加评论功能
--------

评论功能也可以根据自己的喜好添加，我添加评论功能使用的是[来必力](https://links.jianshu.com/go?to=http%3A%2F%2Flivere.com%2F)

注册账号后添加网页，与百度统计类似，添加结束后点击管理界面 - 代码管理，可以看到一串代码

```
<div data-id="city" data-uid="MTAyMC81MDkzOC8yNzQyMA==">
<script type="text/javascript">
   (function(d, s) {
       var j, e = d.getElementsByTagName(s)[0];

       if (typeof LivereTower === 'function') { return; }

       j = d.createElement(s);
       j.src = 'https://cdn-city.livere.com/js/embed.dist.js';
       j.async = true;

       e.parentNode.insertBefore(j, e);
   })(document, 'script');
</script>
<noscript>为正常使用来必力评论功能请激活JavaScript</noscript>
</div>



```

将该代码复制，替换掉_include/comments.html 中的全部内容即可（这里的 bioinformatics-rookie.github.io 是我自己的博客，文中出现的 jungleblack007.github.io 是我用来做试验的账号）

七：上传到 github
------------

所有内容修改完成后可以将自己的代码上传到 github，atom 也提供此功能。

当你所有的内容修改完毕后，atom 右侧 unstaged changes 会显示你修改了什么内容, 点击 stage all, 所有的会移动到下方的 staged changes.

![](http://upload-images.jianshu.io/upload_images/16572814-84c4ec370e2f7725.png)

在 commit message 中随便写点东西点击下方按钮，在 push 出会出现一个待上传的指令

![](http://upload-images.jianshu.io/upload_images/16572814-d7bceb9a6a889a6b.png)

ctrl + 左键点击 push，使用 force push 功能可以将自己修改过的内容传到 github 服务器上，这样输入你的 github 域名就可以打开自己的网页了，后续的更改同样采取此操作。

参考链接
----

[https://github.com/leopardpan/leopardpan.github.io](https://links.jianshu.com/go?to=https%3A%2F%2Fgithub.com%2Fleopardpan%2Fleopardpan.github.io)

[https://www.jianshu.com/p/9f71e260925d](https://www.jianshu.com/p/9f71e260925d)

[https://www.bilibili.com/video/BV14x411t7ZU?t=537](https://links.jianshu.com/go?to=https%3A%2F%2Fwww.bilibili.com%2Fvideo%2FBV14x411t7ZU%3Ft%3D537)

转载请注明转载请注明：[周小钊的博客](https://links.jianshu.com/go?to=https%3A%2F%2Fbioinformatics-rookie.github.io) - [利用 github 和 jekyll 构建个人博客](https://links.jianshu.com/go?to=https%3A%2F%2Fwww.zhouxiaozhao.cn%2F2020%2F07%2F09%2Fgithub%2Bjekyll%2F)
