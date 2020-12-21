## 手写call、apply、bind

## call
call接收多个参数，第一个是函数上下文，也就是this,后面的参数是函数本身的参数。
```markdown
let obj = {
  name:"一个"
}
function allName(fname,lname){
  console.log(this)
  console.log(`我的全名${fname}${this.name}${lname}`)
}
allName('我是','前端')
allName.call(obj,'我是','前端')

Window {parent: Window, opener: null, top: Window, length: 1, frames: Window, …}
我的全名我是前端
{name: "一个"}
我的全名我是一个前端
```

## apply
apply接收两个参数，第一个参数是函数上下文this,第二个参数为函数参数通过数组形式传入
```markdown
allName.apply(obj,['我是','前端']) //我的全名是“我是一个前端” this指向obj
```
