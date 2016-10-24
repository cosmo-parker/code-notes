
### Notes For:  A cartoon guide to performance in React
[Lin Clark: A cartoon guide to performance in React - JSConf Iceland 2016](https://www.youtube.com/watch?v=NGxVLnJKhP8&index=2&list=PL37ZVnwpeshGtbb-i7WJqtxZhoe5AGIw4)

#### Summary
To improve performance
* Always set `key` for array of components
* Use `shouldComponentUpdate` to short circuit rendering
  * requires immutbility of state
  * [react-redux.connect()](https://github.com/reactjs/react-redux) does this for your // my comment
* using `setState()` or `react-redux connect()` at lower levels

### How the browser renders

* The **main thread** covers Javascript, DOM, Layout (HTML, CSS)
* DOM is the way to tell the page what to do
  * Behind the scenes there is the `Render Tree`
  * **main thread** tries to batch those changes
  * Reduce number of DOM changes + batch the changes (React helps with this)

### What React does to minimize DOM changes

A user has downloaded and it has been parsed, and their as an HTML element that will serve as the container for your app.

```
ReactDOM.render(<App />, document.querySelector('#app'))
```

* A `React element` is a way for your code to hand off requirements to React.
  * A note card that has notes about what React needs to build `type`, `props` and `children`
  * React keeps the note card until its ready to build
* Your code tells React to start rendering.
  * React starts rendering work flow
     * Creates a top level wrapper object
     * Then populates the object keys with the sub objects.
     * Only when the object is complete is the actual rendering triggered

* User clicks button which triggers an event which updates state

```
// use shouldComponentUpdate() to check if state changed

let nextItems = this.state.items

nextItems.push(newItem)

this.setState({
    items: [...nextItems]
})
```

* When state changes it adds to list of pending state changes.
* Waits to see if click handler made any ohter updates.
* Then flushes the queue.
* Calculates the next state
* Components creates new element based on the state
* Calculaes what DOM changes are needed.

### What you can do to make it even faster

* When ever your creating an array of children set the keys.
  * React can use these keys to determine which nodes should be compared.

If there are no changes after a click

```
shouldComponentUpdate(nextProps, nextState) {
    if (this.state.items === nextState.items) {
        return false
    }
    return true
}
```

Using `redux` using `connect` at the top level of your tree means that it will always render.
For performance consider using `connect` at the sibling levels of the tree.

Note: [this code in connect.js](https://github.com/reactjs/react-redux/blob/master/src/components/connect.js) only renders if state / props changed.

```
const haveStatePropsChanged = tryCatch(this.updateStatePropsIfNeeded, this)
if (!haveStatePropsChanged) {
    return
}
```







