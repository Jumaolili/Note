



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

axios极大的简化了http请求的程序，并且与fetch相

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

###### 2. 今天不再使用实习的git仓库，转而使用github的我的仓库

github项目上传流程 简书 有讲

https://www.jianshu.com/p/c70ca3a02087

###### 3. 今天出现的问题

**使用yarn安装**   

yarn add @types/react-router-dom@^5.1.8

**配置less**

初始步骤，暴露配置文件

```
yarn eject
```

第一步：

在webpack.config.js文件(暴露后在config文件夹下)中设置如下:

```
66行 插入less更改:
const lessRegex = /\.less$/;
const lessModuleRegex = /\.module\.less$/;
500行，插入：
{
    test: lessRegex,
    exclude: lessModuleRegex,
    use: getStyleLoaders({
    importLoaders: 3,
    sourceMap: isEnvProduction
    ? shouldUseSourceMap
    : isEnvDevelopment,
    }, "less-loader"),
    // Don't consider CSS imports dead code even if the
    // containing package claims to have no side effects.
    // Remove this when webpack adds a warning or an error for this.
    // See https://github.com/webpack/webpack/issues/6571
    sideEffects: true,
    },
    // Adds support for CSS Modules (https://github.com/css-modules/css-modules)
    // using the extension .module.css
    {
    test: lessModuleRegex,
    use: getStyleLoaders({
    importLoaders: 3,
    sourceMap: isEnvProduction
    ? shouldUseSourceMap
    : isEnvDevelopment,
    modules: {
    getLocalIdent: getCSSModuleLocalIdent,
    },
    }, "less-loader"),
},
```

第二步：

安装相应的less包

```
yarn add less less-loader@5.0.0//在这里安装的less-loader的包是低版本 高版本可能存在不兼容的问题
```

第三步：

配置全部变量（在react-app-env.d.ts文件里加入）

```
declare module '*.less' {
  interface Style {
    [propName: string]: string
  }
  const style: Style
  export default style
}
```

第四步：

最好是重新yarn一下，

```
文件名字为style.module.less
引入 import style from './style.module.less'
```

**antd组件的样式问题**

antd的组件无法识别less，所以需要按照原有的模板写css



### 8月31日

###### 1. 经过考虑，沿用之前项目的server模板

###### 2. express mongdb

###### 3. 今天需要完成服务器的初步搭设，以及home页面的书写

###### 4.遇到的问题



**1. hook组件登陆跳转**

useHistory 钩子允许您访问可能用于导航的历史实例。

[![复制代码](https://common.cnblogs.com/images/copycode.gif)](javascript:void(0);)

**解决**

```
import { useHistory } from "react-router-dom";

function HomeButton() {
  let history = useHistory();

  function handleClick() {
    history.push("/home");
  }

  return (
    <button type="button" onClick={handleClick}>
      Go home
    </button>
  );
}
```



### 9月2日

###### 1. 出现的问题

无法解决 react DnD的使用

解决了，但是依旧挂了，悲伤~~



### 9月5号

今天正式开始做双创的项目，一个人，微信app和PC网页端。

明天做最后一个面试，弄完就埋头做，白天复习。

做完项目后，九月基本结束了，考虑转行了，我可能不适合计算机，也拿不到那么高的工资。



### 9月9日

### 数据结构是解决问题的过程中使用的容器

在这里我们还要向大家介绍一个概念：**数据结构是缓存**。

| 数据结构                       | 应用场景                                                     |
| ------------------------------ | ------------------------------------------------------------ |
| 栈                             | 符合「后进先出」的规律                                       |
| 队列                           | 符合「先进先出」的规律                                       |
| 哈希表（散列表）               | 实现「快速存取」数据的功能                                   |
| 二分搜索树（红黑树、B 树系列） | 维护了一组数据的顺序性，得到一个数据的上下界                 |
| 并查集                         | 用于处理不相交集合的「动态」连接问题                         |
| 优先队列                       | 有「动态」添加、删除数据且需要获得最值的场景                 |
| 字典树（Trie）                 | 用于保存和统计大量的字符串和相关的信息                       |
| 线段树                         | 处理数组的区间信息的汇总（求和、最值等）、单点更新、区间更新问题 |
| 树状数组                       | 处理数组的前缀和、单点更新、区间更新问题                     |

### 9月13日

###### 1. 组件内定义变量刷新问题

需要在组件外定义需要的变量，但是如果组件多次引用，将可能存在变量污染问题



### 9月14日

###### 1. 拖拽组件的传值问题

不知道为什么item里面传的值永远是最开始的state，如果state后面发生了改变，也是传原来的state，奇怪？？

```
// 使用 useDrag
    const [, drager] = useDrag(
        ()=>({
            type:'Card',
            item:{type:'Card',title:title,content:content,mark:props.data.mark,father:props.father},
            collect: (monitor) => ({
                isDragging: monitor.isDragging(),
            }),
            end:(item, monitor)=>{
                //console.log('end')
            },
            isDragging:(monitor)=>{
                //console.log('dragging')
            }
        })
    )
```

明明state已经改变了，但是item里面传的值依旧是初始值，可能在拖拽时，**组件估计重新刷新**了。









###### 2. 父组件触发子组件事件

**函数式和hooks写法**
其实下面的缺点基本不算缺点了，因为函数式写法，下面算是简单的了。使用forwardRef只会让你的组件定义的更复杂

优点：
1、写法简单易懂
2、假如子组件嵌套了HOC，也可以指向真实子组件
缺点：
1、需要自定义props属性
2、需要自定义暴露的方法
**父组件**

```
import React from 'react';
import Child from './Child';

const Parent = () => {
  let ChildRef = React.createRef();

  function handleOnClick() {
    ChildRef.current.func();
  }

  return (
    <div>
      <button onClick={handleOnClick}>click</button>
      <Child onRef={ChildRef} />
    </div>
  );
};

export default Parent;


```

**子组件**

```
import React, { useImperativeHandle } from 'react';
import { withRouter } from 'react-router-dom';

const Child = props => {
  //用useImperativeHandle暴露一些外部ref能访问的属性
  useImperativeHandle(props.onRef, () => {
    return {
      func: func,
    };
  });
  function func() {
    console.log('执行我');
  }
  return <div>子组件</div>;
};

export default withRouter(Child);


```



###### 3. 关于Mobx的问题

```
import {useLocalObservable, useObserver, Observer} from 'mobx-react';
import { store } from "./store/store";

let localStore = useLocalObservable(() => store);
// store.XXX   store.setXXX(XXX)
```

###### 4. 关于less配合媒体查询

刚开始，可能有点延迟，刷新几次就好了

```
@media screen {
    @media (max-width: 762px) {
        .index {
            .nav {       
                background-color: #272A33;
                img {
                    width: 182px;
                    height: 50xpx;
                }
            }
        }
        
    }
}
```



### 9月16日

###### 1. 背景图片 铺满

```
background-size: contain/cover;
```

注意这个属性

###### 2. 响应式开发最好结合rem，要不然修改px巨特么麻烦





### 9月17日

###### 1. 类组件和函数时组件

**类组件** ： 动态组件，一般用于有交互或者数据修改的组件

**函数组件** ： 静态组件，一般用于静态页面数据展示，但在16.8后，react引入了React Hook的setState,就可以编写带有状态的组件

###### 2. 生命周期

componentDidMount和componentWillUnmount是生命周期函数，useEffect作用就是代替他们

```
React.useEffect(()=>{
	return ()=>{
	
	}
},[])
```





### 9月19日

###### 1. 还在编写index的响应式布局页面

进度有点慢，毕竟不是全职在做，晚上才有时间

响应式布局界限值

| 762px     |      |
| --------- | ---- |
| 920px     |      |
| 1366px    |      |
| >= 1920px |      |

还有尽量配合rem使用

```
html {
	font-size : 10px ;
}
```





### 9月21日

###### 1. VS code 调试 javascript代码 

```json
{
    // Use IntelliSense to learn about possible attributes.
    // Hover to view descriptions of existing attributes.
    // For more information, visit: https://go.microsoft.com/fwlink/?linkid=830387
    
    "version": "0.2.0",
    "configurations": [{
            "name": "谷歌浏览器", //运行html文件，用谷歌浏览器打开
            "type": "chrome",
            "request": "launch",
            "url": "${file}",
            "sourceMaps": true,
            "webRoot": "${workspaceRoot}"
        },
        {
            "name": "nodeLauch", //单独调试js，即可以直接运行js
            "type": "node",
            "request": "launch",
            "program": "${file}", //这个配置成你要调试的文件、${file}当前打开的文件
            "stopOnEntry": false,
            "args": [],
            "cwd": "${workspaceRoot}",
            "runtimeExecutable": null,
            "runtimeArgs": [
                "--nolazy"
            ],
            "env": {
                "NODE_ENV": "development"
            },
            "console": "internalConsole",
            "preLaunchTask": "",
            "sourceMaps": false,
            "outDir": null
        }
    ]
}

```





### 9月23日

###### 1. 高阶组件的简单尝试

```javascript
import React from 'react';
import ReactDOM from 'react-dom';
import { useDrop, DropTargetMonitor } from 'react-dnd';
import {useLocalObservable, useObserver, Observer} from 'mobx-react';


// 高阶组件
function HOC(WrappedComponent) {
  return class extends React.Component {
    constructor(props) {
      super(props);
      this.state = {
        name: 'new',
      };
      this.onChange = this.onChange.bind(this);
    }
    
    onChange = (event) => {
      this.setState({
        name: event.target.value,
      })
    }

    onClick=(event)=>{
        alert('hello');
    }
    
    render() {
		//拦截并重写props,最后注入
      const newProps = {
        name: {
          value: this.state.name,
          onChange: this.onChange,
          onClick:this.onClick
        },
      };
      //属性注入
      return <WrappedComponent {...this.props} {...newProps} />;
    }
  };
}

// 最终我们返回一个被“强化”过后的组件
@HOC   //重点步骤
class Example extends React.Component {
  render() {
    return <input name="name" {...this.rops.name} />;
  }
}

export default Example


```







### 9月24日

###### 1. 弄清楚Hooks函数的生命周期

###### 2. 完成Login的编写

###### 3. 完成Register页面的部分（也许）





### 9月28日

###### 1. Context 的使用

```javascript
// context方式实现跨级组件通信 
// Context 设计目的是为了共享那些对于一个组件树而言是“全局”的数据
const BatteryContext = createContext();
//  子组件的子组件  
class GrandChild extends Component {
    render(){
        return (
            <BatteryContext.Consumer>
                {
                    color => <h1 style={{"color":color}}>我是红色的:{color}</h1>
                }
            </BatteryContext.Consumer>
        )
    }
}
//  子组件
const Child = () =>{
    return (
        <GrandChild/>
    )
}
// 父组件
// 使用创建的 BatteryContext，创建BatteryContext.Provider标签，在该标签内，所有组件共享 value中的变量 { color }
class Parent extends Component {
      state = {
          color:"red"
      }
      render(){
          const {color} = this.state
          return (
          <BatteryContext.Provider value={color}>
              <Child></Child>
          </BatteryContext.Provider>
          )
      }
}

```





### 9月29日

###### 1.  Axios 的跨域问题

没有解决....

换成fetch了，原来解决过fetch的问题。







### 10月2日

###### 1.  子路由跳转问题

**1、React路由介绍**

**1.1、单页面应用**

单页面得特点：只需要加载一次主页面，通过局部刷新，就可以实现跳转或者切换页面

优点：加载速度快，用户体验比较好

缺点：

- 第一次加载比传统要慢一点
- 不利seo
- 页面相对复杂
- 返回键

**1.2、安装react-router-dom**

在项目命令行中，执行

```
cnpm install react-router-dom -S
```

下载到生产环境的依赖中。

在组件中通过对象的解构方式去获取到`react-router-dom`内置组件，在组件中，按需引入内置组件，在页面中进行使用：

- HashRouter表示一个路由的根容器，将来所有的路由相关的东西，都要包裹在HashRouter里面，而且一个网站中，只需要使用一次HashRouter就好了；
- Route表示一个路由规则，在Route上，有两个比较重要的属性，path，component
- Link表示一个路由的链接，属性to

```
import {HashRouter,Route,Link} from 'react-router-dom'
复制代码
```

代码示例：

```tsx
render(){
        return (
            <HashRouter>
                <div>
                    <h1>这是网站的根目录</h1>
                    <hr />
                    <Link to="/home">首页</Link>&nbsp;&nbsp;
                    <Link to="/movie/">电影</Link>&nbsp;&nbsp;
                    <Link to="/about">关于</Link>
                    <hr />
                    <Route path="/home" component={Home} ></Route><hr/>
                    <Route path="/movie" component={Movie} exact></Route><hr/>
                    <Route path="/about" component={About}></Route><hr/>
                </div>
            </HashRouter>
        );
    }

```

当使用HashRouter把APP根组件的元素包裹起来之后，网站就已经启用路由了，在一个HashRouter中，只能有唯一的一个根元素。 在一个网站中，只需要使用唯一的一次`<HashRouter></HashRouter>`就行了。

Route创建的标签，就是路由规则，其中path表示要匹配的路由，component表示要展示的组件。Route具有两种身份：1.它是一个路由匹配规则；2.它是一个占位符，表示将来匹配到的组件都放到这个位置

需要注意的地方

- Route 组件path地址是以/开头 ，配置component属性，是显示的组件，这个属性不可以大写
- Route组件可以单双标签使用，单标签需要/结尾，双标签不可以在中间写入别的东西
- Link to属性的地址也是/开头，Link在页面渲染的是a标签

作者：柯晓楠
链接：https://juejin.cn/post/6844904111691792398







###### 2. 子路由 子组件样式问题

```js
<NavLink
  to="/faq"
  activeClassName="selected"
>FAQs</NavLink>
//换成NavLink就行了

```

##### `activeClassName`

当某个 route 是激活状态时，`<Link>` 可以接收传入的 className。失活状态下是默认的 class。

##### `activeStyle`

当某个 route 是激活状态时，可以将样式添加到链接元素上。

但是Link好像更新了，不支持这两个，**需要换成最新的NavLink**



### 10月7日

###### 1.  导出interface类的问题

```typescript
//interface.ts

export interface Login_data {
    email:string,
    password:string
}
```



###### 2. TS 里面 传函数arguments问题

策略模式

```typescript
function stragegyFactory(checkList:any[]){    //检查策略组工厂
    let output:any=[];
    let index=1;
    if(!Array.isArray(checkList)){
        output.push({
            status:false,
            msg:'策略组checkList参数需要为数组'
        });
        return output;
    }
    for(let i in checkList){
        //分离策略组，策略和结果
        //执行每个策略组
        let check=checkList[i];
        if(!Array.isArray(check)){
            output.push({
                status:false,
                msg:'策略组checkList中每一项需要为数组[fn,...args]'
            });
            return output;
        }
        let fn=check[0];
        let result;
        let args;
        if(typeof fn !== 'function') {
            output.push({
                status:false,
                msg:`策略组第${index}项[fn,...args],fn必须为函数`
            });
            return output;
        }
        args=Array.prototype.slice.call(check,1)
        result=fn(...args);   
        if(typeof result == 'boolean'){
            let bool = result;
            result = {
                status: bool,
                msg:bool ? '' : `第${index}个策略没有通过`
            }
        }
        output.push(result);
        index++;
    }
    return output
}

```



###### 3. 阻止子组件无意义刷新--memo





### 10月8日

###### 1.  判断是否存在循环引用

```javascript
let a={
  student:null
}

let b= {
  teacher:1
}
a.student=b;

//JSON error
function isCircle(obj) {
  try {
    JSON.stringify(obj);
  } catch (error) {
    return true
  }
  return false
}

//Map
function isCircle_2(obj) {
  let parent=obj;
  let result=false;
  function check(obj) {
    if(result==true) return result;
    for(let i in obj){
      if(typeof obj[i] == 'object'){
        if(obj[i]==parent){
          result = true;
        }
        check(obj[i]);
      }
    }
  }
  check(obj);
  return result;
}


console.log(isCircle_2(a));
```





### 10月8日

###### 1. 是否可以自己做一个云盘？

###### 2. 细小的知识点

  1.

```html
<a>
	<img src='' title=''/>
    <p></p>
</a>
a标签内部可以放很多东西
```

2. symbol 不可被枚举
3. 表格的 cellspacing属性、col标签、colspan属性、rowspan属性



###### 3. 接昨天的问题

之所以每次输入都会导致Model的刷新是因为，父组件（Login）的state改变了，所以引起页面刷新，那么Model（子组件）也会刷新。



```typescript
const isEqual = (prevProps:any, nextProps:any) => {
    if (prevProps.msg !== nextProps.msg) {
        return true;
    }
    return false;
}


const Model_Fail_1 = React.memo(Model,isEqual)


export default Model_Fail_1;
```

但是，还是发生了刷新？？？

函数式组件果然还是由局限性问题



###### 4. 不能在fetch的参数里面拼接字符串，会报错

```typescript
await fetch(`${request.baseURL}+${url}+${search}`,{
            method: 'GET', // or 'PUT'
            headers: {
            'Content-Type': 'application/json;charset=utf-8'
            },
            mode: 'no-cors'
        })
```



###### 5. [typescript提示implicitly has an 'any' type，这个怎么解决？](https://segmentfault.com/q/1010000016082181)

不知道”有三种情况：

- 我不知道它具体是什么，但它一定有某某属性：用字面量声明类型，`{ x: string }`
- 我不确定它有什么属性，之后我会用`if`再仔细判断：声明为`unknown`类型
- 我自己有数，你别管了：声明为`any`类型

解决办法？

**tsconfig.json 中 添加"noImplicitAny": false,**



###### 6.  为什么编写的节流化函数会失效

猜想（正确）

当操作时同步且不会更改state的时候，节流函数生效；但是一旦更改state，引发刷新，则会使定时器刷新





### 10月10日

###### 1. 任务须知：

 	1. 阅读 React 开发文档
 	2. 看网课学习 Node 的库 Koa，学会编写后端代码
 	3. 计算机网络 
 	4. 浏览器原理
 	5. 浏览器 插件制作 脚本编写
 	6. LeeCode 算法
 	7. **需要在10月17日前完成 项目前端页面代码** 





###### 2. 阅读 React 开发文档

先从简单的教程开始回顾,在12：00之前完成简单教程

**还是Class 组件香**

**井字棋，五子棋是滑动窗口问题**

```javascript
Tools={
    chessWin:function(x,y,list) {
        //1. 定义滑动窗口
        //2. 水平 垂直 斜向 
        //3. 满足就返回win

        let cache =[list[x][y]];
        let temp_x=x,temp_y=y;
        //水平 改变y 
        while (temp_y>0&&cache.length<3&&list[x][temp_y-1]===list[x][y]) {
            cache.push(list[x][temp_y-1]);
            temp_y--;    
        }
        if(cache.length==3){
            return true;
        }else{
            temp_y=y;
        }
        while ((temp_y<list[x].length-1)&&cache.length<3&&list[x][temp_y+1]===list[x][y]) {
            cache.push(list[x][temp_y+1]);
            temp_y++;    
        }
        if(cache.length==3){
            return true;
        }else{
            temp_y=y;
        }
        cache =[list[x][y]];

        //垂直 改变x
        while (temp_x>0&&cache.length<3&&list[temp_x-1][y]===list[x][y]) {
            cache.push(list[temp_x-1][y]);
            temp_x--;    
        }
        if(cache.length==3){
            return true;
        }else{
            temp_x=x;
        }
        while ((temp_x<list.length-1)&&cache.length<3&&list[temp_x+1][y]===list[x][y]) {
            cache.push(list[temp_x+1][y]);
            temp_x++;    
        }
        if(cache.length==3){
            return true;
        }else{
            temp_x=x;
        }
        cache =[list[x][y]];

        //斜向 x,y同增同减 (\)
        while (list[temp_x-1]&&list[temp_x-1][temp_y-1]&&temp_y>0&&temp_x>0&&cache.length<3&&list[temp_x-1][temp_y-1]===list[x][y]) {
            cache.push(list[temp_x-1][temp_y-1]);
            temp_x--;
            temp_y--;    
        }
        if(cache.length==3){
            return true;
        }else{
            temp_x=x;
            temp_y=y;
        }
        while (list[temp_x+1]&&(temp_y<list[temp_x+1].length-1)&&(temp_x<list.length-1)&&cache.length<3&&list[temp_x+1][temp_y+1]===list[x][y]) {
            cache.push(list[temp_x+1][temp_y+1]);
            temp_y++;
            temp_x++;    
        }
        if(cache.length==3){
            return true;
        }else{
            temp_x=x;
            temp_y=y;
        }
        // 斜向 （/）
        while (list[temp_x+1]&&list[temp_x+1][temp_y-1]&&temp_y>0&&temp_x<list.length-1&&cache.length<3&&list[temp_x+1][temp_y-1]===list[x][y]) {
            cache.push(list[temp_x+1][temp_y-1]);
            temp_x++;
            temp_y--;    
        }
        if(cache.length==3){
            return true;
        }else{
            temp_x=x;
            temp_y=y;
        }
        while (list[temp_x-1]&&(temp_y<list[temp_x-1].length-1)&&(temp_x>0)&&cache.length<3&&list[temp_x-1][temp_y+1]===list[x][y]) {
            cache.push(list[temp_x-1][temp_y+1]);
            temp_y++;
            temp_x--;    
        }
        if(cache.length==3){
            return true;
        }else{
            return false;
        }
    }
}

console.log(Tools.chessWin(2,0,[['1','','1'],['','1',''],['1','','1']]));

```



###### 3. 关于setState的同步异步问题

```typescript
putChess(x:number,y:number) {
        //get id

    if(this.state.chess_all[x][y]!=''){
        return console.log('不能走那个位置');
    }
    this.state.chess_all[x][y]=this.state.chess_current;
    this.switchChess();
    //判断
    this.checkWin(x,y,this.state.chess_all);
    setTimeout(() => {
        this.props.getCurrent(this.state.chess_current); // 语句
    }, 0);
    //如果不把‘语句’放在setTimeout里面，就不能在switchChess更改state后，得到更改后的state
        
}
```

由此推断出，setState有异步的时候，所以将

```
 this.props.getCurrent(this.state.chess_current); // 语句
```

放在setTimeout里面，才能保证得到更改后state的值



###### 4. 开始学习node库  Koa.js

```
app.use()
```

app.use 后面接一个中间件，有且只有一个。且注册的中间件要为函数



**项目优化，自动重启服务**



项目的基本优化：1. 自动重启配置

安装nodemon工具

```
npm i nodemon
```

在package.json 中编写启动脚本

```javascript
"scripts": {
    "dev": "nodemon ./src/main.js",
    "test": "echo \"Error: no test specified\" && exit 1"
  },
```



**读取配置文件**

```
cd ../  返回上一级
```

安装 dotenv

```
npm i dotenv
```

在根目录安装dotenv

在src新建config文件夹，新建 **.env** 后缀的文件，新建config.default.js文件

.env

```
APP_PORT = 8000 
```

config.default.js

```javascript
const dotenv = require('dotenv');
const result = dotenv.config(); //这一步自动将 .env 中自定义的环境配置 与 process.env 合并

module.exports = result.parsed; //但我们只导出parsed 

```

但是还是有问题





**使用Koa-router**

1. 导入包
2. 实例化对象
3. 编写路由
4. 注册中间件



```javascript
var Koa = require('koa');
var Router = require('koa-router');

var app = new Koa();
var router = new Router();

router.get('/', (ctx, next) => {
  // ctx.router available
});

app
  .use(router.routes())
  .use(router.allowedMethods());
```



```
var router = new Router({
  prefix: '/users'
});

router.get('/', ...); // responds to "/users"
router.get('/:id', ...); // responds to "/users/:id"
```



**路由拆分**

user.route.js

```javascript
const Router = require('koa-router');

const router = new Router({
    prefix: '/users'
})

//GET /users
router.get('/',(ctx,next)=>{
    ctx.body = 'hello users';
})

module.exports = router;
```



main.js

```
const userRouter = require('./route/user.route');
...

app.use(userRouter.routes)
```





###### 5. react报错 TypeError: Cannot read property 'setState' of undefined

```javascript
class A {
  constructor() {
    this.a = this.a.bind(this)
  }
 
  a() {}
 
  // or
  @bindthis
  b() {}
}
```

