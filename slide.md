# HTML5 INTRODUCTION

***

## What's new in HTML5
- New Elements, Attributes
- Canvas, SVG
- CSS3
- Video, Audio
- Storage
- Web Worker, File Operation
- etc.

<!--
  这些是啥来的，其实有人知道么
-->

***

HTML5涉及到的新的东西实在太多了，我自己本身也有很多不了解。而且我也不想讲得太泛泛，所以想寻找几个我们工作中最可能用到的来讲讲，大家共同学习

除了HTML5，CSS3，有些不算是属于HTML5但是跟工作相关的一些，也想籍此顺便讲一讲，比如*移动端开发*, *responsive design*, *ECMAScript 5*

***

**注意：** 这绝对不是一个完整的HTML5的介绍，有机会的话或许会慢慢补齐。
但是我发现如果完整的去学习一套理论，对谁都是一个很大的负担。我只是希望大家看过这些介绍之后，能确实有所获得，那么在以后的学习中，能带着一些思考去学习，可能效果会更好。

    我刚开始学习JavaScript的时候，看的JavaScript: the Definitive Guide。
    但是事实证明，当时选择那本书绝对是不明智的，事实上我也没能坚持看完，
    看了几十页就不看了。在做了不少的项目和一些历练之后，我回过头再去看这
    本大而全的书的时候，体会则完全不一样了。所以从我自己的角度来说，有的
    时候，我觉得像捡面包屑一样，一点一点捡一些，有所心得之后，再找一本大
    而全的权威指南看一遍，那种融会贯通的感觉肯定很爽。

***

## I. CSS3
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

***

## II. Canvas

***

## III. Storage, Application Cache

***

## IV. File Operation & Web Worker

`new Worker`

***

## V. 移动端的开发
viewport, orientation, online, apple-touch-icon 等
移动端的调试

***

## VI. Other Related 2  响应式设计

***

## VII. Other Related 3  ECMAScript 5

***
