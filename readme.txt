1.因为浏览器会默认自带margin和padding，这会导致div大小设置为100%时与浏览器产生白边间隔。因此，需要通过在style里设置 body{margin:0,padding:0}来消除白边，
解决问题。注意是body！

2.要在react里实现引用背景图片，只需在style里写上 backgroundImage:'url(...)'即可，不要忘了加引号！

3.在写事件处理函数时，如handleClick，不要忘了在constructor()里加上this,因为在ES6里组件是由类的形式构造出来的，而类的方法默认不会有this。如果忘记绑定this.handleClick就将它传递给onClick, 当函数被调用时this将会被赋值undefined。如果嫌麻烦，可以在回调中使用箭头函数，如<button onClick={(e) => this.handleClick(e)}>

4.props目前来看只能被用于render和constructor函数里，若别的函数中要使用，需要先在constructor中转化成state。

5.在使用webstorm打字自动补充事件名称时，如鼠标时间onClick，软件会自动将其变为小写，导致react无法识别。

6.在写触发事件来改变CSS样式时(这里指的是写在constructor中的style对象，并非内联在组件中的CSS样式)，请注意，因为JS的不可变性（immutabilty），对style对象的改变并不会添加到原来的style对象中，而是形成一个新的style对象。这也就意味着，如果不想改变太多的原来的样式，就需要复制一大堆代码。但是，这里可以使用展开运算符 ...来引用原style对象，节省很多工作量。