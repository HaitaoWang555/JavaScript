## Object

- Object.create() 创建一个新对象，使用现有的对象来提供新创建的对象的__proto__
- Object.entries() 返回一个给定对象自身可枚举属性的键值对数组，其排列与使用 for...in 循环遍历该对象时返回的顺序一致(区别在于 for-in 循环也枚举原型链中的属性）。
```
const object2 = { 0: 'a', 1: 'b', 2: 'c' }
console.log(Object.entries(object2)[2])
// expected output: Array ["2", "c"]
```
- Object.freeze() 方法可以冻结一个对象，冻结指的是不能向这个对象添加新的属性，不能修改其已有属性的值，不能删除已有属性，以及不能修改该对象已有属性的可枚举性、可配置性、可写性。该方法返回被冻结的对象。

```
const object1 = {
  property1: 42
};

const object2 = Object.freeze(object1);

object2.property1 = 33;
// Throws an error in strict mode

console.log(object2.property1);
// expected output: 42
```

- Object.is() 方法判断两个值是否是相同的值。

- Object.keys() 方法会返回一个由一个给定对象的自身可枚举属性组成的数组

```
// simple array
var arr = ['a', 'b', 'c'];
console.log(Object.keys(arr)); // console: ['0', '1', '2']

// array like object
var obj = { 0: 'a', 1: 'b', 2: 'c' };
console.log(Object.keys(obj)); // console: ['0', '1', '2']

// array like object with random key ordering
var anObj = { 100: 'a', 2: 'b', 7: 'c' };
console.log(Object.keys(anObj)); // console: ['2', '7', '100']

// getFoo is a property which isn't enumerable
var myObj = Object.create({}, {
  getFoo: {
    value: function () { return this.foo; }
  } 
});
myObj.foo = 1;
console.log(Object.keys(myObj)); // console: ['foo']
```

- hasOwnProperty() 方法会返回一个布尔值，指示对象自身属性中是否具有指定的属性

- toString() 方法返回一个表示该对象的字符串。

- valueOf() 方法返回指定对象的原始值。

- Object.defineProperty() 方法会直接在一个对象上定义一个新属性，或者修改一个对象的现有属性， 并返回这个对象

```
var person  = {
  _data: {
    age: 24,
    name: 'wanghaitao'    
  }
}

Object.defineProperty(person, 'age', {
  get: function() {
    console.log('person.age被读取了')
    return person._data.age
  },
  set: function(val) {
    console.log('person.age被设置了')
    person._data.age = val
  }
})

person.age = 25
console.log(person.age)

// "person.age被设置了"
// "person.age被读取了"
// 25
```