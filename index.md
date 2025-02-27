魔改雀魂
=============

> 目前魔改可以在PC+安卓运行。有疑问可以联系我 QQ252373009
> 魔改在IOS失效，但我找到的新方法，但是實現非常麻煩
> 【更新方法】在【导入导出】再次下载规则覆盖即可
> 【2019-08-21】[另一个魔改方法，全平台适用](https://mj.000.mk/#modify_majsoul.md)  
> 【2019-08-21】完全支持日服和国际服，重新导入规则即可  
> 【2019-08-18】雀魂更换了网址，请把规则再次导入一次，见→【二、插件导入规则】  
> 【更新！！】添加了[在线合成雀魂背景图的小程序](makebg.htm)
> 【更新！！】添加了[雀魂图片在线加密解密](imgxor.htm)
> 
> 魔改完有时一些元素没有显示->刷新
> 魔改完清理一下浏览器缓存

> 所有步骤用一句话概括：装插件+设置规则

> 本页介绍的是PC端+安卓魔改的方法，ios见↓

[iOS魔改方法（失效）](ios.md)

[gimmick:TwitterFollow](@lietxia)

[gimmick:ForkMeOnGitHub](https://github.com/lietxia/lietxia.github.io)
----------
# 2018-08-21更新
* [另一个魔改方法，全平台适用](https://mj.000.mk/#modify_majsoul.md)
* 完全支持日服和国际服，重新导入规则即可

如果你要魔改加密的图片：
1. 找到真实地址
2. 把图片上传图床,比如 https://sm.ms
3. 图片地址前加上一个前缀`https://xor.lietxia.workers.dev/?`

比如新建一个规则，改一姬全身像的，你修改后的立绘网址是 https://mj2.000.mk/res/full_test.png

匹配规则写：

    ^https?://(majsoul\.union-game\.com/0|(www\.)?majsoul.com/1|game\.mahjongsoul\.com|mahjongsoul\.game\.yo-star\.com)/[^/]+/extendRes/charactor/yiji/full.png

重定向至：

    https://xor.lietxia.workers.dev/?https://mj2.000.mk/res/full_test.png

一些立绘的其他知识见我另一个帖子的立绘部分（2个方法的正则不同，要注意）  
https://mj.000.mk/#modify_majsoul.md
-----

# 效果
![](img/050.png)


# Chrome系浏览器装插件
> 这个插件有Chrome版，可以在360极速浏览器、360安全浏览器、QQ浏览器等基于chromium的浏览器上安装
> 但由于chrome插件商店被墙，安装插件比较麻烦
> 所以推荐使用firefox，Firefox的安卓版一样可以装插件进行魔改，步骤相同
> 移步-> [Chrome系浏览器装插件](chrome.md)【新】插件更新4.0.4

## 一、Firefox装插件方法
firefox打开  
[https://addons.mozilla.org/zh-CN/firefox/addon/header-editor/](https://addons.mozilla.org/zh-CN/firefox/addon/header-editor/)

点击【添加到 Firefox】，再点【添加】即可

## 二、插件导入规则

> 各浏览器使用本插件方法完全相同，安卓也相同。


![](img/051.png)

※如果你要执行【再导入一次规则】导入之前，如果背景图DIY过，把你DIY的背景网址记下，再做规则覆盖

1. 打开插件
2. 选【导入和导出】
3. 在【下载规则】填 `https://lietxia.github.io/res/header_editor_rules.json`
4. 点【↓】导入规则
5. 页面翻到最下方，点【保存】

※ 这个规则你以后还能在这里更新，也许将来我会加一些新的样式

## 三、规则使用
![](img/052.png)

1. 【规则列表】点击【↓】展开列表
2. 选择要用的规则

> 【注意】同一类别的魔改规则只能开1项，不要多开。


## 四、修改牌桌
如果你要改背景，打开插件，编辑第5个规则【雀魂-修改背景】
把【重定向至】改成你要改的网址

以下方法已过时，新方法:[在线合成背景图的小程序](makebg.htm)

~~牌桌原图是正方形，他会自动拉伸，直接换图片不带边框  
如果想要边框，可以下载我的photoshop文档：  
[https://lietxia.github.io/res/bg.psd](https://lietxia.github.io/res/bg.psd)

然后传到一个【可以外链的图床】推荐图床[https://sm.ms](https://sm.ms)

把网址换成你所需的即可~~

![](img/053.png)

替换图中下方圈起来的部分

## （插件说明）更加自由的DIY

> 魔改教程到上面就结束了，不过如果你想更自由的DIY，就从这里看下去（会有些复杂）
> 我DIY所有的素材，牌背啥的psd，牌矢量图等等全在 [这个github](https://github.com/lietxia/lietxia.github.io)  

![](img/054.png)

一个简单的修改。
按F12打开控制台，刷新雀魂，然后打开【network】，他会展示出所有的资源，这里我们可以只看img（图片）的部分  

复制它的URI，在这个插件里添加一个规则

![](img/055.png)

下面是一个例子，比如我要改雀魂的背景图
【名称】`主页面背景`  
【规则类型】选【重定向请求】  
【匹配类型】选【网址】  
【匹配规则】`http://www.majsoul.com/0/v0.3.47.w/scene/Assets/Resource/lobby/yard.jpg`  
【执行类型】选【常规】  
【重定向至】`https://i.loli.net/2018/09/17/5b9fa1582c181.jpg`

![](img/056.png)

这样一个简单的魔改就完成了

但这样有个小问题，雀魂只要版本一更新，`majsoul.com/0/` 后面的`v0.3.47.w` 就要变一次，我们一次一次的改比较麻烦。所以要用【正则表达式】 [百度百科【正则表达式】](https://baike.baidu.com/item/%E6%AD%A3%E5%88%99%E8%A1%A8%E8%BE%BE%E5%BC%8F/1700215) 来建立一个动态的规则。太细的也不说了，总之：
`http://www.majsoul.com/0/v0.3.47.w/scene/Assets/Resource/lobby/yard.jpg` 的  

    http://www.majsoul.com/0/v0.3.47.w
    部分，换成
    ^http(s?)://(www\.)?majsoul\.com/0/[^/]+

之后从`/xxx/xx/xxx`开始（不要漏掉斜杠）,就变成↓   
`^http(s?)://(www\.)?majsoul\.com/0/[^/]+/scene/Assets/Resource/lobby/yard.jpg`

![](img/057.png)

正则里被()包住的部分，【重定向至】可以用$1，$2，来代替（$1表示第一个被圆括号包住的字符串,$2是第二个）

更复杂的魔改需要一些JavaScript知识，要想像我这样一行规则就能换3处地方，需要自己有带目录的图床（我是丢GitHub，然后用GitHub的pages功能得到一个xxx.github.io的地址，可以自定义目录）

不太会的可以多写几行规则= =

## DIY里的一些坑

第一个坑:雀魂有部分图片是加密过的，这部分资源无法修改。

就是类似`blob:http://www.majsoul.com/6e9850f2-115d-4ae6-a612-b4e9dac2472d`

这样的图片，多为立绘。

原因：图片经过加密，你要用跟他同样的方法加密一次，再解密才正常显示。 你传正常图片经过程序解密图片会乱。你不知道他是怎么加密的所以无法修改。

第二个坑:牌背花纹

![](dir/rose/scene/Assets/Resource/mjpai/1s.png)

牌背素材是在右上角的部分，牌背的部分很小，就算改了牌背也很模糊  
可喜的是，你可以等比放大（我就放大了400%）程序会自动缩小，这样牌背会有很高的分辨率，不会糊了  
可悲的是，他缩放机制很垃圾。总之你要像我下面一样做一个浆糊放大图片【两次立方（平滑渐变）】。不然效果很惨

![](img/058.png)

