## React 框架

### React.js 的引用

- **react.min.js** **核心库**
- **react-dom.min.js** **DOM**相关的功能
- **babel.min.js** 将 **ES6** 代码转为 **ES5** 代码

> **开发环境**

```javascript
<script src="https://cdn.staticfile.org/react/16.9.0/umd/react.development.js"></script>
<script src="https://cdn.staticfile.org/react-dom/16.9.0/umd/react-dom.development.js"></script>
<script src="https://cdn.staticfile.org/babel-standalone/6.7.7/babel.min.js"></script>
<script type="text/babel"></script>
```

> **生产环境**

```javascript
<script src="https://cdn.staticfile.org/react/16.9.0/umd/react.production.min.js"></script>
<script src="https://cdn.staticfile.org/react-dom/16.9.0/umd/react-dom.production.min.js"></script>
<script src="https://cdn.staticfile.org/babel-standalone/6.7.7/babel.min.js"></script>
<script type="text/babel"></script>
```

### JSX

> **注释**

- 需要加**大括号**

```javascript
let name = <div>Text{/*注释*/}</div>;
```

> **多个标签**

- 需要有一个**父元素**

```javascript{.line-numbers}
let num = (
  <div>
    <div>Text1</div>
    <div>Text2</div>
  </div>
);
ReactDOM.render(num, document.getElementById("myReact"));
```

> **插入变量**

```javascript
let text = "你好";
let num = 10;
let txt = (
  <div>
    <div>{text}</div>
    <div>{num}</div>
  </div>
);
ReactDOM.render(num, document.getElementById("myReact"));
```

[返回顶部](#目录)

### React 组件

> **组件名称必须以大写字母开头**

#### 组件常用方法

> **ReactDOM.render()**

```javascript
ReactDOM.render(模板, 位置);
```

**ReactDOM.hydrate()**
**ReactDOM.unmountComponentAtNode()**
**ReactDOM.findDOMNode()**
**ReactDOM.createPortal()**

#### 组件的生命周期方法

> **render()**

- **是 class 组件中唯一必须实现的方法**

> **constructor()**

- **不要在方法里调用 `setState()`方法**
- **在其他语句之前前调用 `super(props)`**
- **通过给 `this.state` 赋值对象来初始化内部 state**

```javascript
constructor(props) {
    super(props);
    this.state = { counter: 0 };
}
```

> **componentDidMount()**

- **可以在方法里直接调用`setState()`**

> **componentDidUpdate()**

- 会在**更新后**会被立即调用,**首次渲染**不会执行此方法

> **componentWillUnmount()**

- 会在**组件卸载及销毁之前**直接调用,在此方法中执行必要的清理操作

> **shouldComponentUpdate()**

[返回顶部](#目录)