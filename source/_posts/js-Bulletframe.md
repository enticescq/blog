---
title: js弹框
typora-root-url: ../ArrayNot/
date: 2019-07-29 21:08:29
tags: [js,原生]
---

![image text](js-Bulletframe/2010011712462000.jpg)
Welcome to .


<!--more-->
## 一、JS的三种最常见的对话框



``` bash
//弹出对话框并输出一段提示信息  
    function ale() {  
        //弹出一个对话框  
        alert("提示信息！");  
  
    }  
  
    //弹出一个询问框，有确定和取消按钮  
    function firm() {  
        //利用对话框返回的值 （true 或者 false）  
        if (confirm("你确定提交吗？")) {  
            alert("点击了确定");  
        }  
        else {  
            alert("点击了取消");  
        }  
  
    }  
  
    //弹出一个输入框，输入一段文字，可以提交  
    function prom() {  
        var name = prompt("请输入您的名字", ""); //将输入的内容赋给变量 name ，  
  
        //这里需要注意的是，prompt有两个参数，前面是提示的话，后面是当对话框出来后，在对话框里的默认值  
        if (name)//如果返回的有内容  
        {  
            alert("欢迎您：" + name)  
        }  
  
    }  


```



### 二、点击按钮时常用的6中提示框和操作

``` bash
<!-----------按钮提示框---------->  
<input type="button" name="btn2" id="btn2" value="删除" onclick="return confirm('Yes/No'););  
  
<!-----------按钮提示框---------->   
<input type="button" name="btn2" id="btn2" value="提示" onclick="javaScript:alert('您确定要删除吗？');  
  
<!-----------提交按钮---------->   
<input type="button" value="提交" onclick="javaScript:window.location.href='http://www.baidu.com';"/>  
  
<!-----------关闭按钮---------->   
<input type="button" value="关闭" onclick="javaScript:window.close();">  
  
<!-----------返回并关闭连接---------->   
<a href="#" onclick="javascript:;window.opener.location.reload();window.close()">返回</a>  
javaScript:window.location.reload();//返回当前页并刷新  
  
<!-----------返回上一级页面---------->   
<input type="button" name="button" value="< 返回" onclick="javascript:history.go(-1)"/> 

```



### 三、弹出独立窗口

``` bash
//关闭,父窗口弹出对话框,子窗口直接关闭   
this.Response.Write("<script language=javascript>window.close();</script>");  
  
//关闭,父窗口和子窗口都不弹出对话框,直接关闭   
this.Response.Write("<script>");   
this.Response.Write("{top.opener =null;top.close();}");   
this.Response.Write("</script>");  
  
//弹出窗口刷新当前页面width=200 height=200菜单。菜单栏,工具条,地址栏,状态栏全没有   
this.Response.Write("<script language=javascript>window.open('rows.aspx','newwindow','width=200,height=200')</script>");  
  
//弹出窗口刷新当前页面   
this.Response.Write("<script language=javascript>window.open('rows.aspx')</script>");  
this.Response.Write("<script>window.open('WebForm2.aspx','_blank');</script>");  
  
//弹出提示窗口跳到webform2.aspx页(在一个IE窗口中)   
this.Response.Write(" <script language=javascript>alert('注册成功');window.window.location.href='WebForm2.aspx';</script> ");  
  
//关闭当前子窗口,刷新父窗口   
this.Response.Write("<script>window.opener.location.href=window.opener.location.href;window.close();</script>");  
this.Response.Write("<script>window.opener.location.replace(window.opener.document.referrer);window.close();</script>");  
  
//子窗口刷新父窗口   
this.Response.Write("<script>window.opener.location.href=window.opener.location.href;</script>");  
this.Response.Write("<script>window.opener.location.href='WebForm1.aspx';</script>");  
  
//弹出提示窗口.确定后弹出子窗口(WebForm2.aspx)   
this.Response.Write("<script language='javascript'>alert('发表成功！');window.open('WebForm2.aspx')</script>");  
  
//弹出提示窗口,确定后,刷新父窗口   
this.Response.Write("<script>alert('发表成功！');window.opener.location.href=window.opener.location.href;</script>");  
  
//弹出相同的一页   
<INPUT type="button" value="Button" onclick="javascript:window.open(window.location.href)">  
  
//   
Response.Write("parent.mainFrameBottom.location.href='yourwebform.aspx?temp=" +str+"';");  
  
  
<SCRIPT LANGUAGE="javascript">   
<!--   
window.open ('page.html', 'newwindow', 'height=100, width=400, top=0, left=0, toolbar=no, menubar=no, scrollbars=no, resizable=no,location=n o, status=no') //这句要写成一行  
-->   

/*
 参数解释：
window.open 弹出新窗口的命令； 
'page.html' 弹出窗口的文件名； 
'newwindow' 弹出窗口的名字（不是文件名），非必须，可用空''代替； 
　　height=100 窗口高度； 
　　width=400 窗口宽度； 
　　top=0 窗口距离屏幕上方的象素值； 
　　left=0 窗口距离屏幕左侧的象素值； 
　　toolbar=no 是否显示工具栏，yes为显示； 
　　menubar，scrollbars 表示菜单栏和滚动栏。 
　　resizable=no 是否允许改变窗口大小，yes为允许； 
　　location=no 是否显示地址栏，yes为允许； 
　　status=no 是否显示状态栏内的信息（通常是文件已经打开），yes为允许；

'newwin':隐藏菜单栏地址栏工具条 
*/
```


### 四、弹出窗口实例演示

``` bash
//1、最基本的弹出窗口代码  
  
window.open ('page.html')   
  
  
  //2、经过设置后的弹出窗口  
  
window.open('page.html', 'newwindow', 'height=100, width=400, top=0, left=0, toolbar=no, menubar=no, scrollbars=no, resizable=no,location=n o, status=no') //这句要写成一行  
  
   
//参数解释：   
//window.open 弹出新窗口的命令；   
//'page.html' 弹出窗口的文件名；   
//'newwindow' 弹出窗口的名字（不是文件名），非必须，可用空''代替；   
//height=100 窗口高度；   
//width=400 窗口宽度；   
//top=0 窗口距离屏幕上方的象素值；   
//left=0 窗口距离屏幕左侧的象素值；   
//toolbar=no 是否显示工具栏，yes为显示；   
//menubar，scrollbars 表示菜单栏和滚动栏。   
//resizable=no 是否允许改变窗口大小，yes为允许；   
//location=no 是否显示地址栏，yes为允许；   
//status=no 是否显示状态栏内的信息（通常是文件已经打开），yes为允许；   
   
  //3、用函数控制弹出窗口  
  
function openwin() {  
    window.open("page.html", "newwindow", "height=100, width=400, toolbar =no, menubar=no, scrollbars=no, resizable=no, location=no, status=no") //写成一行  
}   
  $(document).ready(fucntion(){  
      openwin();  
  });  
  
//这里定义了一个函数openwin(),函数内容就是打开一个窗口。在调用它之前没有任何用途。怎么调用呢？  
  
//方法一：<body onload="openwin()"> 浏览器读页面时弹出窗口；   
//方法二：<body onunload="openwin()"> 浏览器离开页面时弹出窗口；   
//方法三：用一个连接调用：   
//<a href="#" onclick="openwin()">打开一个窗口</a>   
//注意：使用的“#”是虚连接。   
//方法四：用一个按钮调用：   
//<input type="button" onclick="openwin()" value="打开窗口">   
  
  //4、同时弹出2个窗口   
   
    function openwin() {  
        window.open("page.html", "newwindow", "height=100, width=100, top=0, left=0,toolbar=no, menubar=no, scrollbars=no, resizable=no, location=n o, status=no")//写成一行  
        window.open("page2.html", "newwindow2", "height=100, width=100, top=1 00, left=100,toolbar=no, menubar=no, scrollbars=no, resizable=no, loca tion=no, status=no")//写成一行  
    }   
  
//为避免弹出的2个窗口覆盖，用top和left控制一下弹出的位置不要相互覆盖即可 。最后用上面说过的四种方法调用即可。   
//注意：2个窗口的name(newwindows和newwindow2)不要相同，或者干脆全部为空。  
  
  //5、主窗口打开文件1.htm，同时弹出小窗口page.html  
  
    function openwin() {  
        window.open("page.html", "", "width=200,height=200")  
    }    
  
//调用：<a href="1.htm" onclick="openwin()">open</a>  
   
  //6、弹出的窗口之定时关闭控制  
   
//下面我们再对弹出的窗口进行一些控制，效果就更好了。如果我们再将一小段 代码加入弹出的页面(注意是加入page.html的HTML中，不是主页面中)，让它10秒后自动关闭是不是更酷了？  
  //首先，将如下代码加入page.html文件的<head>区：   
  function closeit() {  
      setTimeout("self.close()", 10000) //毫秒   
  }   
  //页面加载完成调用关闭事件  
$(document).ready(fucntion(){  
      closeit();  
  });  
  
  //7、在弹出窗口中加上一个关闭按钮  
  
  //<INPUT TYPE='BUTTON' VALUE='关闭' onClick='window.close()'>   
  
  
  //8、内包含的弹出窗口-一个页面两个窗口  
  
//上面的例子都包含两个窗口，一个是主窗口，另一个是弹出的小窗口。通过下面的例子，你可以在一个页面内完成上面的效果。  
  
    function openwin() {  
        OpenWindow = window.open("", "newwin", "height=250, width=250,toolbar=no ,scrollbars=" + scroll + ",menubar=no");  
        //写成一行   
        OpenWindow.document.write("<TITLE>例子</TITLE>")  
        OpenWindow.document.write("<BODY BGCOLOR=#ffffff>")  
        OpenWindow.document.write("<h1>Hello!</h1>")  
        OpenWindow.document.write("New window opened!")  
        OpenWindow.document.write("</BODY>")  
        OpenWindow.document.write("</HTML>")  
        OpenWindow.document.close()  
    }   
  
//<a href="#" onclick="openwin()">打开一个窗口</a>   
//<input type="button" onclick="openwin()" value="打开窗口">   
  
  
  //9、终极应用--弹出的窗口之Cookie控制  
  
//回想一下，上面的弹出窗口虽然酷，但是有一点小毛病，比如你将上面的脚本放在一个需要频繁经过的页面里(例如首页)，那么每次刷新这个页面，窗口都会弹出一次，我们使用cookie来控制一下就可以了。  
//首先，将如下代码加入主页面HTML的<HEAD>区：  
  
    function openwin() {  
        window.open("page.html", "", "width=200,height=200")  
    }  
    function get_cookie(Name) {  
        var search = Name + "="  
        var returnvalue = "";  
        if (document.cookie.length > 0) {  
            offset = document.cookie.indexOf(search)  
            if (offset != -1) {  
                offset += search.length  
                end = document.cookie.indexOf(";", offset);  
                if (end == -1)  
                    end = document.cookie.length;  
                returnvalue = unescape(document.cookie.substring(offset, end))  
            }  
        }  
        return returnvalue;  
    }  
    function loadpopup() {  
        if (get_cookie('popped') == '') {  
            openwin()  
            document.cookie = "popped=yes"  
        }  
    }   
  
//然后，用<body onload="loadpopup()">（注意不是openwin而是loadpop啊！）替换主页面中原有的<BODY>这一句即可。你可以试着刷新一下这个页面或重新进入该页面，窗口再也不会弹出了。真正的Pop-Only-Once！  

```