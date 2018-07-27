## DOM Event
- addEventListener 
```
// options 为true时 是事件捕获，是false，则是在事件冒泡阶段处理
myButton.addEventListener('click', function(){alert('Hello world');}, false);
// 使用 passive 改善的滚屏性能
elem.addEventListener('touchmove', function listener() { /* do something */ }, { passive: true });
```

- event.stopPropagation() 阻止事件冒泡
- event.preventDefault() 取消默认事件

### 事件流

  - 事件冒泡：事件开始时由最具体的元素接收，然后逐级向上传播到较为不具体的元素

  - 事件捕获：不太具体的节点更早接收事件，而最具体的元素最后接收事件，和事件冒泡相反

  - DOM事件流：DOM2级事件规定事件流包括三个阶段，事件捕获阶段，处于目标阶段，事件冒泡阶段，首先发生的是事件捕获，为截取事件提供机会，然后是实际目标接收事件，最后是冒泡阶段

### 事件代理
```
<div class="container">
  <div class="box">box1</div>
  <div class="box">box2</div>
  <div class="box">box3</div>
</div>

var box = document.querySelector('.container')
box.addEventListener('click',function(e) {
  if(e.target.classList.contains('box')){ // 检查元素的类属性中是否存在指定的类值
    console.log(e.target.innerText)
  }
})
```