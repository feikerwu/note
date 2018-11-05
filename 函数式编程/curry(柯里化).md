# curry(柯里化)
### 什么是柯里化 
柯里化是指传递一部分参数来调用它，返回一个函数去处理剩下的函数。
比如
```js
const fn = function(a, b, c) {
	return a * b * c
} // 可以转化为以下的柯里函数

const fn = function(a) {
		return (b) => {
			return (c) => {
				return a * b * c 
			}
}
```

### 为什么要用柯里化
柯里化函数可以策略性的将要操作的数据放到最后一个参数，只给函数传入部分参数的局部调用在增加代码可读性的同时可以减少样本文件代码

### 通用的柯里化

```js
const curry = (fn, ...args) => (..._agrs) => fn(...args, ..._args)
```



#frontend/函数式编程