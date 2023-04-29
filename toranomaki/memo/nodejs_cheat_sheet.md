## 1.syntax
|details|command|
|:--|:--|
|Comment out|//|
|Comment out|/*   */|
|Export console|console.log("test");|
|Definition Variable|var hoge;|

## 2.if
```
if (conditions === 'symfoware') {
    console.log('if block')
} else if (conditions === 'symfo') {
    console.log('else if block')
} else {
    console.log('else block')
}
```

## 3.for
```
const array = ['hoge', 'piyo', 'huga'];
for (let i = 0; i < array.length; i++) {
    console.log(array[i])
}

const array = ['hoge', 'piyo', 'huga'];
for (const index in array) {
    console.log(index)
}
```

## 4.function
```
console.log(fn1())
function fn1() {
  return 'text1'
}

// 変数に入れる書き方①
// 宣言より前で呼び出すことはできない
var fn2 = function fn2() {
  return 'text2'
}
console.log(fn2())
```
