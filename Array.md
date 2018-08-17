## Array
- isArray 确定传递的值是否是一个 Array。
```
Array.isArray([1, 2, 3]);  
// true
```
- push 再数组最后添加一个元素
- pop 把数组最后一位弹出来，返回
```
var arr = [1,2,3,5,8]
var newArr = arr.pop()
// arr [1, 2, 3, 5]
// newArr 8
```
- unshift 在数组第一位新增
- shift 把数组第一位拿出来返回，数组发生变化
```
var arr = [1,2,3,5,8]
var newArr = arr.shift()
// arr [2,3,5,8]
// newArr 1
```
- splice(a, b) 从下标为a的元素开始，拿出来b个元素作为一个数组返回，原数组发生改变
```
var arr = [1,2,3,5,8]
var newArr = arr.splice(2, 2)    
// arr [1,2,8]
// newArr [3, 5]
```
- splice(a, b, 'x', 'y') 从下标为a的位置开始，删除b个，新增两个元素
```
var arr = [1,2,3,5,8]
var newArr = arr.splice(2, 2, 'x','y')    
// arr [1,2,'x','y',8]
// newArr [3, 5]
```
- slice(a, b) 从下标为a开始，到下标为b结束(不包括b)，做为新数组，原数组不变
```
var arr = [1,2,3,5,8]
var newArr = arr.slice(2, 4)    
// arr [1, 2, 3, 5, 8]
// newArr [3, 5]
```
- join('-') 用'-'连接每一项
```
var arr = [1,2,3,5,8]
var str = arr.join('-')  
// arr [1, 2, 3, 5, 8]
// str 1-2-3-5-8
```
- reverse 倒序，本身发生变化
```
var arr = [1,2,3,5,8]
var newArr = arr.reverse()
// arr [8, 5, 3, 2, 1]
// str [8, 5, 3, 2, 1]
```
- sort 排序，本身发生变化
```
var arr = [1,2,9,3,5,4,0]
var newArr = arr.sort(function(v1, v2){ 
    return v1-v2
})
// arr [0, 1, 2, 3, 4, 5, 9]
// arr [0, 1, 2, 3, 4, 5, 9]
```
- concat(array)  拼接数组
```
var array1 = ['a', 'b', 'c'];
var array2 = ['d', 'e', 'f'];
var array3 = array1.concat(array2)

//array1  ["a", "b", "c"]
//array2  ["d", "e", "f"]
//array3  ["a", "b", "c", "d", "e", "f"]
```
- every 测试数组的所有元素是否都通过了指定函数的测试
```
function isBelowThreshold(currentValue) {
  return currentValue < 40;
}

var array1 = [1, 30, 39, 29, 10, 13];

console.log(array1.every(isBelowThreshold));
// expected output: true
```
- some 方法测试数组中的某些元素是否通过由提供的函数实现的测试
```
var array = [1, 2, 3, 4, 5];

var even = function(element) {
  // checks whether an element is even
  return element % 2 === 0;
};

console.log(array.some(even));
// expected output: true

```
- fill 用一个固定值填充一个数组中从起始索引到终止索引内的全部元素
```
var array1 = [1, 2, 3, 4];

// fill with 0 from position 2 until position 4
console.log(array1.fill(0, 2, 4));
// expected output: [1, 2, 0, 0]

// fill with 5 from position 1
console.log(array1.fill(5, 1));
// expected output: [1, 5, 5, 5]

console.log(array1.fill(6));
// expected output: [6, 6, 6, 6]
```
- filter 创建一个新数组, 其包含通过所提供函数实现的测试的所有元素。 
```
var words = ['spray', 'limit', 'elite', 'exuberant', 'destruction', 'present'];
const result = words.filter(word => word.length > 6);
console.log(result);
// expected output: Array ["exuberant", "destruction", "present"]
```
- find 返回数组中满足提供的测试函数的第一个元素的值。否则返回 undefined
```
var array1 = [5, 12, 8, 130, 44];

var found = array1.find(function(element) {
  return element > 10;
});

console.log(found); //  12
```
- findIndex 返回数组中满足提供的测试函数的第一个元素的索引。否则返回-1。
```
var array1 = [5, 12, 8, 130, 44];

function findFirstLargeNumber(element) {
  return element > 13;
}

console.log(array1.findIndex(findFirstLargeNumber));
// expected output: 3
```
- indexOf 返回在数组中可以找到一个给定元素的第一个索引，如果不存在，则返回-1。
```
var beasts = ['ant', 'bison', 'camel', 'duck', 'bison'];

console.log(beasts.indexOf('bison'));
// expected output: 1

// start from index 2
console.log(beasts.indexOf('bison', 2));
// expected output: 4

console.log(beasts.indexOf('giraffe'));
// expected output: -1
```
- includes 用来判断一个数组是否包含一个指定的值
```
var pets = ['cat', 'dog', 'bat'];

console.log(pets.includes('cat'));
// expected output: true

console.log(pets.includes('at'));
// expected output: false

```
- map 方法创建一个新数组，其结果是该数组中的每个元素都调用一个提供的函数后返回的结果。
```
var array1 = [1, 4, 9, 16];

// pass a function to map
const map1 = array1.map(x => x * 2);

console.log(map1);
// expected output: Array [2, 8, 18, 32]

```
- reduce 方法对累加器和数组中的每个元素（从左到右）应用一个函数，将其减少为单个值。
```
const array1 = [1, 2, 3, 4];
const reducer = (accumulator, currentValue) => accumulator + currentValue;

// 1 + 2 + 3 + 4
console.log(array1.reduce(reducer));
// expected output: 10

// 5 + 1 + 2 + 3 + 4
console.log(array1.reduce(reducer, 5));
// expected output: 15
```
