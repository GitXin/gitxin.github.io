---
layout: post
title:  "css Learning"
date:   2016-01-15 10:46:23 +0800
categories: learning 
---

## CSS

### 动画

> [慕课网地址：http://www.imooc.com/video/6041](http://www.imooc.com/video/6041)

  * 命令式 jquery  
动画状态与应用状态混杂在一起  
逻辑复杂，后期不易维护，容易导致bug
  * 声明式 CSS Angular Vue.js  
将应用状态和动画分离，易于维护
  * Javascript animations  
通过逐帧计算并设置 css property 来模拟动画 优点：可以进行更精确的控制：时间轴，缓动曲线，物理模拟，增量动画 缺点：需要在 js 主线程进行大量计算（ js 是单线程），通常伴随命令式的 api
  * CSS Transitions/animations  
通过 css class/property 的变更来触发动画  
通常伴随着声明式的 api  
优点：对 js 主线程的计算消耗小，会放在浏览器的某个单独线程中进行计算  
缺点：通常伴随着声明式的 api，受限制于 cubic－bezier 曲线或是 keyframes，受限制于固定状态之间的切换，无法处理增量动画

### CSS3

> [慕课网地址：http://www.imooc.com/learn/33](http://www.imooc.com/learn/33)

  * 不同浏览器的前缀  
在编写CSS3样式时，不同的浏览器可能需要不同的前缀。它表示该CSS属性或规则尚未成为W3C标准的一部分，是浏览器的私有属性，虽然目前较新版本的浏览器都是不需要前缀的，但为了更好的向前兼容前缀还是少不了的。
<table style="border-collapse: collapse; border-spacing: 0; margin: 1em;">

<thead>
<tr>
<th style="border: 1px solid #DDD; padding: 6px 13px;"><em>前缀</em></th>
<th style="border: 1px solid #DDD; padding: 6px 13px;"><em>浏览器</em></th>
</tr>
</thead>
<tr style="border: 1px solid #DDD; padding: 6px 13px;">
<td style="border: 1px solid #DDD; padding: 6px 13px;">-webkit</td>
<td style="border: 1px solid #DDD; padding: 6px 13px;">chrome 
& safari</td>
</tr>
<tr style="border: 1px solid #DDD; padding: 6px 13px; background-color: #F8F8F8;">
<td style="border: 1px solid #DDD; padding: 6px 13px;">-moz</td>
<td style="border: 1px solid #DDD; padding: 6px 13px;">firefox</td>
</tr>
<tr style="border: 1px solid #DDD; padding: 6px 13px;">
<td style="border: 1px solid #DDD; padding: 6px 13px;">-ms</td>
<td style="border: 1px solid #DDD; padding: 6px 13px;">IE</td>
</tr>
<tr style="border: 1px solid #DDD; padding: 6px 13px; background-color: #F8F8F8;">
<td style="border: 1px solid #DDD; padding: 6px 13px;">-o</td>
<td style="border: 1px solid #DDD; padding: 6px 13px;">opera</td>
</tr>

</table>


```css
  transform-style: preserve-3d;
  -moz-transform-style: preserve-3d;
  -webkit-transform-style: preserve-3d;
  -ms-transform-style: preserve-3d;
  -0-transform-style: preserve-3d;
```


  * 为某个标签定义 class


```css 
  div.circle{
    height: 100px;
    width: 100px;
    background: #9da;
    border-radius: 50px 50px 0 0; <!-- 分别为 左上 右上 右下 左下（顺时针）-->
  }
  <div class="circle"></div> <!--会显示圆-->
  <span class="circle"></span> <!--不会显示圆-->
```

  * box-shadow

> box-shadow: X轴偏移量 Y轴偏移量 阴影模糊半径 阴影扩展半径 颜色 投影方式(inset，默认为外阴影)

box-shadow: 5px 5px 5px 5px white, 5px 5px 5px 5px black inset;（多投影用逗号隔开）

  * RGBA(Alpha)

> background-color: rgba(255, 255, 255, 0.5);

### CSS 基础

> [慕课网地址：http://www.imooc.com/learn/9](http://www.imooc.com/learn/9)

  * CSS 三种方法  
内联式  
嵌入式  
外部式  
优先级：声明的就近原则
  * 选择器  
类和 id 选择器不同：id 选择器智能在文档中使用一次，id选择器不能像类选择器那样为一个元素同时设置多个样式
  * 子选择器

```css
  .food>li{border:1px solid red;}
  // 这行代码会使class名为food下的子元素li（水果、蔬菜）加入红色实线边框。
```

  * 包容（后代）选择器

> 包含选择器，即加入空格,用于选择指定标签元素下的后辈元素。如右侧代码编辑器中的代码：

```css
  .first  span{color:red;}
```

  * 通用选择器

> 通用选择器是功能最强大的选择器，它使用一个（*）号指定，它的作用是匹配html中所有标签元素，如下使用下面代码使用html中任意标签元素字体颜色全部设置为红色：

```css
  * {color:red;}
```

  * 伪类选择器

> 它允许给html不存在的标签（标签的某种状态）设置样式，比如说我们给html中一个标签元素的鼠标滑过的状态来设置字体颜色：

```css
  a:hover{color:red;}
```

  * 分组选择符

> 当你想为html中多个标签元素设置同一个样式时，可以使用分组选择符（，），如下代码为右侧代码编辑器中的h1、span标签同时设置字体颜色为红色：

```css
  h1,span{color:red;}
```

  * 权值  
ID 选择器 > 类选择器 > 标签选择器 > 继承
  * 层叠  
如果同一个元素有多个相同权值的 css 样式，就根据 css 样式的先后顺序来决定，遵循覆盖原则
  * 重要性：具有最高权值

```css
  p{color:red!important;}
  p{color:green;}
  <p class="first">这段文本会显示成红色<span>因为</span>重要性具有最高权重值。</p> 
```

  * 元素分类  
1.块状元素：div p h1...h6 ol ul dl table address blockquote form  
2.内联元素（行内元素）：文本 图片 a span br i em strong label q var cite code  
3.内联块状元素：img input

  * 块级元素  
可以通过设置 display:block 来让内联元素显示为块级元素  
块级元素特点：  
1.每个块级元素都从新的一行开始，并且其后的元素也另起一行  
2.元素的高度，宽度，行高，以及顶和底边距都可设置  
3.元素宽度不设置的情况下，是它父容器的100%（和父元素宽度一致），除非设定一个宽度

  * 内联元素 可以通过设置 display:inline 来让块状元素显示为内联元素  
内联元素特点：  
1.和其他元素都在一行上  
2.元素的高度，宽度，行高，以及顶和底边距都不可设置  
3.元素的宽度就是它包含的文字或图片的宽度，不可改变

  * 内联块状元素  
可以通过设置 display:inline-block 来让元素显示为内联块状元素  
内联块状元素特点：  
1.和其他元素都在一行上 2.元素的高度，宽度，行高，以及顶和底边距都可设置

  * 盒子模型  
  
1.内边距：padding  
2.外边距：margin  
3.边框：border

  * 盒模型：边框  
可以设置边框的粗细，样式，颜色  
边框样式有三种：dashed（虚线）｜dotted（点线）｜solid（实线）  
可单独设置四个方向的边框，如：border-bottom, border-top, border-left, border-right width 与 height 指的是内容的宽高度

```css
  div{
    border:2px solid red;
  }
```

  * 盒模型：宽高  
css定义的 width 和 height 指的是内容的宽高  
盒子的实际宽度为 外边距宽度＋盒子的边框宽度＋盒子内容的宽度＋内边距的宽度
  * 盒模型：填充  
元素内容与元素边框之间的称为填充
```css
  div{
    padding:20px 10px 15px 30px;
  } #上右下左(顺时针)
  div{
   padding-top:20px;
   padding-right:10px;
   padding-bottom:15px;
   padding-left:30px;
  }
```

  * 布局模型：  
`三种布局模型：流动模型，浮动模型，层模型`
  1. 流动模型  

    * 块状元素都会在所处的包含元素内自上而下按顺序垂直延伸分布，因为在默认状态下，块状元素的宽度都为100%
    * 内联元素都会在所处的包含元素内从左到右水平分布显示
  2. 浮动模型  
任何元素在默认情况下都是不能浮动的，可以通过设置 css 定义浮动  
`css div{float:left;}`
  3. 层模型  
让 html 元素在网页中精确定位，css 定义了一组定位（positioning）属性来支持层布局模型 
    * 绝对定位 ( `css position: absolute`)  
这条语句的作用是将元素从文档流中拖出来，然后使用 left，right，top，bottm 属性相对其最接近的一个具有定位属性的父包含块进行绝对定位，如果不存在，则相对于 body 元素，即相对于浏览器窗口
    * 相对定位 ( `css position: relative`) 它通过 left，right，top，bottom 属性确定元素在正常文档流中的偏移位置，即相对于原始位置的移动，偏移前的位置不动，依然存在
    * 固定定位 ( `css position: fixed`) 它的相对移动的坐标是视图（屏幕内大网页窗口）本身。由于视图本身是固定的，它不会跟随浏览器窗口的滚动而滚动，不会受文档流的影响

> Relative 与 Absolute 组合使用：  
前辈元素：position: relative  
当前元素：position: absolute  
这样当前元素就能够相对于前辈元素进行定位了，参照物不再是浏览器了

  * 颜色值 
    * 英文命令颜色: `css p{color:red;}`
    * rgb 颜色: `css p{color:rgb(133, 45, 200);} / p{color:rgb(20%, 33%, 25%);}`
    * 十六进制颜色: `css p{color:#00ffff;}`
  * 长度值

    * 像素（px）：
    * em：就是本元素给定的 font-size 的值, 1em = font-size  
如 `css p{font-size:12px;text-indent:2em;}` 这段代码可以实现段落首行锁进24px  
但当给 font-size 设置单位为 em 时，此时计算的标准以父元素的 font-size 为基础
    * 百分比（％）：
  * 元素水平居中  
  

    * 行内元素居中，可以通过设置父元素的 css 属性 `css text-align:center;`
    * 定宽块状元素居中，可以通过设置 “左右margin” 值为 ”auto“ 来实现居中
        
                width:500px /* 定宽 */; 
        margin:20px atuo; /*margin-left 与 margin-right 设置成 auto*/
        
        

    * 不定宽块状元素居中

      * 加入 table 标签，为这个 table 设置左右 marigin 居中，参考定宽块状元素居中
      * 设置 display:inline 方法，将其变为行内元素，然后参考行内元素居中方式
      * 设置 父元素 float, position:relative, left:50%;  
设置 子元素 positive:relative, left:50%;

  


  * 水平居中还可以使用 <center></center> 进行嵌套


```css
  .container{
    float:left;
    position:relative;
    left:50%
  }

  .container ul{
    list-style:none;
    margin:0;
    padding:0;

    position:relative;
    left:-50%;
  }
```

  * 垂直居中

    * 父元素高度确定的单行文本，通过设置 line-height 与 height 一致来实现  
`css .container{height:100px;line-height:100px;}`
    * 父元素高度确定的多行文本 
      * 使用插入 table(包括 tbody, tr, td) 标签，同时设置 vertical-align: middle（td 标签默认设置了 vertical-align: middle）
      * 设置块级元素的 display: table-cell, 激活 vertical-align 属性  
`css .container{display:table-cell; vertical-align:middle;}`
  * 隐性改变 display 类型

> 有一个有趣的现象就是当元素（不论之前是什么类型元素，display:none 除外）设置以下 2个语句 之一  
position: absolute  
float: left 或 float:right 元素会自动变成以 display: inline-block 的方式显示，当然就可以设置元素的 width 和 height 了，且默认宽度不占满父元素
