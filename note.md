



### 7.7 日志

###### 1. 复习 5.md 关于flex布局的相关内容

###### 2. 重新检查和修改之前的作业

###### 3. 复习前面的内容和要求

###### 4. 重要布局 仿demo-flex-01 （容器[container]，上端[top]高度固定由内容撑开，下端内容[自适应）固定基础布局

```css
.container,
html,
body {
    /* box */
    margin: 0;
    padding: 0;
    /* content */
    height: 100%;
}

.container {
    /* box */
    /* position */
    position: relative;
    bottom: 0;
    display: flex;
    flex-direction: column;
    flex-wrap: wrap;
    /* content */
}

```

容器设置flex布局，方向垂直，这是flex的基本内容，之后只设置下端内容的flex：1,上端就用内容撑开

```css
main {
    /* box */
    padding: 25px;
    /* position */
    flex: 1;
    display: flex;
    flex-direction: column;
    overflow: auto;
    /* content */
    height: 100%;
    background-color: #EEEEEE;
}


```

### 7.8 日志

###### 1. 学习了非常重要且实用的布局 Grid 网格布局 

###### 2. 关于伪类的更多用法

​	

```html
<body>
	<div class="father">
        <div class="son"></div>
        <div class="son"></div>
        <div class="son"></div>
    </div>
</body>
    
```

借助伪类以及其他选择器，可以让父元素控制子元素CSS

仿照QQ音乐的demo中的方法实现

```css
.item-top:hover>.item-mask {
    /* content */
    background-color: black;
    opacity: 0.25;
}

.item-top:hover>.mask-img {
    /* content */
    opacity: 1;
    transform: scale(1.3);
}

.item-top:hover>.item-img {
    /* content */
    /* aniamtion */
    transform: scale(1.07);
}
```

###### 3. 依旧是QQ音乐demo中的，鼠标hover到img上时，img局部放缩，大小不变。



```html
<div>
    <img></img>
</div>
```

看以来要js，实际上就把img 随便装到一个容器内，div固定宽高，并设置overflow。至于img，肯定是有transition和transform

```
div {
	overflow: hidden;
	width: 100px;
	height:100px
}
```

### 7.9 日志

###### 1. 按照要求修正了flex的作业

###### 2. 复习一下 JS 的设计模式



### 7.11-12 周末



### 7.12 日志

###### 1. Grid 高级布局

###### 2. 响应式布局

【disable cache】 Network里禁止缓存

Grid内部item区域控制: grid-template-areas  ;  grid-area

###### 3. Rem 的使用

###### 4. 完成响应式页面task的编写



### 7.13 日志

###### 1. Es6 知识回顾

###### 2. 完成ES6 相关基础内容。

### 7.14 日志

###### 1.  JS 中的数字问题 0.1+0.2 ！= 0.3 好像跟储存有关

###### 2. 关于异步操作的问题，这个细说的话很多，要看<Nodejs设计模式> 那本书。

目前的异步流程控制 主要有纯JS、Generator，promise，来解决。

流程分为 串行执行、并行执行，其中并行分为有限制和无限制。。

看完在继续写吧...（坑）



### 7.15 日志

###### 1. 油猴 插件 用法编写和发布自己写的浏览器插件

有必要学一下--写一个取边框广告的脚本

######  2.  一个项目的基本步骤

```js
git init
npm init -y
tsc --init

tsc-w  //编译 
```

设置source的编译后文件夹

继承 Interface 类

### 7.16 日志

1. 今天没什么特别的，把task完成就行



### 7.19日志

###### 1. VS code 插件好像对type/babel类型的文件有影响，最好不用CSS-HTML-formation这个美化插件

###### 2. 如果State的某个状态值是复杂结构，可以直接修改某个属性，但是页面数据不会更新，仍然需要手动调用

```js
this.state.XXX.X=XX

this.setState({
    XXX:XXX
})

```

###### 3. 感觉React基础部分不是很难



### 7.20 日志

###### 1.  TS 可索引类型

```
interface StringArray {
  [index: number]: string;
  //length:number
}

let myArray: StringArray;
myArray = ["Bob", "Fred"];

let myStr: string = myArray[0];
```

- 之前用策略模式改写表单验证的时候，无法遍历装有函数的数组，就是这个原因,不全是，要添加签名。

###### 2. 关于fetch的请求问题

1. 服务端必须允许header

   ```
    res.setHeader('Access-Control-Allow-Origin', '*')
    res.setHeader('Access-Control-Request-Method','*');
    //****************************** */
    res.setHeader('Access-Control-Allow-Headers', 'Origin, X-Requested-With, Content-Type, Accept');
   ```

2. 客户端的细节问题

   response无法直接访问，只能按键值对访问

   ```
   fetch('http://127.0.0.1:3280/api/add',{
           method: 'POST', // or 'PUT'
           body: JSON.stringify(form), // data can be `string` or {object}!
           headers: {
             'Content-Type': 'application/json'
           },
           mode: 'cors'
       })
       .then((res)=>{
           return res.json();
       })
       //***                 */
       .then(response => alert('Success:'+ response.id))  //直接返回response不行，是undefined
       .catch(error => console.error('Error:', error))
   ```




### 8.28 日志

###### 1. 备忘* 这是开学前的、单独的对7月实习和8月未完成的实习的学习，开学之后有别的任务。

###### 2.使用create-react-app快速搭建应用

```
Success! Created react-app at D:\WPS-homework\xuhao\Task-8.28\react-app
Inside that directory, you can run several commands:

  yarn start
    Starts the development server.

  yarn build
    Bundles the app into static files for production.

  yarn test
    Starts the test runner.

  yarn eject
    Removes this tool and copies build dependencies, configuration files
    and scripts into the app directory. If you do this, you can’t go back!

We suggest that you begin by typing:

  cd react-app
  yarn start

Happy hacking!
```

yarn start 用来启动项目

###### 2.1 生成项目的基本结构解读

`public/index.html`页面入口文件,
`src/App.js`根组件，
`src/App.css`根组件样式文件，
`src/index.js`程序入口文件，
`src/index.css`页面样式文件，
`App.test.js`和`serviceWorker.js`暂时不会使用，可以删除

.js和.tsx同理

###### 2.2 遇见的问题

1.Typescript的版本和React版本兼容问题，Typscript版本需要4.1.0以上

2.hook和mobx的配合使用

1. 创建store

```javascript
import { action, observable } from 'mobx';

class Store {
    @observable
    count = 1;
    
    @action
    setCount = () => {
        this.count++;
    }
}
export const store = new Store();
```

1. 注入store，这样既可以在class中使用，也可以在hooks中使用了

```javascript
// 注入store
import { Provider } from 'mobx-react';
import {store} from './store';

<Provider store={store}>
  <Demo />
</Provider>
```

1. 在class中使用

```javascript
import React, { Component } from 'react';
import { inject, observer } from 'mobx-react';

@inject('scope')
@observer
class Demo1 extends Component { 
    render() {
        return <div>{this.props.count}</div>
    }
}
```

​	2.在hooks中使用

```javascript
import React from 'react';
import { useObserver, Observer, useLocalStore } from 'mobx-react';
import {store } from './store';

// 方法1
function Demo2() { 
    const localStore = useLocalStore(() => store);
    return useObserver(() => <div onClick={localStore.setCount}>{localStore.count}</div>)
}

// 方法2，更新Observer包裹的位置，注意这里包裹的必须是一个函数
function Demo3() { 
    const localStore = useLocalStore(() => store);
    return <Observer>{() => <span>{localStore.count}</span>}</Observer>
}
  
//但是方法一存在报错问题
//解决办法：在tsconfig.ts配置文件中添加 "experimentalDecorators": true 即可
    
  
```

3. store和页面刷新的关系

   为什么store的值改变了，但是组件不刷新.

   render期间Mobx观察者注册失效BUG。

    `useLocalStore` 将要废弃 !!

   解决：

   ​	1.const 一个[color,setColor] 但意义不大

   ​	2.将颜色信息存储在浏览器的cookie里面 (麻烦，但是没有问题)

   ​	3.Hook 与 mobx结合,有些人的写法。

   声明一个Store与之前没有变化，使用的时候发生了变化

   ```tsx
   import { useLocalObservable, useObserver, Observer } from 'mobx-react';
   import Store from './Store'
   
   export function app() {
     let localStore = useLocalObservable(() => Store); 
     
     return useObserver(()=>(<div>...</div>)) //第一种方法，不过好像在mobx6弃用了
     return <Observer>{()=>(<div>.....</div>)}</Observer> //现在更推荐这种写法
   }
   ```

    4. **真正的解决办法****************************

       ```js
       import React from "react"
       import ReactDOM from "react-dom"
       import { makeAutoObservable } from "mobx"
       import { observer } from "mobx-react-lite"
       
       class Timer {
           secondsPassed = 0
       
           constructor() {
               makeAutoObservable(this)
           }
       
           increaseTimer() {
               this.secondsPassed += 1
           }
       }
       
       const myTimer = new Timer()
       ```

       要加

       ```
       constructor() {
               makeAutoObservable(this)
       }
       ```

       之后就可以看到页面组件会随store的改变而更新了

###### 3. Axios

axios极大的简化了http请求的程序，并且与fetch相比，没有出现跨域请求失败的现象。

### 8.28 日志

###### 1. 现在快速创建一个标准的React运用步骤

```
npx create-react-app react-app --template typescript
npm i yarn -g
//安装所有依赖：
//或者yarn  
yarn install
//运行 注意由于新建的项目路径改变了，需要重新cd
yarn start

```

### 8.29 日志

###### React项目，“知乎”网站

### 8.30 日志

###### 1. 打算先写完 登录和注册页面用antd的组件
