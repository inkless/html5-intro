# HTML5 INTRODUCTION

## What's new in HTML5
- New Elements, Attributes
- Canvas, SVG
- CSS3
- Video, Audio
- Storage
- Web Worker, File Operation
- etc.

HTML5涉及到的新的东西实在太多了，我自己本身也有很多不了解。而且我也不想讲得太泛泛，所以想寻找几个我们工作中最可能用到的来讲讲，大家共同学习

除了HTML5，CSS3，有些不算是属于HTML5但是跟工作相关的一些，也想籍此顺便讲一讲，比如*移动端开发*, *responsive design*, *ECMAScript 5*


**注意：** 这绝对不是一个完整的HTML5的介绍，有机会的话或许会慢慢补齐。
但是我发现如果完整的去学习一套理论，对谁都是一个很大的负担。我只是希望大家看过这些介绍之后，能确实有所获得，那么在以后的学习中，能带着一些思考去学习，可能效果会更好。

    我刚开始学习JavaScript的时候，看的JavaScript: the Definitive Guide。
    但是事实证明，当时选择那本书绝对是不明智的，事实上我也没能坚持看完，
    看了几十页就不看了。在做了不少的项目和一些历练之后，我回过头再去看这
    本大而全的书的时候，体会则完全不一样了。所以从我自己的角度来说，有的
    时候，我觉得像捡面包屑一样，一点一点捡一些，有所心得之后，再找一本大
    而全的权威指南看一遍，那种融会贯通的感觉肯定很爽。

移动端上，动画效果，Application Cache, viewport等
Webview上，需要研究

## I. CSS3


## II. Canvas


## III. Storage, Application Cache


## IV. File Operation & Web Worker

`new Worker`


## V. 移动端的开发
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
**竖屏**

![Alt text](http://m2.img.libdd.com/farm4/2013/0220/20/9FF8D77501969C9923D8216BD707BBB50C5E015895EBC_500_800.jpg)

**横屏**

![Alt text](http://m2.img.libdd.com/farm4/2013/0220/20/267EE7C2B1B9EB81A354336B50E09D49442F7E2266DE1_500_313.jpg)


viewport, orientation, online, apple-touch-icon 等
移动端的调试

## VI. Other Related 2  响应式设计


## VII. Other Related 3  ECMAScript 5

