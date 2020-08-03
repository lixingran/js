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

       
