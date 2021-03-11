#### 1. React生命周期

##### 1.1 挂载
constructor：构造函数，用于初始化。

getDerivedStateFromProps：触发：1.props传入；2.setState变化；3.forceUpdate强制更新。

render：描述渲染内容。

componentDidMount：加载完成时操作，比如发起网络请求。

##### 1.2 更新

getDerivedStateFromProps

shouldComponentUpdate：通过state 和 props 浅比较可以阻止渲染。

render

getSnapshotBeforeUpdate(prevProps, prevState)：DOM更新前调用，返回值作为componentDidUpdate第三个参数。

componentDidUpdate(prevProps, prevState, snapshot)：使用setState会死循环，所以要比较一下this.props和prevProps。

##### 1.3 卸载
componentWillUnmount：取消定时器

#### 3. virtual DOM 更新规则
#### 4. React Hook
#### 5. Component 和 Element：

没有JSX时，使用React.createElement创建标签，使用JSX时可以extends React.Component，然后render返回Element
<p></p>
