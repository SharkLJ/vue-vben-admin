1. 以下代码输出什么？
```const promise1 = new Promise((resolve, reject) => {
  console.log('promise1')
})
console.log('1', promise1);
```
a
  promise1
  1 Promise { <pending> }
b
  1 Promise { <fulfilled> }
  promise1
c
  1 Promise { <rejected> }
  promise1
d
  promise1
  1 Promise { <fulfilled> }

2. 以下代码输出什么？
```
const promise = new Promise((resolve, reject) => {
  console.log(1);
  resolve('success')
  console.log(2);
});
promise.then(() => {
  console.log(3);
});
console.log(4);
```
a
  1243
b
  1423
c
  1234
d
  1432

3. 以下代码输出什么？
```
const promise = new Promise((resolve, reject) => {
  console.log(1);
  console.log(2);
});
promise.then(() => {
  console.log(3);
});
console.log(4);
```
a
  124
b
  1234
c
  1243
d
  123

4. 以下代码输出什么？
```
const promise1 = new Promise((resolve, reject) => {
  console.log('promise1')
  resolve('resolve1')
})
const promise2 = promise1.then(res => {
  console.log(res)
})
console.log('1', promise1);
console.log('2', promise2);
```
a
  promise1
  1, Promise { 'resolve1' }
  2, Promise { <pending> }
  resolve1
b
  promise1
  1, Promise { <resolve> }
  2, Promise { <fulfilled> }
  Promise { <fulfilled> }
c
  promise1
  1, Promise { <fulfilled> }
  2, Promise { <fulfilled> }
  resolve1
d
  promise1
  1, Promise { <fulfilled> }
  2, Promise { <pending> }
  resolve1

5 以下代码输出什么？
```
const fn = () => (new Promise((resolve, reject) => {
  console.log(1);
  resolve('success')
}))
fn().then(res => {
  console.log(res)
})
console.log('start')
```
a
  start
  1
  success
b
  start
  1
  success
c
  1
  success
  start
d
  1
  start
  success

6 以下代码输出什么？
```
const fn = () =>
  new Promise((resolve, reject) => {
    console.log(1);
    resolve("success");
  });
console.log("start");
fn().then(res => {
  console.log(res);
});
```
a
  start
  1
  success
b
  start
  1
  success
c
  1
  success
  start
d
  1
  start
  success
  


简答题：
1. 标准盒子模型和怪异盒子模型(IE盒子)有什么区别
  标准盒子模型的width/height与content的width/height相同
  IE盒子模型的width/height = content的width/height +padding+border
2. Tree Shaking 是什么，有什么作用
通过清除多余代码方式来优化项目打包体积的技术，
就是在保持代码运行结果不变的前提下，去除无用的代码
可以减少程序体积、减少程序执行时间、便于将来对程序架构进行优化
3.vue中的trim修饰符有什么用
  <input type="text" v-model.trim="value">
  自动过滤用户输入value的首尾空格字符，而中间的空格不会过滤
