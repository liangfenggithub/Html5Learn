# html5
## 1. 什么是html5

### 简介
1. HTML5 将成为HTML XHTML HTML DOM的新标准
2. HTML5是针对目前web发展对原有HTML的补充和升级、并不是颠覆
3. 将元素语义和元素内容呈现的影响分开，如取出font标签，添加article
4. 使用标签完全从标签的语义触发，而不是表现形态

### 新特点
1. HTML的一些有趣的新特性
2. 用于绘画的canvas元素
3. 用于媒介回放的video和audio元素
4. 对本地离线存储更好的支持
5. 新的特殊内容元素，比如article、footer、header、nav、section、
6. 新的表单控件，比如calender、date、time、email、url、search、

### 浏览器支持
最新版本的Safari、Chrome、FireFox以及Opera支持某些HTML5特性，IE9支持某些特性

### 优势
1. 提高可用性和改进用户体验
2. 有几个新标签，有足浴开发人员定义重要内容
3. 可以给站点带来更多的多媒体元素（视频和音频）
4. 可以很好的替代FLASH和Silverlight
5. 当设计网站抓取和索引是对SEO很友好
6. 将被大量应用于移动移动程序和游戏

### HTML5主要包括内容
1. WebStorage：比cookie更大、更有弹性的存储
2. Web SQL Datebase：本地端的SQL数据库
3. indexed DB: Key-Value的本地数据库
4. Application Cache: 将部分常用网页Cache起来，如移动端的首页
5. WebSocket： 实时的socket联机
6. Web Workers：以往JavaScript都是单线程，通过Worker可以有多线程。
7. Notifications: 原生的提示讯息
8. Dragn Drop：HTML元素的拖拉
9. File API: 读取用户本机计算机的内容。
10. Geolocation：地理定位
11. Device orientation: 手持装置的方向。
12. Speech input：语音输入
13. New Tags: 新标签，如header、section
14. Applicaiton tags：也是新标签，如meter progeress
15. Microdate： 将入语义的数据让搜索引擎等网站正确显示
16. Form type：表单可以加入的type更多了，包含email等
17. Audio video：音视频的原生播放支持
18. Canvas的绘图支持功能
19. CSS3技术

## 2. 标签新变化
DOCTYPE:
	<!DOCTYPE html>
meta设置编码:
	<meta charset = "utf-8">
link标签
	<link rel = "stylesheet" src= "haaad.css"/>
script标签
	<script>...</script>

### 新属性
1. contenteditable  使内容可编辑
2. hidden  使内容隐藏

直接在标签内部写属性名即可，也可写“属性名=‘true’”，实现功能相同

## 3. web语义化
在html4以div来定义的头部、导航条等区块，html5以新的有固定含义的标签直接指定，如header、nav、footer等，方便浏览器和搜索引擎更精准的识别编写的网页。
### 新增的语义化标签
1. header
2. nav 导航
3. article 文章
4. aside  侧边栏
5. footer
6. section 表示文章章节
7. time 时间
8. address 地址
9. code  代码
10. mark 标记页面中重要的部分
11. ins 给元素加下划线 相当于html4中的u标签
12. del 给元素加删除线
13. progress 进度条，但是在不同浏览器样式不一致，还不如自己用div写

### 表单新增type类型有：
1. email 必须符合邮箱格式: asdfs@qq.com，否则提交不了
2. url  必须符合网址格式: http://www.baidu.com，同上
3. number  可以在页面中通过上下箭头调整数字，可指定 min、max、step（调整的步长）、value等属性
4. range 滑块，可指定 min、max、step（调整的步长）、value等属性
5. date 日期类，点击后提供日期选择器选择框，但是兼容性不太好，因此都用第三方
6. color  颜色，点击后弹出颜色选择器，选择什么颜色，表单值就是颜色值，同样兼容性不太好

### 表单新特性
1. select 中新增了optgroup标签，用于给待选项分组
2. datalist 单行文本的自定义列表，注意：input中的list的值对应datalist中id的值，两者才能绑定
3. autofocus 自动聚焦表单
4. 提交form以外的表单（html4中只能提交html4中的表单）：在form外的表单指定form属性，对应提交form的id值就能实现。
5. 文件上传 以往html4中input的type=file文件上传只能上传一个，当加入新属性“multiple”可同时长传多个
6. placeholder 文本框默认提醒，与value相比是光标聚焦时自动删除
7. pattern 表单验证 直接在标签内写正则表达式验证输入
8. required 表单不能为空

### 多媒体标签
1.autdio 标签插入音乐 control属性显示控制框 autoplay自动播放 loop指定播放次数（只写loop就是反复播放）
2. video 标签插入视频，支持MP4、ogg、webm格式的视频文件、control属性显示控制框 autoplay自动播放 loop指定播放次数（只写loop就是反复播放）、poster是视频封面
controls 对于不同浏览器样式不一致，因此一般自定义控制视频播放的样式，这就用到了下边的多媒体API

### 多媒体API
以视频为例video介绍，audio类同
1. play() 播放视频
2. pause() 暂停播放
3. currentTime 属性是当前播放时间，为其赋值是跳转到指定的时间
4. muted 属性是是否静音，true为静音，false为不静音 
5. volume 属性是音量，范围是0-1

## 4. 本地存储
类似于之前的cookie，例如在京东中不同页面将不同商品加入购物车，那么在结算页面就能看到所有购物车内的商品，而加入购物车这动作是没有和后台交互的（也许有），应该就是利用了html的本地存储功能，本地存储主要有两种。

1. sessionStorage 临时存储
2. localStorage  永久存储

**注意**
*. sessionStorage 存储的数据在浏览器关闭后就清理掉
*. sessionStorage 写入数据的页面和获得数据的页面要在**同一个浏览器标签**中打开才可以。

*. localStorage存储的数据，多标签存储数据,即使不在一个标签打开也能获得。
*. localStorage存储的是永久数据，如果不清理浏览器缓存，无论在什么时候打开，数据都存在。

### 方法
对于localStorage和sessionStorage的操作方法都相同，如下：

1. setItem("key","value") 写入数据
2. getItem("key","value") 读出数据
3. clear();  清除所有数据
4. length  属性，获得所有数据长度


### 本地存储的特点
1. 容量大，5M-10M,目前形势就5M的考虑笔记稳妥。
2. 不会随回话来传输。
3. 接口丰富，读取和写入方便。

## 5. Canvas绘制图形
### 简介

	<canvas>标签定义图形，比如图标和其他图像。
	<canvas>标签**只是图形容器**，我必须用脚本来绘制图形
	canvas其实对于HTML来说很简单，只是一个标签元素，自己没有行为，但却把一个绘图API展现给客户端Javascript以使脚本能够把想要绘制的东西都绘制到一块画布上，拥有绘制路径、矩形、圆、字符以及图像等功能，所有的标签都是图形的容器，必须使用JavaScript的API来操作绘图

### 标签
```html
<canvas id="canvas" width="500" height="500"></canvas>
```

注意：画板canvas 的宽高不要用css来定义

### 绘制矩形API

1. getContext("2d")  返回一个用于画布上2d绘图的环境
2. fillStyle属性，设置填充颜色
3. fillRect(100,100,500,300); 绘制实心矩形，参数分别是，距离左边，距离右边，宽度，高度
4. strokeStyle 属性，设置描边颜色
5. lineWidth 属性，设置描边宽度
6. strokeRect(300,200,400,260); 参数同rillRect
7. clearRect(220,170,200,160); 清理画布内容，参数通rillRect

### 绘制路径API

路径是两个点之间的轨迹

1. beginPath(); 开启路径
2. moveTo(30,30); 指定起点路径，参数分别是，距离左边，距离右边，下同。
3. lineTo(200,30); 指定下一点，canvas是确定路径的点，在进行绘制
4. closePath(); 关闭路径，将最后一点和第一点连接，形成一个封闭空间。
5. lineJoin(); 指定圆角类型
6. stroke(); 绘制路径


### canvas实现绘图画板
基础思路：鼠标按下时，获得鼠标相对于画板的位置，设为起点；设置鼠标移动事件，每次进入移动时间后，获得新的鼠标位置，作为终点，进行鼠标绘制。直到抬起鼠标，取消鼠标移动事件。


### 画布控制

1. scale(x,y)  画布缩放，x是横向缩放倍数，y是竖向缩放倍数
2. translate(x,y)  画布平移， x是向右平移，y是向下平移，当xy为负数时，方向相反。
3. rotate(x)  旋转 x是旋转弧度，角度360度=2π, 弧度转换函数为:弧度 = 角度*(Math.PI/180) 
**注意**
1. 假设画布是一个长方形，旋转画布以后只是让画布上的图形进行了旋转，画布仍然保持横平竖直的长方形。
2. 假设有两次旋转，第一次旋转10度，第二次旋转30度，那么第二次旋转的结果就是相对于原位置的40度。


### 绘制圆弧

1. arc(距离左边，距离上边，半径，起始弧度，终止弧度[, 弧度方向])  绘制圆弧，注意角度是以弧度来表示的，转换方式如上。弧度方向默认为false为顺时针，如果为true，那么为逆时针。

### 绘制扇形
扇形绘制是利用路径和圆弧想配合实现的，先设置路径起点到圆心，再画圆弧，最后闭合路径，填充实现扇形。


### 绘制饼状图
饼状图其实就是在一个圆形上画不同的扇形，凑满360度就可以了。

### 绘制文字
相关API

1. context.font="40px 黑体"  设置字体属性
2. context.textAlign = "left|right|center"
3. context.fillText(文字,x,y,maxWidth); 在画布上绘制实心文本
4. context.strokeText(文字,x,y,maxWidth); 在画布上绘制空心文本
5. context.textBaseLine = "top|middle|bottom"  设置文字基线
6. context.measureText(文字)  获得文本宽度。

### 绘制验证码
绘制验证码步骤如下：
1. 先固定canvas宽高为200px,50px
2. 写for循环写入4个随机字母
3. 在for循环内给4个随机字母加上随机的位置
4. 在for循环中给4个随机字母加上随机颜色
5. 给4个随机字母加上随机干扰线条颜色

### canvas绘制图片
将图片加入canvas中先得保证图片被引入到html中，同时得等图片加载完成。
1. context.drawImage("图像资源",x,y[,宽度,高度])  宽度高度指放入canvas后的宽高
2. drawImage("图像资源",裁切开始x位置，裁切开始y位置，宽，高，放置到x位置，放置到y位置,放置后款，放置后高)

### canvas自定义填充

API
cv.createPattern(pic,"repeat|repeat-x|repeat-y|no-repeat");

### canvas 读取和写入图像

API

1. context.getImageData(位置开始x，位置开始y，宽度，高度)
2. context.putImageData(图像,位置开始x，位置开始y)

没实现出来。。。。。