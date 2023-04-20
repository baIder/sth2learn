# JS 的 this

this是`.call()`的第一个参数

`f(p)`相当于`f.call(undefined, p)`

`obj.child.say('hi')` 相当于 `obj.child.say.call(obj.child, 'hi')`
