# HTML5 INTRODUCTION

## What's new in HTML5
- Semantic Elements, Attributes
- Canvas, SVG
- CSS3
- Video, Audio
- Storage
- Online, Connection
- Web Worker, File Operation
- etc.

HTML5涉及到的新的东西实在太多了，我自己本身也有很多不了解。而且我也不想讲得太泛泛，所以想寻找几个我们工作中最可能用到的来讲讲，大家共同学习

考虑到目前工作上涉及移动端的内容较多，所以我也想偏重一下 *移动端开发* ，除此之外，一些已经很成熟，已经有较广泛应用的技术也会讲一讲，比如 *Storage*, *CSS3*


**注意：** 这绝对不是一个完整的HTML5的介绍，有机会的话或许会慢慢补齐。
其实如果完整的去学习一套理论，对谁都是一个很大的负担。我只是希望大家看过这些介绍之后，能确实有所获得，那么在以后的学习中，能带着一些思考去学习，可能效果会更好。

    我刚开始学习JavaScript的时候，看的JavaScript: the Definitive Guide。
    但是事实证明，当时选择那本书绝对是不明智的，事实上我也没能坚持看完，
    看了几十页就不看了。在做了不少的项目和一些历练之后，我回过头再去看这
    本大而全的书的时候，体会则完全不一样了，会有一种融会贯通的感觉。

## I. 移动端的开发
### Viewport

一个典型的优化过的移动端站点通常含有这样的一个属性：

```html
<meta name="viewport" content="width=device-width, initial-scale=1, maximum-scale=1">
```
    
Viewport的属性共有7种：

1. **width** = [ 像素值 | device-width ]
2. **height** = [ 像素值 | device-height ]
3. **initial-scale** = Float Number(如 1.0 / 1 / 0.5)
4. **minimum-scale** = Float Number(如 1.0 / 1 / 0.5)
5. **maximum-scale** = Float Number(如 1.0 / 1 / 0.5)
6. **user-scalable** = [ yes | no ]
7. **target-densitydpi** = [ DPI值 | device-dpi| high-dpi | medium-dpi | low-dpi ]

#### viewport.width
***设置网页可视区域的宽度***

##### 设置 width=device-width

```html
<meta name="viewport" content="width=device-width, initial-scale=1, maximum-scale=1">
```

**竖屏**

![Alt text](http://m2.img.libdd.com/farm4/2013/0220/20/9FF8D77501969C9923D8216BD707BBB50C5E015895EBC_500_800.jpg)

**横屏**

![Alt text](http://m2.img.libdd.com/farm4/2013/0220/20/267EE7C2B1B9EB81A354336B50E09D49442F7E2266DE1_500_313.jpg)

##### 设置 width=320

```html
<meta name="viewport" content="width=320">
```
注: 我的经验中，设置了固定的width以后，scale相关属性一般不生效

**竖屏**

![Alt text](http://m1.img.libdd.com/farm4/2013/0220/20/09C2E15DF71C7DFD35CD3BA045996DF6CBBDC13D15E0C_250_400.jpg)

**横屏**

![Alt text](http://m1.img.libdd.com/farm5/2013/0220/20/8CEFCEC4E346906565D143E940FDD97AC27920920B1BA_500_313.jpg)

#### 设置 sacle
* **initial-scale** = Float Number(如 1.0 / 1 / 0.5)
* **minimum-scale** = Float Number(如 1.0 / 1 / 0.5)
* **maximum-scale** = Float Number(如 1.0 / 1 / 0.5)
* **user-scalable** = [ yes | no ]

#### 设置DPI
##### CSS pixel与device pixel
* **CSS pixel**： 浏览器使用的抽象单位， 主要用来在网页上绘制内容。
* **device pixel**： 显示屏幕的的最小物理单位，每个dp包含自己的颜色、亮度。

每个CSS pixel所含有的device pixel不是固定的，一般来说

    1 CSS pixel = devicePixelRatio^2 个device pixel

##### PPI/DPI
PPI，有时也叫DPI，所表示的是每英寸所拥有的像素（pixel）数目，数值越高，即代表显示屏能够以越高的密度显示图像。

**注：**这里的像素，指的是device pixels。

PPI准确的计算公式：

![](http://m2.img.libdd.com/farm4/2013/0220/21/BFA4B3989F54DD003418E3CFF9B23677E5E7703F62222_250_155.jpg)

常见的一些屏幕尺寸和对应的 DPI

![](http://m1.img.libdd.com/farm5/2013/0220/21/970E5D7327BE2E522E556C4787C63944EB1A1D292D92F_640_426.JPEG)

实际设置了target-densitydpi之后的页面:

```html
<meta name="viewport" content="target-densitydpi=device-dpi,width=device-width,initial-scale=1,maximum-scale=1">
```

![](http://m2.img.libdd.com/farm5/2013/0220/21/88C52C0E0F08D71BF4EBEEA0F4100E7AB13D0E6ECB72B_250_400.jpg)

##### 通过Media Query实现不同屏幕加载不同的CSS

```css
.header {
background:url (medium-density-image.png);
}
@media screen and (-webkit-device-pixel-ratio:2.0) {
/* CSS for retina-density screens */
.header { background:url (retina-density-image.png);}
}
@media screen and (-webkit-min-device-pixel-ratio:1.5) and (-webkit-max-device-pixel-ratio:1.99){
/* CSS for high-density screens */
.header { background:url (high-density-image.png);}
}
@media screen and (-webkit-max-device-pixel-ratio:0.75) {
/* CSS for low-density screens */
.header { background:url (low-density-image.png);}
}
```

* **注1：使用了target-densitydpi属性以后，所有的Media Query的数值会产生改变**
* **注2：更多的 Media Query 稍后再详细介绍**
* **注3：其实对于图片的处理，已经有更为优美的解决方案--响应式图片**

### Orientation
移动端用户有的时候会开启自动旋转，需要考虑旋转之后的布局等安排
一般说来，处理的方式有两种：

* JavaScript
* Media Query

#### JavaScript
可以通过JavaScript来监控屏幕转动

```javascript
window.onorientationchange = function() { /*Do Something*/ };
// 或者使用jQuery
$(window).on("orientationchange", function() { /*Do Something*/ });
```

同时，还有一个属性: ***window.orientation*** 表明当前旋转的角度（逆时针方向）
0/90/-90/180

#### Media Query
如果仅仅是跟布局相关的，通过Media Query或许是最好的选择

```css
@media (orientation: portrait) {
/* Some CSS for portrait */
}
@media (orientation: landscape) {
/* Some CSS for landscape */
}
```

其实很多时候使用Media Query，很多时候也不需要考虑是横向还是纵向。
只需要针对宽度做适配即可：

```css
@media screen and (max-width: 479px) {
/* Some CSS for Width < 480 */
.desc { background: yellow; }
}
@media screen and (min-width: 480px) and (max-width: 639px) {
/* Some CSS for 480 <= Width < 640 */
.desc { background: blue; }
}
@media screen and (min-width: 640px) and (max-width: 1023px) {
/* Some CSS for 640 <= Width < 1024 */
.desc { background: green; }
}
@media screen and (min-width: 1024px) {
/* Some CSS for Width >= 1024 */
.desc { background: red; }
}
```

##### 查看应用了以上CSS之后的效果
移动设备竖屏，宽高比400x519

![](http://m3.img.libdd.com/farm4/2013/0221/13/76C11A965272F8CF10397A419526AFCA9798BB957EDDD_250_400.jpg)

移动设备横屏，宽高比640x327

![](http://m1.img.libdd.com/farm5/2013/0221/13/25E4FF80684612516CA99152818AB1EBA5A5EEF99E75E_250_156.jpg)

电脑，宽高比1275x783

![](http://m2.img.libdd.com/farm5/2013/0221/13/C5A0C4FF20252429694AF7D72DE59AEAB1BAD0B5C04CD_250_172.jpg)

当然这样写显得比较拥挤，不太好维护，还有一种更为友好的做法：

```html
<link rel="stylesheet" media="only screen and (max-device-width:360px)" href="mobile360.css" type="text/css" />
<link rel="stylesheet" media="only screen and (min-device-width:361px) and (max-device-width:480px)" href="mobile480.css" type="text/css" />
<link rel="stylesheet" media="only screen and (min-device-width:481px)" href="mobileHuge.css" type="text/css" />
```

* 注：这里是 **min-device-width**，不是 **min-width**。

#### 简单的Retina屏幕优化方案
前文中讲到通过 **target-densitydpi** 改变 devicePixelRatio 来优化retina屏幕显示。
但是实际操作中，这样会非常吃力。

实际上，目前也没有一个权威的并且成熟的解决方案。（我还没找到）
各种方案也是百花齐放，我这里只介绍一种我自己的解决方案（绝对不是最好的方案），
有兴趣的同学可以多些了解关于 **响应式图片** 相关的内容。

##### 背景图片

```css
.header { background-image:url(http://path/of/pic/normal.png);
/* 普通屏幕 */ 
/* ------------ Retina ------------ */ 
@media only screen and (-o-min-device-pixel-ratio: 2/1), /* Opera */ 
    only screen and (min--moz-device-pixel-ratio: 2), /* Firefox 16 之前 */ 
    only screen and (-webkit-min-device-pixel-ratio: 2), /* Webkit */ 
    only screen and (min-resolution: 240dpi), /* 标准 */ 
    only screen and (min-resolution: 2dppx) /* 标准 */ {
    .header {
        background-image:url(http://path/of/pic/large.png); 
        background-size: 50% 50%; /* will be introduced later */
    }
}
```

##### 图片 img

```html
    <img data-src="http://path/of/pic/normal.png" data-src-2x="http://path/of/pic/large.png" width="400px" height="300px"/>
    <script type="text/javascript">
        $('img[data-src-2x]').each(function() {
            if (window.devicePixelRatio === 2) {
                // this.src = this.dataset.src2x;
                this.src = $(this).attr("data-src-2x");
            }else {
                // this.src = this.dataset.src;
                this.src = $(this).attr("data-src");
            }
        });
    </script>
```

### Online & Connection
#### navigator.onLine
如果需要判断当前手机是否联网，其实很简单。。。

通过 JavaScript 判断 **navigator.onLine**
返回值 true/false

同时还有两个 JavaScript的Events:
**ononline**, **onoffline**

#### navigator.connection

##### Android 2.2+ 以后的内置Webkit中：

```json
navigator.connection = {
    "type": "4",
    "UNKNOWN": "0",
    "ETHERNET": "1",
    "WIFI": "2",
    "CELL_2G": "3",
    "CELL_3G": "4"
}
```

我们可以写出类似于这样的代码：

```javascript
if (navigator.onLine) {
    var connection =    navigator.connection ||
                        navigator.webkitConnection ||
                        navigator.mozConnection ||
                        {type: 0};
    switch(connection.type) {
        case connection.CELL_3G: // 3G
            connectionSpeed = 'mediumbandwidth';
            break;
        case connection.CELL_2G: // 2G
            connectionSpeed = 'lowbandwidth';
            break;
        default: // WIFI, ETHERNET, UNKNOWN
            connectionSpeed = 'highbandwidth';
            break;
    }
}
```

**注：ECMAScript 5中有不同的定义，而且在目前的手机Chrome上无效果**

### Semantics
新的元素，含有语意的元素等
#### Form

```html
<style>
  [required] {
    border-color: #88a;
    -webkit-box-shadow: 0 0 3px rgba(0, 0, 255, .5);
  }
  :invalid {
    border-color: #e88;
    -webkit-box-shadow: 0 0 5px rgba(255, 0, 0, .8);
  }
</style>
<input type="text" required />
<input type="email" value="zhang.gd@foxmail.com" />
<input type="date" min="1988-01-01" max="2013-12-12" value="2013-02-22"/>
<input type="range" min="0" max="50" value="10" />
<input type="search" results="10" placeholder="搜索..." />
<input type="tel"  placeholder="(021) 2222-8888" pattern="^\(?\d{3}\)?[-\s]\d{4}[-\s]\d{4}.*?$" />
<input type="color" placeholder="e.g. #bbbbbb" />
<input type="number" step="1" min="-5" max="10" value="0" />
```

<style>
  [required] {
    border-color: #88a;
    -webkit-box-shadow: 0 0 3px rgba(0, 0, 255, .5);
  }
  :invalid {
    border-color: #e88;
    -webkit-box-shadow: 0 0 5px rgba(255, 0, 0, .8);
  }
  .intro_form {

  }
</style>

<div class="intro_form">
	<input type="text" required />
	<input type="email" value="zhang.gd@foxmail.com" />
	<input type="date" min="1988-01-01" max="2013-12-12" value="2013-02-22"/>
	<input type="range" min="0" max="50" value="10" />
	<input type="search" results="10" placeholder="搜索..." />
	<input type="tel"  placeholder="(021) 2222-8888" pattern="^\(?\d{3}\)?[-\s]\d{4}[-\s]\d{4}.*?$" />
	<input type="color" placeholder="e.g. #bbbbbb" />
	<input type="number" step="1" min="-5" max="10" value="0" />
</div>



#### Progress & Meter
#### dataset
#### datalist

### 移动端调试


## II. CSS3
<http://www.css3maker.com/>
<http://cssdeck.com/>
### Border

### Radiant

### Shadow

### Background

### Transform

### Transition

### Animation

### Media Query

## III. Application Cache, Storage
### Application Cache
<http://everytimezone.com/>
### localstorage
### WebSQL
### IndexedDB

## IV. Canvas

## V. File Operation, Web Worker & Web Socket

`new Worker`

## VI. Other Related 2  Responsive Design


## VII. Other Related 3  ECMAScript 5

