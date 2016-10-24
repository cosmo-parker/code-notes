
## Notes For:  Web Development in Year 2020

* [Web Development in Year 2020](https://www.youtube.com/watch?v=0tj6VLuSowQ)
* [blog](http://blog.stevensanderson.com/)

### Topics

* ES2015 (ES6) Language featues
* Web components and custom rendering
* Simplified asynchrony
* WebAssembly and Cross compoiliation
* Shared memory parallelism
* CSS-free layouts

### Web components
* Allows packaging of scripts, html, css into a reusable encapsulated form.
* Can be consumed via custom elements in markup
* Safe isolation
* Interop with 3rd-party libraries

```
class salesChart extends HTMLElement {
    let shadow = this.createShadowRoot()
    createCallback() {
        shadow.innerHTML = 'Hello There!'
    }
}

document.registerElement('sales-chart', salesChart)
```

### Simplified asynchrony

Promises

```
getTodos() {
    let url = `/backend/todos.json`

    fetch(url)
        .then(response => response.json())
        .then(json => this.todos = json.todos)
        .catch(err => console.error(error))
}
```
Synchronous

```
// wont work because it's asynchronous code
getTodos() {
    let url = `/backend/todos.json`

    let response = fetch(url)
    let json = response.json()
    this.todos = json.todos
}
```

async await

```
// wont work because it's asynchronous code
async getTodos() {
    let url = `/backend/todos.json`

    let response =  awiat fetch(url)
    let json = await response.json()
    this.todos = json.todos
}
```

Also you can use `try.. catch`

```
async getTodos() {
    let url = `/backent/todos.json`

    try {
        let response = await fetch(url)
        let json = await response.json()
        this.todos = json.todos
    } catch(err) {
        // handel err
    }
}
```

### Native code on the Web

`WebAssembly`: the neew bytecode format for the web

* Include C libraries
* Write code in Swift/Go/Grog ect.
* WebAssembly is fast to transmit parse and execute

### `SharedArrayBuffer`

### CSS-free layouts

Some of the things that are really hard to do in css, are still hard to do.

* Vertical centering
* Making one thing the right size to fit something else
* `Flexbox` is great, but there are alot of things that can't be expressed with it.

Could there be an alternate way that doesn't require padding, etc.

* Constrains engine to define layout

#### Auto layout
[Autho layout css](https://youtu.be/0tj6VLuSowQ?t=2743)

* A way of defining layout of components in your app according to constraints, and the OS places the according to display size.

```
// left hand edge of `B1..B3` equal right hand edge of `A` + 20 pixels
B1[left] == B2[left] == B3[left] == A[right] + 20

B2[center - y] == A[center - y]
B1[top] == A[top]
B3[bottom] == A[bottom]
```

Can be done today using [GSS](https://github.com/gss/engine)

### Wrap up

<table>
    <thead>
        <th></th>
        <th>2015</th>
        <th>2020</th>
        <th>Alternative<th>
    </thead>
    <tbody>
        <tr>
            <td>ES 2016/16 Syntx</td>
            <td>Transpile bable / typescript</td>
            <td>Native</td>
            <td></td>
        </tr>
        <tr>
            <td>Webcomponents</td>
            <td>polyfill</td>
            <td>Native</td>
            <td></td>
        </tr>
        <tr>
            <td>Async/await/yield</td>
            <td>Near native / transpile</td>
            <td>Native</td>
            <td>Bable / Typescript, or use `yield`</td>
        </tr>
        <tr>
            <td>Web assembly / asm.js</td>
            <td>Not yet native bytecode</td>
            <td>Native</td>
            <td><a href="https://github.com/kripken/emscripten">emscripten</a></td>
        </tr>
        <tr>
            <td>Shared array buffer</td>
            <td>None</td>
            <td>Native</td>
            <td></td>
        </tr>
        <tr>
            <td>Constraint-based layout</td>
            <td>Only if brave</td>
            <td>?</td>
            <td></td>
        </tr>
    </tbody>
</table>







