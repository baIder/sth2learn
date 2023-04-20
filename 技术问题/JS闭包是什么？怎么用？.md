# JS闭包是什么？怎么用？

## 是什么

闭包是JS的一种语法特性
闭包=某函数+自由变量（不是全局变量，也不是该函数的局部变量）

## 怎么做

```javascript
//方式1
{
  let count
  function add(){
    count += 1
  }
}

//方式2
const add2 = function (){
  let count
  return add (){
    count +=1 
  }
}()
```

## 解决了什么问题

1.  避免污染全局环境
2.  **提供对局部变量的间接访问**
3.  维持变量，使其不被垃圾回收
