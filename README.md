# PicGo + GitHub 搭建个人图床工具

### 为什么需要图床

大家在使用typora等markdown文本编辑工具写markdown文本时，尤其文本插入有图片情况时，很难实现文本的移动阅读（图片会丢失），因此我们需要图床，一般指存储图片的服务器，通俗易懂来讲，我们上传图片后会得到图片的链接，这样就可以通过此链接来查看图片，实现移动阅读。

常用的图床有：Github图床、微博图床、SM.MS图床、七牛图床、腾讯云COS等等

本文向大家推荐Github图床，因为别的图床尤其七牛，你可以免费使用一年半载，但免费期一过，图片链接就消失了

### 图床工具 PicGo

[PicGo](https://github.com/Molunerfinn/PicGo)是一款图床工具，供大家上传图片到图床，而且支持前面说到的众多常用图床，我这里集成到Github,通过PicGo官网或者github链接可以下载各种版本，其中dmg格式是Mac,exe格式是windows

![](https://raw.githubusercontent.com/penghuima/ImageBed/master/img/blog_file/PicGo-Github-ImgBed1622612845.png)

### 新建github仓库

安装完毕后，需要先在github上创建自己的图片存储仓库，例如我创建了一个[ImageBed](https://github.com/penghuima/ImageBed)的仓库，仓库得设置为public，供后面客户端的访问，创建仓库这里就不展开描述了

### 获取github个人账户token

点击github个人用户头像-->Settings-->Developer settings-->Personal access tokens  点击进入创建token

![](https://cdn.jsdelivr.net/gh/penghuima/ImageBed@master/img/blog_file/PicGo-Github-ImgBed1622616772(1).png)

Note内容自己随便写，只需要勾中复选框`repo`,接着到底部生成token序列就可以了，复制生成的token序列（最好找文本存一下，因为这个序列只出现一次，下次查看只能update token又换成新的不同序列了）

### PicGo配置

配置结果如下图所示：

![](https://cdn.jsdelivr.net/gh/penghuima/ImageBed@master/img/blog_file/PicGo-Github-ImgBed1622614302(1).png)

- 设定仓库名：即你本身的github仓库名
- 设定分支名：即你仓库分支，这里需要看你个人github仓库分支（默认仓库分支是main，后来本人将分支重命名为master）
- 设定token:即刚才的个人token序列
- 指定存储路径：就是仓库文件夹设置，一般是/img开头，这样你的仓库里面会自动生成img文件目录，里面存放着你上传的图片
- 设定自定义域名：就是你以后使用图片时的url链接前缀，`https://raw.githubusercontent.com/<用户名>/<仓库名>/分支`

> 这里提供一个加速访问图片的方法：CDN加速
>
> 原域名格式：https://raw.githubusercontent.com/penghuima/ImageBed/master
>
> 现域名格式：https://cdn.jsdelivr.net/gh/penghuima/ImageBed@master

PicGo里面的设置大家可以自己看下摸索，主要是要开启服务，默认监听地址为：127.0.0.1，监听端口为36677，剩下的就是开机自启选项、上传前图片重命名选项等，截至到目前，我没感觉图片重命名有什么需要

### 上传图片并使用图片链接

![](https://cdn.jsdelivr.net/gh/penghuima/ImageBed@master/img/blog_file/PicGo-Github-ImgBed20210602151517.png)

在这里给大家介绍一种也是大家常用到的图片上传方式，剪贴板图片上传方式，当你使用截图工具截图之后，图片还保存在剪贴板中，这时你点击工具中的 `剪贴板图片`按钮，就自动将图片上传到github仓库了，使用的时候点开工具相册按钮

![](https://cdn.jsdelivr.net/gh/penghuima/ImageBed@master/img/blog_file/PicGo-Github-ImgBed20210602152334.png)

选中红色矩形框中的图片URL链接，就可以随意在markdown文档里粘贴使用了

### Typora具体应用

[Typora](https://www.typora.io/)是一款很还用的markdown编辑工具，简洁且强大，通过设置可将图片自动上传到GitHub仓库

![image-20210602153348259](https://cdn.jsdelivr.net/gh/penghuima/ImageBed@master/img/blog_file/PicGo-Github-ImgBedPicGo-Github-ImgBedimage-20210602153348259.png)

设置完成之后，typora就可以自动调用PicGo应用程序上传图片到图床了，一般粘贴本地图片到markdown文件里时，什么也不需要做了，自动就上传图片了，如果点击图片在选择 `上传图片`按钮，就会发现github仓库里有两张一样的图片，实在是多此一举

当然在使用过程中，有可能会遇到各种问题，多上网逛相关问题帖子，自救

