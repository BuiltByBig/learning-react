# MOVED!

**For the latest examples of using react, please see my other repo [react-examples](https://github.com/danawoodman/react-examples)!**

# Learning React

This repository contains many examples of using React and the various tools in the React family.

These guides are meant to illustrate various features of React as well as some tips and best practices for writing React apps.


## Guides

- [Hello World](hello-world) - This is where you should start if you're new to React!
- [Your First Component](first-component) - Now that you've seen React, let's write your first component!
- [Stateless Functions](stateless-functions) - For simple components, use stateless functions to create React components.

**Note** In many of the examples, I write ES6/7-style JavaScript. If you're new to ES6/7, don't worry, the examples can all be written without it. The ES6/7 code is included because, in my opinion, it makes writing JavaScript more enjoyable. Try it out and see if you like it!


## What is React?

React is a frontend UI library written by Facebook. It makes creating UIs in JavaScript simple to reason about, fast to render and predictable.


## What does React look like?

Here is a simple example of React that just renders a list of items:

```js
var ProductItem = React.createClass({
  render: function () {
    return (
      <tr>
        <td>{this.props.name}</td>
        <td>{this.props.price}</td>
      </tr>
    )
  }
})

var ProductList = React.createClass({
  render: function () {
    var products = this.props.products.map(function (product, index) {
      return (
        <ProductItem
          key={index}
          name={product.name}
          price={product.price}
        />
      )
    })

    return (
      <table>
        {products}
      </table>
    )
  }
})

// Could come from an API, LocalStorage, another component, etc...
var products = [
  { name: 'Toast', price: 1499 },
  { name: 'Bacon', price: 3245 },
  { name: 'Coffee', price: 300 },
]

ReactDOM.render(<ProductList products={products} />, document.getElementById('root'))
```

You'll notice the HTML-like tags in the JavaScript. Don't freak out! It is syntactic sugar called [JSX](https://facebook.github.io/react/docs/jsx-in-depth.html) that makes it very easy to reason about the HTML your React application is generating. It compiles down to JavaScript:

```js
<div>Foo</div> //=> React.createElement('div', null, 'Foo')
```

JSX is perhaps the hardest thing for people to get used to when learning React but I've found that after a short time of actually using it you quickly come to love it. I can't even think about *not* using JSX in my JavaScript apps now :)


## Usage

You should be able to download this repository (or clone it) and follow the readme in each folder for usage information.

Each folder is self-contained and should be usable directly. There are some that will require you to have `npm` installed, but that is also documented.


## Helpful links and resources

- [React documentation](http://facebook.github.io/react/docs/getting-started.html)
- Flux architecture using [Reflux](https://github.com/spoike/refluxjs) (see [this blog post for more](http://spoike.ghost.io/deconstructing-reactjss-flux/))
- React routing with [react-router](https://github.com/rackt/react-router)
- I'd recommend checking out [Babel](https://babeljs.io/) and [WebPack](https://webpack.github.io/) for your build tooling setup.
- My other Gist on using [React + Reflux + WebSockets](https://gist.github.com/danawoodman/fa6145ee35caae3cd0a2)
- [Redux](https://github.com/reactjs/redux) is a great library for FLUX as well and seems to becoming the defacto standard in React-land.


## Contribute

See things that should be added, improved or clarified? Please create a Pull Request or Issue!


## License

MIT by [Dana Woodman](http://danawoodman.com) & [BIG](http://builtbybig.com)
