## Notes: The First Engineer's Dilema
[Alex Kaminsky: The First Engineer's Dilemma - JSConf Iceland 2016](https://www.youtube.com/watch?v=w-CSrRquNGI&list=PL37ZVnwpeshGtbb-i7WJqtxZhoe5AGIw4&index=7)

### Workflow, Technology

* Workflow
  * Design, Product
* Tehcnology
  * Stack
  * Standards

 > Insane number of options to build web apps in the mondern age.
 > How do you begin to pick a full tech stack top to bottom, thats not going to feel completely outdated in just a few months?

### Design

* Desing and technology usually completely siloed.
* Interpreting `psd` files without any context can lead to frustration
* Designers don't always think of edge cases
* Without technology involved in th design, designers don't know how far they can push it.

### Don't

* Don't be that *NO* developer
  * Sick of everything, thinks that everything is stupid.

### Prototyping

* First few weeks should be about prototyping.
* Show progress
* Reduce frustration, feeling that nothing is getting done.

### Technology Issues

One of the biggest decision your going to make.

1. Friendlyness to new developers
2. Sexiness
  * New technologies make us happy
3.  Ability to lead on it.
  * You are expected to know the ins and outs of the tech stack
  * You are expected to make decisions on how to style build and execute on features.
4. Production readiness
  * Technology that isn't just sexy, but also has a good community
5. context
  * Heavy weight enterprise UI, or lighter view based UI

### CSS

Less and Sass came out dead even.

### JS technologies

* Anagular, Ember, React
  * React good for UI view heavy, minimal update apps.
  * Angular, Ember full stack data driven UI

### Why is React intimidating

* React itself is easy to understand, has an approachable API
* Flow, [Redux](https://github.com/reactjs/redux), [Relay](https://github.com/facebook/relay) etc that intimidate.
* Not all apps require Flow, Redux.

### Build System

* Grunt, Gulp, Webpack.

Chose Webpack

### Standards

Set good standards for your team

* Questions?
  * How to standardize CSS?
  * How to style and document our Javascript?
  * What does the project structure look like?
  * How to enfore it all?

### CSS Standards

```
.dashes-not-underscores {
    .tabs-not-spaces {
        .no-nesting {
            // more than three deep!
        }
    }
}
```

Just one file per component

### Javascript

* [JSDoc](http://usejsdoc.org/) style comments
* [Google Javascript style guide](https://google.github.io/styleguide/javascriptguide.xml)

### Directory structure

* Putting this off will result in a gnarly directories with tons of files to sort through.
* Dependent on your framework, build system....

> Webpack takes alot of the stress of complitcated dependencies out of your app.

* Webpack
  * Import images, stylesheets and other dependencies directly into your javascript files.
     * Neat little bundles for your components

```
+-- assets
    +-- lib
+-- components
    +-- nav
    +-- sidebar
        +-- Sidebar.jsx
        +-- Sidebar.less
    +-- video
```

As project grew

```
+-- assets
    +-- lib
+-- components
    +-- shared
        +-- nav
        +-- sidebar
            +-- Sidebar.jsx
            +-- Sidebar.less
    +-- views
    +-- video
```

### Linting

* [ESLint](https://github.com/eslint/eslint)
* [TSLint](https://github.com/palantir/tslint) // mine

### Scafolding

* Boilerplate template for new components






















