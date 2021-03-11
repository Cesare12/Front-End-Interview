#### 1. React生命周期

##### 1.1 挂载
constructor：构造函数，用于初始化。

getDerivedStateFromProps：触发：1.props传入；2.setState变化；3.forceUpdate强制更新。

render：描述渲染内容。

componentDidMount：加载完成时操作，比如发起网络请求。

##### 1.2 更新

getDerivedStateFromProps

shouldComponentUpdate：通过state 和 props 浅比较可以阻止渲染。

render：state变化 或 父组件props传入（无论有没有变化）

getSnapshotBeforeUpdate(prevProps, prevState)：DOM更新前调用，返回值作为componentDidUpdate第三个参数。

componentDidUpdate(prevProps, prevState, snapshot)：使用setState会死循环，所以要比较一下this.props和prevProps。

##### 1.3 卸载
componentWillUnmount：取消定时器

##### 1.4 函数组件
如何情况都会渲染，没有生命周期，使用React.memo缓存优化，方法是复用最近一次渲染结果。
##### 1.5错误边界
错误边界是一种 React 组件，class ErrorBoundary extends React.Component，React渲染出错时，渲染备用组件。
#### 2. setState

#### 3. virtual DOM 更新规则
#### 4. React Hook
函数式编程，生命周期概念淡出，相比类组件更轻量。
#### 5. Component 和 Element：

没有JSX时，使用React.createElement创建标签，使用JSX时可以extends React.Component，然后render返回Element
<p></p>
