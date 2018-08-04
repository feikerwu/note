## 随机返回非黑名单内的数字

给定一个数字区间[0, N)， 以及一个黑名单列表B, 随机返回一个数字number，使得number不在黑名单内



##### 解法

 令B_length = B.length, range_top = N - B.length， 将每个出现在[0. range_top]中且在黑名单中的数字x

映射到(range_top, N)中且不出现在黑名单的数字y

```javascript
// 返回的随机数
randomNumber = Math.random(0, 1) * range_top
result = map(randomNumber) ? map(randomNumber) : randomNumber
```



##### 代码

```javascript
/** 给定区间[0, N), 以及一个黑名单B，实现一个函数，随机返回区间内且不在黑名单中的数字
 * @param {number} N
 * @param {number[]} blacklist
 */
var Solution = function(N, blacklist) {

}

Solution.prototype.createNew = function(N, blacklist) {
    const map = Object.create(null)
    const randomTop = N - blacklist.length
    let index = N - 1
    blacklist.map(item => {
        if (item < random_top) {
            map[item] = numberOverRange()
        }
    })

    function numberOverRange() {
        while(blacklist[index--])
        return index
    }

    this.randomTop = randomTop
    this.map = map

    return this
}

/**
 * @return {number}
 */
Solution.prototype.pick = function() {
    let randomNum = Math.floor(Math.random(0, this.randomTop) * this.randomTop)
    return this.map[randomNum] ? this.map[randomNum] : randomNum
};


var obj = Object.create(Solution.prototype).createNew(1, [])
console.log(obj.pick())



```

