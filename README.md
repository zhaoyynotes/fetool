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
apply接收两个参数，第一个参数是函数上下文this,第二个参数为函数参数通过数组形式传入。
```markdown
allName.apply(obj,['我是','前端']) //我的全名是我是一个前端 this指向obj
```

## bind
bind接收多个参数，第一个是bind返回值返回值是一个函数上下文this,不会立即执行。
```markdown
let obj = {
  name:"一个"
}
function allName(fname,lname,flag){
  console.log(this)
  console.log(`我的全名${fname}${this.name}${lname}我的座右铭是${flag}`)
}
allName.bind(obj) //不会立即执行
let fn = allName.bind(obj);
fn('我是','前端','好好学习天天向上')

//也可以这样用，参数分开传。bind后的函数函数默认排在原函数参数后边
fn = allName.bind(obj,"你是")
fn('前端','好好学习天天向上')
```

## 实现call
