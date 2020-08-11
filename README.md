<h1>面试总结</h1>
<h6>闭包：函数可以访问并且记住当前词法作用域（写代码时就已经决定了的变量作用域），就产生了闭包，即使函数在此法作用域之外执行</h6>
<h6>function fn1() {</h6>
	<h6>var name = 'iceman';</h6>
	<h6>function fn2() {</h6>
		<h6>console.log(name);</h6>
	<h6>}</h6>
	<h6>return fn2;</h6>
<h6>}</h6>
<h6>var fn3 = fn1();</h6>
<h6>fn3()</h6>
<h6>fn3就是fn2  fn记住了并且访问了他的此法作用域，fn2在此法作用域之外</h6>

<h1>css三列布局</h1>
<h2>已知左右宽度</h2>
<h6>css双飞翼</h6>
    <h6>.container{</h6>
        <h6>min-width:600px;</h6>
    <h6>}</h6>
    <h6>.colmun{</h6>
        <h6>float:left;</h6>
        <h6>height: 200px;</h6>
    <h6>}</h6>
    <h6>#left{</h6>
        <h6>width:200px;</h6>
        <h6>background: red;</h6>
        <h6>margin-left:-100%;</h6>
    <h6>}</h6>
    <h6>#right{</h6>
        <h6>width:200px;</h6>
        <h6>background: red;</h6>
        <h6>margin-left: -200px;</h6>
    <h6>}</h6>
    <h6>#center{</h6>
        <h6>width:100%;</h6>
        <h6>background: #ccc;</h6>
    <h6>}</h6>
    
 <div class="container">
    <div id="center" class="colmun">
        <div class="aa"></div>
    </div>
    <div id="left" class="colmun"></div>
    <div id="right" class="colmun"></div>
</div>

       
