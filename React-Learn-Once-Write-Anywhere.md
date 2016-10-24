## Notes for React: Learn Once Write Anywhere
[React: Learn Once Write Anywhere - JSConf Iceland 2016](https://www.youtube.com/watch?v=G_nh6JnE2_4&index=6&list=PL37ZVnwpeshGtbb-i7WJqtxZhoe5AGIw4)

[https://github.com/btholt](https://github.com/btholt)

Demo based on [Blessed: A high-level terminal interface library for node.js.](https://github.com/chjj/blessed)

### React

* React is a library for creating views
* Created for the DOM
* Created at Instagram and took over everything
* A pattern for writing UIs

### MVC
Got stuck with MVC as front end developers.

* MVC is super awsesome for the back end.  `Ruby on Rails`, `Django`,  `ASP.Net MVC` etc.
* Abstraction of MVC, model, view, controller.
* Separtion of concerns.
  * MVC models that talks to the database
  * MVC viewss that talk out to the clients
  * thin little controllwers that wire all the data together.  Works great for back end programming.
* People thought that this was an awesome idea to apply to the DOM.  Turned out that it's not such an awesome idea.
* Huge MVC apps can fall apart, unless you are very disciplined.  (Applies to all apps no?)

### There has to be better way.  A paradigm shift.

* For years:... request a web page, you get a web page.
* Idea:...  given a set of `state` you get an output of `DOM`
  * This ended up being really great.
  * Then they came up with a bunch of crazy ideas of how they could implement it
     * Such as the `Virtual DOM`.

#### Lets write React and have it target iOS and Android

* We are using the same paradigms, the same life cycle methods
* Same react components, remember, they are just Javascrit objects.

```
```

* Use React object metadata to render Android, iOS specific components.
* Break out `ReactDOM` form `React` and have this generalized React library taht doesn't care what it's targeting.  It just makes components.

Now we can do this like..  (a.k.a last mile libraries)
* [React Native](https://github.com/facebook/react-native)
* [React blessed](https://github.com/Yomguithereal/react-blessed)
* [React Hardware](https://github.com/iamdustan/react-hardware)

#### Why React is cool
* It's about creating components
* A pattern for user interfaces
* Declarative method of declarting components
* Components can be black boxes to each other.
  * Component props is like is API.
* One way data flow
  * `props` down, `actions` up
* Presentation components cannot mutate state, which reduces surface area for bugs.
* Pass down props to the child component.
* Child component communicates changes via an `up callback`
  * `Hey! Here's the data I got, you deal with it`
  * If there is a problem with the modified data, the parent did it.
* React is not too big.   You can know the entire API.
  * Has anyone ever used the entire JQuery API?
* React is more declarative

> The theme here is that React is very maintainable, very easy to track down bugs.

* For UI: Instead of arbitrary sepration of concerns, we take all the conerns and mush them all together.

Example: if your button is not working, where is the bug?
* Angular:
  * Is it the `directive`, `controller`, `template`, one of the many services
* React
  * It's in the component, because all the conerns live there.

#### Netflix
* React used for TV's, PS4, XBox
* Able target platforms that he didn't know too much about.
* Learn the paradigm once and apply it in many places.
* React's ecosystem today is about embracing the differences in all the different platforms.

#### JSX
* Lets you write like you write HTML like syntax
* Syntax sugar that transpiles to fuction calls.
* I'm writing code to mimic markup... So wouldn't it be great if I could just write the markup.
* Declarative code is easier to read, reason about, maintain.

