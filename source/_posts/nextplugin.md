---
title: hexo插件及next内置样式集
date: 2018-11-24 16:54:09
tags:
- hexo
- 前端
- pdf
categories: hexo
password:
abstract:
message:
description:
top:
author:
permalink:
---

{% note info %}
让文章写的好看又简洁又好用的插件！
{% endnote %}

<!--more-->
### hexo插件

#### hexo-tag-dplayer
[more](https://github.com/MoePlayer/hexo-tag-dplayer)
##### npm install
```
npm install hexo-tag-dplayer --save
```
##### Usage
```
{% dplayer key=value ... %}
```
key can be 
```
dplayer options:
    'autoplay', 'loop', 'screenshot', 'hotkey', 'mutex', 'dmunlimited' : bool options, use "yes" "y" "true" "1" "on" or just without value to enable
    'preload', 'theme', 'lang', 'logo', 'url', 'pic', 'thumbnails', 'vidtype', 'suburl', 'subtype', 'subbottom', 'subcolor', 'subcolor', 'id', 'api', 'token', 'addition', 'dmuser' : string arguments
    'volume', 'maximum' : number arguments
container options:
    'width', 'height' : string, used in container element style
other:
    'code' : value of this key will be append to script tag
```

##### example
```
{% dplayer "url=https://moeplayer.b0.upaiyun.com/dplayer/hikarunara.mp4" "addition=https://dplayer.daoapp.io/bilibili?aid=4157142" "api=https://api.prprpr.me/dplayer/" "pic=https://moeplayer.b0.upaiyun.com/dplayer/hikarunara.jpg" "id=9E2E3368B56CDBB4" "loop=yes" "theme=#FADFA3" "autoplay=false" "token=tokendemo" %}
```
{% dplayer "url=https://player.youku.com/embed/XMzY0MzgxNDMyOA==" "addition=https://dplayer.daoapp.io/bilibili?aid=4157142" "api=https://api.prprpr.me/dplayer/" "pic=https://moeplayer.b0.upaiyun.com/dplayer/hikarunara.jpg" "id=9E2E3368B56CDBB4" "loop=yes" "theme=#FADFA3" "autoplay=false" "token=tokendemo" %}

#### hexo-tag-aplayer
[more](https://github.com/MoePlayer/hexo-tag-aplayer)
##### 安装
```
npm install --save hexo-tag-aplayer
```
##### 使用

```
{% aplayer title author url [picture_url, narrow, autoplay, width:xxx, lrc:xxx] %}
```

##### 标签参数

- `title` : 曲目标题
- `author`: 曲目作者
- `url`: 音乐文件 URL 地址
- `picture_url`: (可选) 音乐对应的图片地址
- `narrow`: （可选）播放器袖珍风格
- `autoplay`:  (可选) 自动播放，移动端浏览器暂时不支持此功能
- `width:xxx`: (可选) 播放器宽度 (默认: 100%)
- `lrc:xxx`: （可选）歌词文件 URL 地址

当开启 Hexo 的 [文章资源文件夹](https://hexo.io/zh-cn/docs/asset-folders.html#%E6%96%87%E7%AB%A0%E8%B5%84%E6%BA%90%E6%96%87%E4%BB%B6%E5%A4%B9) 功能时，可以将图片、音乐文件、歌词文件放入与文章对应的资源文件夹中，然后直接引用：

```
{% aplayer "Caffeine" "Jeff Williams" "caffeine.mp3" "picture.jpg" "lrc:caffeine.txt" %}

{% aplayer 你离开了南京，从此没人和我说话 李志 https://m10.music.126.net/20190403173541/13770c7659f7e4db4f199753d61e1663/ymusic/534d/12e3/11d8/eb843de06316340562b81988e66f7fb8.mp3 https://p2.music.126.net/UuSe-Vc6rS7JtRJSQgDU2g==/2323268069553116.jpg?param=300x300 %}
```

{% aplayer 你离开了南京，从此没人和我说话 李志 https://m10.music.126.net/20190403173541/13770c7659f7e4db4f199753d61e1663/ymusic/534d/12e3/11d8/eb843de06316340562b81988e66f7fb8.mp3 https://p2.music.126.net/UuSe-Vc6rS7JtRJSQgDU2g==/2323268069553116.jpg?param=300x300 %}

#### hexo-pdf
[pdf传送门](https://lruihao.cn/hexo/next-pdf.html)

#### hexo-filter-flowchart(流程图)
[语法](https://flowchart.js.org)
##### install
```bash
npm install --save hexo-filter-flowchart
```

##### Usage

````
```%flow #去掉%号
st=>start: Start|past:>https://lruihao.cn[blank]
e=>end: End:>https://www.lruihao.cn[blank]
op1=>operation: My Operation|past
op2=>operation: Stuff|current
sub1=>subroutine: My Subroutine|invalid
cond=>condition: Yes
or No?|approved:>/hexo/nextplugin.html
c2=>condition: Good idea|rejected
io=>inputoutput: catch something...|request

st->op1(right)->cond
cond(yes, right)->c2
cond(no)->sub1(left)->op1
c2(yes)->io->e
c2(no)->op2->e
```
````

```flow
st=>start: Start|past:>https://lruihao.cn[blank]
e=>end: End:>https://www.lruihao.cn[blank]
op1=>operation: My Operation|past
op2=>operation: Stuff|current
sub1=>subroutine: My Subroutine|invalid
cond=>condition: Yes
or No?|approved:>/hexo/nextplugin.html
c2=>condition: Good idea|rejected
io=>inputoutput: catch something...|request

st->op1(right)->cond
cond(yes, right)->c2
cond(no)->sub1(left)->op1
c2(yes)->io->e
c2(no)->op2->e
```

#### hexo-spoiler
##### Install
```bash
npm install hexo-spoiler --save
```
> If hexo can't detect this plugin automatically, you need to modify the `plugins` section of `[path_to_your_site]/_config.yml` manually, like:

```yaml
plugins:
 - hexo-spoiler
```

##### Syntax
```plain
{% spoiler [text] %}
```
>It will pixelate your text, and click to reveal. Click again to hide your text again.
>But you need to add `<br>` manually if you want line breaks after/before it.

##### Preview
When you writes:
```plain
{% spoiler text %}
{% spoiler ~~text~~ %}
{% spoiler *text* %}
{% spoiler **text** %}<br>
{% spoiler **hello welcome to 博採眾長！** %}
```
{% spoiler text %}
{% spoiler ~~text~~ %}
{% spoiler *text* %}
{% spoiler **text** %}<br>
{% spoiler **hello welcome to 博採眾長！** %}

### 宅音乐侧栏播放器插件
[体验](https://player.lruihao.cn)
> 目前在next中可能引起部分css冲突，建议在next中使用在单个页面中。
依赖于jQuery，一行js可以引入播放器插件。

### Mermaid
[more info](https://theme-next.org/docs/tag-plugins/mermaid.html)

example
```
{% mermaid gitGraph: %}
options
{
    "nodeSpacing": 150,
    "nodeRadius": 10
}
end
commit
branch newbranch
checkout newbranch
commit
commit
checkout master
commit
commit
merge newbranch
{% endmermaid %}
```
{% mermaid gitGraph: %}
options
{
    "nodeSpacing": 150,
    "nodeRadius": 10
}
end
commit
branch newbranch
checkout newbranch
commit
commit
checkout master
commit
commit
merge newbranch
{% endmermaid %}

### video
#### Usage
```xml video.js
{% video url %}
```
#### Examples
```
{% video https://example.com/sample.mp4 %}
{% video /path/to/your/video.mp4 %}
```

### 选项卡

> "tab"为选项卡的名称，可以自定义，数字是几表示从第几个选项卡开始。非必须，若数值为-1则隐藏选项卡内容。
> [查看更多](https://almostover.ru/2016-01/hexo-theme-next-test)

```
{% tabs tab,2 %}
<!-- tab -->
this is tab1
<!-- endtab -->
<!-- tab -->
this is tab2
<!-- endtab -->
<!-- tab -->
this is tab3
<!-- endtab -->
{% endtabs %}
```
{% tabs tab,2 %}
<!-- tab -->
this is tab1
<!-- endtab -->
<!-- tab -->
this is tab2
<!-- endtab -->
<!-- tab -->
this is tab3
<!-- endtab -->
{% endtabs %}

> 数值为-1

{% tabs 选项,-1 %}
<!-- tab -->
**选项1**
<!-- endtab -->
<!-- tab -->
**选项2**
<!-- endtab -->
<!-- tab -->
**选项3**
<!-- endtab -->
{% endtabs %}

> 名字写在选项里面

```
{% tabs Fourth unique name %}
<!-- tab Solution 1 -->
**This is Tab 1.**
<!-- endtab -->
<!-- tab Solution 2 -->
**This is Tab 2.**
<!-- endtab -->
<!-- tab Solution 3 -->
**This is Tab 3.**
<!-- endtab -->
{% endtabs %}
```

{% tabs Fourth unique name %}
<!-- tab Solution 1 -->
**This is Tab 1.**
<!-- endtab -->
<!-- tab Solution 2 -->
**This is Tab 2.**
<!-- endtab -->
<!-- tab Solution 3 -->
**This is Tab 3.**
<!-- endtab -->
{% endtabs %}

### note便签

> 主题配置文件搜索note,可设置风格和图标是否显示。

```
# Note tag (bs-callout).
note:
  # Note tag style values:
  #  - simple    bs-callout old alert style. Default.
  #  - modern    bs-callout new (v2-v3) alert style.
  #  - flat      flat callout style with background, like on Mozilla or StackOverflow.
  #  - disabled  disable all CSS styles import of note tag.
  style: flat
  icons: true
  border_radius: 15
  # Offset lighter of background in % for modern and flat styles (modern: -12 | 12; flat: -18 | 6).
  # Offset also applied to label tag variables. This option can work with disabled note tag.
  light_bg_offset: 0
```
写法
```
{% note default %}default是类型还有以下几种{% endnote %}
```
{% note default %}default是类型还有以下几种{% endnote %}
{% note default %}default{% endnote %}
{% note primary %}primary{% endnote %}
{% note success %}success{% endnote %}
{% note info %}info{% endnote %}
{% note warning %}warning{% endnote %}
{% note danger %}danger{% endnote %}
{% note %}不填{% endnote %}
{% note danger no-icon %}danger no-icon{% endnote %}


### 引用(文本居中)

```
{% cq %}
**there are test words**
{% endcq %}
```

{% cq %}
**there are test words**
{% endcq %}

### [Font Awesome图标](https://www.runoob.com/font-awesome/fontawesome-tutorial.html)
> Font Awesome 是一套绝佳的图标字体库和CSS框架。
> Font Awesome 字体为您提供可缩放矢量图标,它可以被定制大小、颜色、阴影以及任何可以用CSS的样式。
> 要使用Font Awesome图标，请在HTML页面的 部分中添加以下行：

#### 1、国内推荐 CDN

```
<link rel="stylesheet" href="https://cdn.staticfile.org/font-awesome/4.7.0/css/font-awesome.css">
```
#### 2、海外推荐 CDN

```
<link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/4.7.0/css/font-awesome.min.css">
```

next已经引用了，可以直接用，比如：
```
<i class="fa fa-car"></i>
<i class="fa fa-car" style="font-size:48px;"></i>
<i class="fa fa-car" style="font-size:60px;color:red;"></i>
<i class="fa fa-car fa-lg"></i>
<i class="fa fa-car fa-2x"></i>
<i class="fa fa-car fa-3x"></i>
<i class="fa fa-car fa-4x"></i>
<i class="fa fa-car fa-5x"></i>
```
<i class="fa fa-car"></i> <i class="fa fa-car" style="font-size:48px;"></i> <i class="fa fa-car" style="font-size:60px;color:red;"></i> <i class="fa fa-car fa-lg"></i> <i class="fa fa-car fa-2x"></i> <i class="fa fa-car fa-3x"></i> <i class="fa fa-car fa-4x"></i> <i class="fa fa-car fa-5x"></i>

动态图标

```
<i class="fa fa-spinner fa-spin"></i>
<i class="fa fa-circle-o-notch fa-spin"></i>
<i class="fa fa-refresh fa-spin"></i>
<i class="fa fa-cog fa-spin"></i>
<i class="fa fa-spinner fa-pulse"></i>
```
<i class="fa fa-spinner fa-spin"></i> <i class="fa fa-circle-o-notch fa-spin"></i> <i class="fa fa-refresh fa-spin"></i> <i class="fa fa-cog fa-spin"></i> <i class="fa fa-spinner fa-pulse"></i>

### 代码块等

```cpp 三个点后面的参数 https://lruihao.cn lruihao.cn
[language] [title] [url] [link text]

code snippet

```

```diff diff
-  printf("Hello World!");
+  printf("Hello_World!");
```
**iframe**
在文章中插入 iframe。
```default iframe
{% iframe url [width] [height] %}
```
{% iframe https://weibo.com/liahao 100% 400 %}

### Todo list
- <i class="fa fa-check-square"></i> 已完成
- <i class="fa fa-square"></i> 未完成

```http Todo list
<ul>
<li><i class="fa fa-check-square"></i> 已完成</li>
<li><i class="fa fa-square"></i> 未完成</li>
</ul>

<!--或者-->

- <i class="fa fa-check-square"></i> 已完成
- <i class="fa fa-square"></i> 未完成
```

### Label
主题配置文件中打开
```
# Label tag.
label: true
```
`@`前面的是label的名字，后面的是要显示的文字
{% label default@default %} {% label primary@primary %} {% label success@success %} {% label info@info %} {% label warning@warning %} {% label danger@danger %}
```
{% label default@default %}

primary success info warning danger
```


### [其他](http://www.mykernel.cn/my-hexo-next-1.html)
> 包括小色块、左侧色条、右侧色条、上方色条、数字色块（需要自定义样式）