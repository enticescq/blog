---
title: canvas
date: 2018-11-01 21:23:49
tags: [canvas,基础方法]
---

> canvas的基本方法 
<!--more-->

### 1.首先使用canvas必须要

 创建一个 2d 上下文对象

```shell
var canvas = documen.getElementById('canvas元素')
var ctx = canvas.getContext('2d');
```

画一个矩形

```bash
ctx.fillStyle = "rgba(0, 0, 200, 0.5)";

 // x y width height
ctx.fillRect (30, 30, 55, 50);

```


> canvas 提供了三种方法绘制矩形：


- fillRect(x, y, width, height)

绘制一个填充的矩形

- strokeRect(x, y, width, height)

绘制一个矩形的边框

- clearRect(x, y, widh, height)

清除指定的矩形区域，然后这块区域会变的完全透明。


```bash
function draw(){
    var canvas = document.getElementById('tutorial');
    if(!canvas.getContext) return;
    var ctx = canvas.getContext("2d");
    ctx.fillRect(10, 10, 100, 50);  //绘制矩形,填充的默认颜色为黑色
    ctx.strokeRect(10, 70, 100, 50);  //绘制矩形,边框为黑色
    
}
draw();

```
--- 

### 2.绘制路径(path)

图形的基本元素是路径。

路径是通过不同颜色和宽度的线段或曲线相连形成的不同形状的点的集合。

一个路径，甚至一个子路径，都是闭合的。

> 使用路径绘制图形需要一些额外的步骤：

1. 创建路径起始点
1. 调用绘制方法去绘制出路径
1. 把路径封闭
1. 一旦路径生成，通过描边或填充路径区域来渲染图形。


> 下面是需要用到的方法：


- beginPath()

新建一条路径，路径一旦创建成功，图形绘制命令被指向到路径上生成路径

- moveTo(x, y)

把画笔移动到指定的坐标(x, y)。相当于设置路径的起始点坐标。

- ctx.lineTo(x, y)

绘制一条从当前位置到指定坐标(200, 50)的直线.

- closePath()

闭合路径之后，图形绘制命令又重新指向到上下文中

- stroke()

通过线条来绘制图形轮廓

- fill()

通过填充路径的内容区域生成实心的图形

> 演示

```bash
function draw(){
    var canvas = document.getElementById('tutorial');
    if (!canvas.getContext) return;
    var ctx = canvas.getContext("2d");
    ctx.beginPath(); //新建一条path
    ctx.moveTo(50, 50); //把画笔移动到指定的坐标
    ctx.lineTo(200, 50);  //绘制一条从当前位置到指定坐标(200, 50)的直线.
    //闭合路径。会拉一条从当前点到path起始点的直线。如果当前点与起始点重合，则什么都不做
    ctx.closePath();
    ctx.stroke(); //绘制路径。
}
draw();

```

> 绘制三角形

```bash
function draw(){
    var canvas = document.getElementById('tutorial');
    if (!canvas.getContext) return;
    var ctx = canvas.getContext("2d");
    ctx.beginPath();
    ctx.moveTo(50, 50);
    ctx.lineTo(200, 50);
    ctx.lineTo(200, 200);
  	ctx.closePath(); //虽然我们只绘制了两条线段，但是closePath会closePath，仍然是一个3角形
    ctx.stroke(); //描边。stroke不会自动closePath()
     
     
    //ctx.fill(); //填充闭合区域。如果path没有闭合，则fill()会自动闭合路径。
}
draw();
```

### 3.绘制圆弧

1. arc(x, y, r, startAngle, endAngle, anticlockwise):
   以(x, y)为圆心，以r为半径，从 startAngle弧度开始到endAngle弧度结束。anticlosewise是布尔值，true表示逆时针，false表示顺时针。(默认是顺时针)
  1.1. 这里的度数都是弧度。
       0弧度是指的x轴正方形

```bash
radians=(Math.PI/180)*degrees   //角度转换成弧度
```

```bash
    ctx.beginPath();
    ctx.arc(50, 50, 40, 0, Math.PI / 2, false);
    ctx.stroke();
```


```shell

//画半圆
//	function draw(){
//		var can = document.getElementById('app')
//	    var ctx = can.getContext('2d')
//	    ctx.beginPath() // 创建路径
//	    ctx.arc(50,50,40,0,Math.PI/2,false)
//	    //ctx.closePath() //使他闭合
//	    ctx.stroke() //画
//	    
//	    ctx.beginPath();
//      ctx.arc(50, 150, 40, Math.PI, Math.PI / 2, false);
//      ctx.closePath() //使他闭合
//      ctx.fill();
//	}


//查看arcTo的属性
function draw(){
		var can = document.getElementById('app')
	    var ctx = can.getContext('2d')
	    ctx.beginPath() // 创建路径
         ctx.moveTo(50, 50);
        //context.fillRect(x1,y1,x2,y2,r);
        //弧的起点的 x 坐标， 弧的起点的 y 坐标 ，   弧的终点的 x 坐标，弧的终点的 y 坐标，弧的半径
        ctx.arcTo(200, 50, 200, 200, 100);
        ctx.stroke();
        
        ctx.beginPath();
        ctx.fillRect(50, 50, 10, 10); //绘制正方形
        //ctx.fill()
        ctx.fillRect(180, 50, 10, 10)
        //ctx.fillRect(200, 200, 10, 10)
	}

draw()
	
```

