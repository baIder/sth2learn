# JS的立即执行函数

1.  是什么

    声明一个函数并立即执行
2.  怎么做

```javascript
(function (){console.log(1)}());
!function (){console.log(1)}();
~function (){console.log(1)}();
+function (){console.log(1)}();
-function (){console.log(1)}();

const a = function (){console.log(1)};
```

1.  解决了什么问题

    在ES6之前创建局部作用域
2.  优点

    兼容性好
3.  缺点

    丑
4.  如何解决

    用ES6的block+let
