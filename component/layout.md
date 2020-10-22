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