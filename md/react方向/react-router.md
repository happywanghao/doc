##react

creat-react-app react-demo
新建一个react环境


####ReactDOM
render(,)


jq的$('.class')
原生的document.querySelector('body #root')
原生的document.querySelectorAll('body #root')


第三个参数是回调函数 渲染成功的时候执行
#### JSX语法

* 直接在js里写html；

* 组件化开发

* JSX语法需要BABEL进行编译转,转换成React.createElement()

* 相邻的JSX元素必须被包裹在一个闭合的标签内；

* Adjacent JSX elements must be wrapped in an enclosing tag

* 每一个标签必须闭合,单独的标签写成自闭和；

* 加class的时候写成className

* for 也是关键字换成htmlFor

* 区分大小写；

* 在JSX语法中可以嵌入变量和求值表达式，可以写js语句,方式是用{}包裹
 let a='ssss'

* 图片先当做模块导入 再引入




 #### React组件有三种
 1.
 ```
  let Hello =React.createClass({
   render:function(){
     return (
       <div>
         <h1>    我是第一种组件的创建方式，即将废弃</h1>
       </div>
     )
   }
 })
 ReactDOM.render(<Hello></Hello>,document.querySelector('#root'))

 ```
 2.
 ```
 function World(){
   return (
     <p>我是个p</p>
   )
 }
 function Hello (){
   return (<h1>我是第二种组件的创建方式而且<World/>返回值必须是JSX elements</h1>)
 }
 ReactDOM.render(<Hello/>,document.querySelector('#root'))

 ```

3.
## render(){}===render:function(){}


```
class Hello extends React.Component{
  render(){
    return(
      <div>我是第三种方式最常用</div>
    )
  }
}
ReactDOM.render(<Hello/>,document.querySelector('#root'))

```


#### .gitignore文件是屏蔽上传文件名的


### 对象的合并  Object.assign() 返回值是更改后的第一个对象  有相同的属性后者会覆盖前者
```
let a={
  a1:1
}
let b={
  b1:2
}
let c={
  c1:3
}
Object.assign(a,b,c)
console.log(a)

```

图片在css里正常引入



#### setState是异步操作


state   是对象
setState 是方法



### vw 可视窗口宽度  vh 可视窗口高度



###  console.dir()  查看详细信息


作业好多视频 和分页器


### includes()  检索数组和字符串的



### state可以放一个箭头函数   setState 是异步操作




# react-props  

props 是一个对象

父子间沟通  父-->子



# 生命周期函数

### Mounting
### These methods are called when an instance of a component is being created and inserted into the DOM:

* constructor()
 在这里用porps要这么写;
```
constructor(props) {
  super(props);
  this.state = {
    color: props.initialColor
  };
}
```
* componentWillMount()
* render()
* componentDidMount()


### Updating
### An update can be caused by changes to props or state. These methods are called when a component is being re-rendered:

* componentWillReceiveProps()  接受一个参数  nextProps
* shouldComponentUpdate()  接受两个参数  nextProps,nextState   必须return  返回一个布尔值
* componentWillUpdate()
* render()
* componentDidUpdate()  接受两个参数 nextProps,prveState

### Unmounting
### This method is called when a component is being removed from the DOM:

* componentWillUnmount()



### 修改props或者通过setState修改state会触发组件更新 并且props必须父级通过setState修改并且执行render方法;



## from


```
<form action='https://api.github.com' method='GET'>
  <input type="text" name='age'/>
  <button>提交</button>
</form>
```

  * e.target.reset() 清空表单数据


## 用普通value  



  ```
  class Form extends React.Component{
    constructor(){
      super()
      this.state={
        data:5
      }
    }
    handleSuBmint(e){
      e.preventDefault()
      // console.log(e)
      e.target.reset()
    }
    handleChange(e){
      console.log(e.target.value)
      this.setState({
        data:e.target.value
      })
    }
    render(){
      return (
        <form onSubmit={this.handleSuBmint.bind(this)}>
          <input onChange={this.handleChange.bind(this)} type="text" name='age' placeholder='name' value={this.state.data}/>
          <button>提交</button>
        </form>
      )
    }
  }

  ```

##  dafaultValue



### 对象的属性名也可以用变量不过得用中括号包起来






###  str.trim()   去掉字符串前后的空格


  <input type='number'/>
  h5新增  只能输数字 挺好使
  input type='email'
  只能输邮箱

  h5 新增很多表单元素
### JSON  
把正常的js数据转成字符串   JSON
把json转成正常数据类型
```
let obj = {
  name:'wanghao'
}
console.log(JSON.stringify(obj))
let jsonStr = '{"name":"wanghao"}'
let obj2=JSON.parse(jsonStr)
console.log(obj2)
```


localStorage.aaa="666"
把666存到缓存
存的时候会自动转成字符串
localStorage.getItem('aaa')  读取
localStorage.setItem('ooo',888) 设置  
localStorage.removeItem('aaa')删除
