## this
一. 全局上下文

  在全局执行上下文中（在任何函数体外部）this 都指代全局对象。

二. 函数上下文

- 简单调用

```
// 非严格模式
function f1(){
  return this
}
//在浏览器中：
f1() === window   //在浏览器中，全局对象是window

//在Node中：
f1() === global

//严格模式下，this默认为undefined。
```    

把 this 的值从一个上下文传到另一个，就要用 call 或者apply 方法

```
function add(c, d) {
  return this.a + this.b + c + d
}

var o = {a: 1, b: 3}

add.call(o, 5, 7) // 1 + 3 + 5 + 7 = 16

add.apply(o, [10, 20]) // 1 + 3 + 10 + 20 = 34
```
- bind方法
```
function f(){
  return this.a
}
var g = f.bind({a:"azerty"})
console.log(g()) // azerty

var h = g.bind({a:'yoo'}) // bind只生效一次！
console.log(h()) // azerty

```
- 作为对象的方法

  当函数作为对象里的方法被调用时，它们的 this 是调用该函数的对象。
```
var o = {
  prop: 37,
  f: function() {
    return this.prop
  }
}

console.log(o.f()) //  37
```
- 箭头函数
  
  就是外面的this

- 作为构造函数

  当一个函数用作构造函数时（使用new关键字），它的this被绑定到正在构造的新对象。

- 作为一个DOM事件处理函数

  当函数被用作事件处理函数时，它的this指向触发事件的元素
  