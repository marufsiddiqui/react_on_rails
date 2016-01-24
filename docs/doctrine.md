# The React on Rails Doctrine

By Justin Gordon with community participation, January 20, 2016

This document is an extension and complement to [The Rails Doctrine](http://rubyonrails.org/doctrine/). If you haven't read that document, I suggest you do so first.

As stated in the [React on Rails README](../README.md), the project objective is to provide an opinionated and optimal framework for integrating **Ruby on Rails** with modern JavaScript tooling and libraries. When considering what goes into **react_on_rails**, we ask ourselves, is the functionality related to the intersection of using Rails and with modern JavaScript? A good example is view helper integration of React components on a Rails view. If the answer is yes, then the functionality belongs right here. In other cases, we're releasing separate npm packages or Ruby gems. For example, we needed an easy way to integrate [Twitter Bootstrap](http://getbootstrap.com/) with Webpack, and we released the [npm bootstrap-loader](https://github.com/shakacode/bootstrap-loader/). 

Besides the project objective, let's stick with the "Rails Doctrine" and keep the following in mind.

## Optimize for Programmer Happiness
The React on Rails setup provides several key components related to front-end developer happiness:

1. [Hot reloading of both JavaScript and CSS](https://gaearon.github.io/react-hot-loader/), via the [webpack dev server](https://webpack.github.io/docs/webpack-dev-server.html). This works for both using an [express server](http://expressjs.com/) to load stubs for the ajax requests, as well as using a live Rails server. **Oh yes**, your Rails server can do hot reloading!
2. [CSS modules](https://github.com/css-modules/webpack-demo) which remove the madness of a global namespace for CSS. We organize our CSS (Sass actually) right next to our JavaScript React component files. This means no more creating arbitrarily long class names to just position your HTML elements.
3. [ES6 JavaScript](http://es6-features.org/#Constants), using [Babel](https://babeljs.io/) and [Webpack](http://webpack.github.io/), is a great language for client side coding, much more so than Ruby due to the asynchronous nature of UI programming. 
4. We want to use JavaScript libraries and tooling in the native node way, rather than via some aspect of Sprockets and the Rails Asset Pipeline. We find way less frustration this way, especially from being able to get the latest advances with the rest of the JavaScript community. Why complicated beautiful JavaScript tooling Rails asset pipeline complexity?
5. We want our JavaScript from npm. Getting JavaScript from rubygems.org is comparatively frustrating.
6. Happiness for us is actively participating in open source, so we want to be where the action is, which is with the npm libraries on github.com.
7. You can get setup on React on Rails **FAST** using our application generator.
8. By placing the entire client side of development inside of the `/client` directory, we're allowing the *comfortable* and *productive* inclusion of pure JavaScript developers onto projects using Ruby on Rails. These developers can create they own stub APIs on an express server and edit React components that are also include the Rails application. Another benefit of this structure is the ability to create UI prototypes quickly.
9. Just because we're not relying on the Rails asset pipeline for ES6 conversion does not mean that we're deploying Rails apps in any different way. We still use the asset pipeline to include our Webpack compiled JavaScript. This only requires a few small modifications, as explained in our doc [Heroku Deployment](additional_reading/heroku_deployment.md).

## Convention over Configuration
* We take the hard work out of figuring out the JavaScript tooling that works best with Rails. Not only could you spend lots of time researching different tooling, but then you'd have to figure out how to splice it all together. This is where a lot of "JavaScript" fatigue comes from.
* We follow a [Style Guide](coding-style/style.md) and rigorously use [linters](coding-style/linters.md).
* Our [Recommended Project Structure](recommended-project-structure.md) provides a clear and consistent client application organization.

We're big believers in this quote from the Rails Doctrine: 

> The same goes even when you understand how all the pieces go together. When there’s an obvious next step for every change, we can scoot through the many parts of an application that is the same or very similar to all the other applications that went before it. A place for everything and everything in its place. Constraints liberate even the most able minds.


## The Menu Is Omakase

Here's the chef's selection from the React on Rails community:

### Libraries
* [Bootstrap](http://getbootstrap.com/), loaded from [bootstrap-loader](https://github.com/shakacode/bootstrap-loader/).
* [Lodash](https://lodash.com/): your Swiss army knife of utilities.
* [React](https://github.com/rackt/react-router): does this need explanation? 
* [React-Router](https://github.com/rackt/react-router): sync up your URL with your client side application.
* [Redux](https://github.com/rackt/redux): our preferred Flux implementation.

### JavaScript Tooling
* [Babel](https://babeljs.io/): Transpiler for ES6 into ES5 and much more.
* [EsLint](http://eslint.org/) and [Jsrc](http://jscs.info/): We use both of these linters.
* [Webpack](http://webpack.github.io/): Create the deployment assets, and provide hot module reloading.

By having a common set of tools, we can discuss what we should or shouldn't be using. Thus, this takes out the "JavaScript Fatigue" from having too many unclear choices in the JavaScript world.

By the way, we're *not* omakase for standard Rails. That would be CoffeeScript. However, the Rails Doctrine makes it clear that non-standard menu choices are certainly welcome!

## No One Paradigm
React on Rails fits into the "No One Paradigm" into the Rails ecosystem from the perspective that it rocks for client side development with Rails, even though it's a totally different language than the server code written in Ruby.

## Exalt Beautiful Code
ES5 was ugly. ES6 is beautiful. React is beautiful. Client side code written with React plus Redux, fully linted with the ShakaCode linters and organized per our recommended project structure is beautiful. Don't take our word for it. Take a look at the component sample code in the [react-webpack-rails-tutorial sample code](https://github.com/shakacode/react-webpack-rails-tutorial/tree/master/client/app/bundles/comments).

## Value Integrated Systems
Assuming that you're building the type of app that's a good fit for Rails (document/database based with lots of business rules), we suggest that tight integration of modern JavaScript with React on top of Ruby on Rails is better than building a pure client side app and separate microservices. Why:

* Via React on Rails, we can seamlessly integrate React UI components with Rails.
* Tight integration allows trivial setup of server rendering of React on top of Rails, even with fragment caching of the server rendered HTML, and integration with [Turbolinks](https://github.com/rails/turbolinks).
* Let's be honest. It take **MUCH** more time to build a UI for basic forms and pages using React than plain Rails. So why not mix and match Rails pages with React pages based on the task? Not every part of a UI requires the high fidelity achievable using React. This is the best of both worlds. 

## Progress over Stability
We intend to maintain an active pace of development of React on Rails, keeping up with:

* Community suggestions.
* New client side tooling, libraries, and techniques.
* Updates to Rails.

## Push up a big tent
We're definitely a part of the big tent of Rails, just like RSpec is! And we intend to provide a big tent for integration of various JavaScript tooling and techniques with Rails. In fact, a huge benefit of the React on Rails system is simple integration with Webpack and NPM. Thus, you could probably use this system with other clients side frameworks, and really any library available on [npm](https://www.npmjs.org/)!

## Thanks!
Thanks for reading and being a part of the React on Rails community. Feedback on this document and *anything* in React on Rails is welcome. Please [open an issue](https://github.com/shakacode/react_on_rails/issues/new) or a pull request. If you'd like to join our private Slack channel, please [email](mailto:contact@shakacode.com) us a request.
