# js
js面试笔记
MVVM是将“数据模型数据双向绑定”的思想作为核心，因此在View和Model之间没有联系，
 通过ViewModel进行交互，而且Model和ViewModel之间的交互是双喜那个的，因此试图的数据的变
 化会同事修改数据源，而数据源数据的变化也会立即反应到View上。
 <!-- for循环异步问题 -->
 for (var i = 0; i < 5; i++) { setTimeout(function() { console.log(i); }, 1000 * i); }
<!-- es6使用let声明循环参数： -->
for (let i = 0; i < 5; i++) { setTimeout(function() { console.log(i); }, 1000 * i); }

<!-- 闭包 -->
for(let i=0;i<5;i++){
    (function(){
        setTimeout(function(){
            console.log(i)
        },1000*i)(i)
    })
}
<!-- 闭包内存释放 -->  
function f1(){ 　
    var n=999; 　
    return　function f2(){ 
        　　alert(n); 
    } 
}
 var a = f1();
  a=null; <!-- 释放-->

<!-- 函数节流 -->
函数防抖 函数防抖指的是多次触发事件后，事件处理函数只执行一次，
而且是在事件触发操作停止的时候。具体的思路就是延迟处理函数，如果设定的时间到来之前，
又一次触发了事件，就清除上一次的定时器，具体代码实现如下。
var obj = document.getElementById('handle');
 function myFun() {
      console.log('throttleV1'); 
    } 
 function db(method,delay,context){
                    clearTimeout(method.timer);
                    method.timer =setTimeout(function(){
                        method.call(context) },delay) 
                        } 
 obj.onmousemove = function(){
         db(myFun,500); 
        }

 <!-- 垃圾回收机制 -->
 <!-- 标记清楚 -->
 当变量进入环境时，将变量标记"进入环境"，当变量离开环境时，标记为："离开环境"。某一个时刻，垃圾回收器会过滤掉环境中的变量，以及被环境变量引用的变量，剩下的就是被视为准备回收的变量。
 <!-- 引用计数 -->
  声明一个变量，当他被引用赋值时，则记录一次引用次数，包含这个值的引用变量又取得了另外的值，
  则这个值引用次数减1。引用次数为0，则释放值所占用的内存。



 <!-- 数组去重 -->

 var s = []; //遍历数组
  for(var i = 0;i<arr.length;i++){ 
      if(s.indexOf(arr[i])==- 1){ 
          //判断在s数组中是否存在，不存在则push到s数组中 
          s.push(arr[i]);
    } 
}
<!-- 冒泡 -->
function bubbleSort(arr) { 　
    　var len = arr.length; 　　
    for (var i = 0; i len; i++) { 
        for (var j=0 ; j < len - 1 - i;j++) { 
            　if (arr[j]> arr[j+1]) {
                 //相邻元素两两对比 　　　　
                 　var temp = arr[j+1]; //元素交换 　
                 　arr[j+1] = arr[j]; 　　　　
                   arr[j] = temp; 　　　　
                　　} 　　　
            　}
    　　} 　　
    return arr; 
}


<!-- 7、随机生成指定长度的字符串 -->
<!-- ◎Math.ceil()执行向上舍入，即它总是将数值向上舍入
◎Math.floor()执行向下舍入，即它总是将数值向下舍入
 ◎Math.round()执行标准舍入，即它总是将数值四舍五入 -->
     function add(a){ 
         var str="qewrjghglgmglgghghg55556698222";
          var temp=""; 
          for(var i=0;i<a;i++){ 
              temp+=str.charAt(Math.random()*str.length)
        } 
        return temp 
    } 
    console.log(add(50))

    
<!-- 字符串换出现最多次数 -->
 function findMax(str){
      if (str.length ==1){ 
          return str;
         } 
         let charObj = {}; 
         for (let i=0;i<str.length;i++) 
         { 
             if(!charObj[str.charAt(i)]){
                 charObj[str.charAt(i)]=1; 
                }else{
                 charObj[str.charAt(i)]+=1; }
                } 
                     let maxChar='' , 
                     maxValue=1; 
                     for (var k in charObj){ 
                         if (charObj[k]>=maxValue) { 
                             maxChar=k; 
                             maxValue = charObj[k]; 
                        } 
                    } return maxChar;
                 }
 <!-- 获取浏览器URL中查询字符串中的参数 -->
 function showWindowHref(){ 
     var sHref ="channelid=12333&name=xiaoming&age=23" 
     var str =sHref.split("&") 
     console.log(str)
var obj={} for(var i in str){
     var str1 =str[i].split("=")
      obj[str1[0]] =str1[1] 
    }
       return obj 
      ole.log(href)
 }

 <!-- 闭包 -->
<button>Button0</button>
<button>Button1</button>
<button>Button2</button>
<button>Button3</button>
<button>Button4</button>

 var btns = document.getElementsByTagName('button'); 
 for (var i = 0, len = btns.length; i < len; i++) { 
     (function(i){ btns[i].onclick=f
    unction () { alert(i); } }(i))
 }

 <!-- JS 动态删除对象属性 -->
 用关键字delete

 <!-- 面向对象 -->
 多态：
 是指一个引用(类型)在不同情况下的多种状态(通过指向父类的引用，来调用在不同子类中的实现方法)。

 

<!-- 事件委托 -->
利用冒泡原理把事件加到父元素上，触发执行
<!-- 13.json和jsonp的区别? -->
json 是数据格式  jsonp是是把json用js包裹起来，也就是将json封装成js文件过去
<!-- div垂直居中 -->
<div class="box">
    <div class="center-box1">
        <p>【第一种方法】知道长和宽，使用绝对定位+外边距设定水平垂直居中</p>
    </div>
</div>

.box{ width:600px; height:600px; background: red; position: relative; } .center-box1{ position: absolute; width:200px; height:200px;
top:50%; left:50%; background:#ccc; margin-left:-100px; margin-top:-100px; }

<!-- 跨域document.domain -->
  前提条件：这两个域名必须属于一个基础的域名，而且所有的协议，端口都要一致
 ，两个子域名： aaa.xxx.com bbb.xxx.com
 aaa里的 一个页面（a.html）引入bbb里面的一个网页（b.html）

 这里a.html 不能操作b.html里面的内容，
 因为document.domain不一样，一个是aaa.xxx.com，另一个是bbb.xxx.com。
 用javascript 将两个页面改成一样的，在a.html 和b.html 都加入
 document.domain = "xxx.com"; 这样这两个页面就可以互相操作了。也就是实现了同一基础域名之间的"跨域"
<!-- postMessage -->
.在父框架页面index.html发送obj对象给远程服务器的wozien.com/test/b.html，该页面是通过iframe加载的
在远程页面b.html中监听message事件，先通过origin属性判断下数据来源的域是否可信任
<!-- a页面 -->
var obj = 
{ msg: 'this is come from client message!' 
}
 function postMsg ()
 { var iframe = document.getElementById('proxy');
var win = iframe.contentWindow; win.postMessage(obj,'http://wozien.com'); 
}
<!-- b页面 -->
window.onmessage = function(e){
     if(e.origin !== 'http://localhost') 
     return; console.log(e.origin+' '+e.data.msg); 
    }
    <!-- eval -->
     eval()主要用于执行一些由用户输入或者由ajax从服务器获取的代码。再有是用来执行js加密代码解析后的字符串

     <!-- js  几大类型   bsofun-->
     boolean string objct function undefined number
     <!-- 浏览器内核 -->
        webkit             chrome
           -moz   mozilla  firefox
             -o  opera
              -ms  trident

        <!-- new 做了什么       -->
        创建一个新对象
        将函数的作用域付给新对象
        执行函数
        返回新对象

        <!-- 浏览器兼容h5标签 -->
        引用计谷歌的html5.js 在html头部添加javascript简单的document.createElemen 利用注释针对ie这个 js文件
        
        <!–[if lt IE9]>
        <script src=”http://html5shiv.googlecode.com/svn/trunk/html5.js”></script>
        <![endif]–>

        <!-- jq on bind live delegate -->
        bind 直接绑定在元素上
        live 冒泡方式绑定跟适合表单类型
        delegate 更精确  范围跟小
        on 集合了他们的优点
 <!-- 如何用jQuery禁用浏览器的前进后退按钮？ -->
 window.history.forward(1)

$("div[title^=test]")

<!-- js获取今天是周几 -->
 var d =new Date().getDay();
 <!-- 作用域链0 -->

 作用域链：当代码在某个环境执行时会创建变量对象的作用域链，
 作用：保证环境能有权访问的变量和函数有序的执行
<!-- 原型链 -->
原型链是实现继承的主要方法。其基本思想是：利用原型让一个引用类型继承另一个应用类型的属性和方法。
 <!-- 基本数据类型 引用类型的区别 -->
 基本类型：首先基本类型的赋值是不可改变的，
         var a=2; var b=a; b=3; console.log(a);//2 console.log(b);//3
 引用类型：这个赋值是可以改变的
 var aa=[3,4,2,5]; var bb=aa; bb.push(6); console.log(aa);//34256 console.log(bb);//34256
<!-- 阶乘 -->
function add(num){
    if(num<1){

    }else{
        num*(num-1)
    }
}
function add(num){
    if(mun<1){
        return
    }else{
       return num*(num-1)
    }
}
call 参数直接放进去以逗号分隔
apply  数组
bind() bind 返回的是一个新的函数，你必须调用它才会被执行

<!-- 跨域形成 -->
协议、端口、和域名有任意一个不同就会造成跨域
<!-- 利用多个域名来存储网站资源 -->
  cdn 缓存更方便 
  突破浏览器并发限制
  节约cookie宽带
  防止不必要的安全问题

  <!-- 前端优化 -->
  <!-- 页面级优化 -->
  减少http请求 
          :简单化页面，设置http缓存
  使用浏览器缓存
 -将小图片合并为一张大图片
 CSS放在页面最上面、JavaScript放在页面最下面
 精简CSS和JS文件
 js减少对DOM的操作
 减少Cookie传输

 <!-- 原生JS实现下拉加载 -->

  <!-- promise -->
  是一个简单的容器，是一个异步操作，Promise是一个构造函数
  三种状态：
  pending  进行中
  fulfilled  已成功
  rejected   以失败

  只能从padding ->fulfilld
       pending ->rejected

       一旦执行无法取消，不设置回调函数无法知道进展到哪一个阶段


    var aa = document.getElementById('aa')
    aa.onclick = function () {
        this.nextElementSibling.className ="bbb"
        console.log(this.previousElementSibling)
        
    }
<!-- 下拉刷新原理 -->
 滚动条高度+可视范围高度>文档的总高度 加载

 <!-- js拷贝 -->
 基本类型穿的是值  数组 对象传的是地址
 浅拷贝
     浅复制是复制引用 复制的引用都是指向同一个对象实例，相互影响

 深拷贝
     将堆中重新分配内存，并且把原对象实例的所有属性都进行新建复制，复制后的对象与原来的对象是完全隔离的  
     
     
     <!-- 举个例子 -->
     <!-- 栈中的地址  引用类型 -->
     <!-- 堆中的值    基本类型 -->

     var arr =[1,2,3,4,6]
     var b =arr;
     b.[3] =5;
     console.log(arr[3]) =5

     var c =arr[0];
     c =7;
     console.log(arr[0])   =1

     <!-- 例子：2 -->
     var a ={
         key:'111'
     };
     function copy(p){
         var c ={};
         for(var i in p){
             c[i] =p[i]
         }
          return c;
     }
     a.key2 =["小辉"，"小辉"];
     var b =copy(a);
     b.key3="333";
     b.key1   //111
     b.key3   //333
     a.key3   //unfefined

  a拷贝到b key1 key2 都拷贝了 新加一个b.key3="333"，然后a.key3 //unfefined
b.key2.push("大辉") alert(b.key2) //小辉，小辉，大辉
 alert(a.key2); //小辉，小辉，大辉

       
