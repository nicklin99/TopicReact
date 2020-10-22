Layout页面布局组件

公用Header、Footer组件

```js
const Header = () => <header><h1>Header</h1></header>
const Footer = () => <footer><h1>Footer</h1></footer>

function Layout({children}){
  return (
    <div>
      <Header />
        {children}
      <Footer />
    </div>
  )
}
```

应用

```js
<Layout>
  <div>page content</div>
</Layout>
```

### 动态layout

使用高阶组件嵌套

```jsx
function withLayout(Component){
  return function(props){
    const {layout} = props
    if(layout  === 'SplitPane'){
      return (
        <div className="SplitPane">
          <div className="SplitPane-left">
            {props.left}
          </div>
          <div className="SplitPane-right">
            {props.right}
          </div>
        </div>
      )
    }
    return <Component {...props} />
  }
}
```

应用

```js
const LayoutSplitPanel = withLayout(Layout)

function App(){
  return (
    <LayoutSplitPanel layout={'SplitPane'} left={<div>left</div>} right={<div>right</div>} />
  )
}
```