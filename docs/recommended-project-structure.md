# Project structure

While React On Rails does not enforce an specific project structure, we do want to recommend a standard organization. The more we follow standards as a community, the easier it will be for all of us to move between various Rails projects that include React On Rails.

1. `/client`: All client side JavaScript goes under the `/client` directory. 
We organize the major domains of the client side app 
1. `/client/app`: All application JavaScript. Note, we're following the [Airbnb JavaScript Style Guide](https://github.com/airbnb/javascript#naming-conventions) where we name the files to correspond to exported Objects (PascalCase) or exported functions (camelCase). We don't use dashes or snake_case for JavaScript files, except for possibly some config files.
1. `/client/app/bundles`: Top level of different app domains
1. `/client/app/lib`: Common code for bundles
1. Within each bundle directory (or the lib directory), such as `/client/app/lib/HelloWorld`, we have the following directory structure:

  * `/actions`: Redux actions.
  * `/components`: "dumb" components (no connections to Redux or Ajax). These get props and can render themselves and children.
  * `/constants`: Constants used by Redux actions and reducers.
  * `/containers`: "smart" components. These components are bound to Redux.
  * `/reducers`: Reducers for redux. 
  * `/routes`: Routes for React Router.
  * `/startup`: Container components and bundle's Redux **store** exposed to React On Rails and 
  * `/schemas`: Schemas for JSON files
1. `/client/app/assets`: Assets for CSS for client app.
1. `/client/app/assets/fonts` and `/client/app/assets/styles`: Globally shared assets for styling. Note, most Sass and image assets will be stored next to the JavaScript files.
