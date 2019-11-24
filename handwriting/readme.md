```js
// 节流
function debounce(fn, delay = 200) {
  var timer;
  return function(...args) {
    timer && clearTimeout(timer);
    timer = setTimeout(() => {
      fn.apply(this, args);
    }, delay);
  };
}
```

```js
// 函数柯里化
function currySum(...args) {
  var res = args.reduce((a, b) => a + b);
  return function(...nextAtgs) {
    if (nextAtgs.length === 0) return res;
    return currySum(res, ...nextAtgs);
  };
}
console.log(currySum(1)(2, 4, 5, 6, 7)());
```

```js
// 生成一个任意范围的随机数
function random(min, max) {
  return (Math.random() * (max - min + 1) + min) | 0;
}
```

```js
function random(min, max) {
  return (Math.random() * (max - min + 1) + min) | 0;
}
// 打乱数组
function shuffle(arr) {
  arr = arr.slice(0);
  for (var i = 0; i < arr.length; i++) {
    var index = random(0, arr.length - 1);
    [arr[index], arr[i]] = [arr[i], arr[index]];
  }
  return arr;
}
console.log(arr);
console.log(shuffle(arr));
```
