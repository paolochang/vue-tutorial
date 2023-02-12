# Tutorial for Vue.js 3.x

### Check installation

```sh
$ vue --version
```

### Installation

```sh
# make sure remove all vue cli
$ sudo npm uninstall --global vue-cli
$ sudo npm uninstall --global @vue/cli
# install the latest version of vue cli
$ sudo npm install --global vue
$ sudo npm install --global @vue/cli@latest
```

### Update Vue version

```sh
$ npm update -g @vue/cli
```

### VSCode Extension

- `Vue Language Features (Volar)`
- `Vetur`

### Create Vue Project

- Default Setup with Vue.js 3.x

  ```sh
  $ vue create <project_name>
  Vue CLI v5.0.8
  ? Please pick a preset: (Use arrow keys)
  ❯ Default ([Vue 3] babel, eslint)
    Default ([Vue 2] babel, eslint)
    Manually select features
  ```

- Manual Setup

  ```sh
  $ vue create <project_name>
  Vue CLI v5.0.8
  ? Please pick a preset: Manually select features
  ? Check the features needed for your project: Babel, Router, Vuex, Linter
  ? Choose a version of Vue.js that you want to start the project with 3.x
  ? Use history mode for router? (Requires proper server setup for index fallback in production) Yes
  ? Pick a linter / formatter config: Standard
  ? Pick additional lint features: Lint on save
  ? Where do you prefer placing config for Babel, ESLint, etc.? In dedicated config files
  ? Save this as a preset for future projects? Yes
  ? Save preset as: Basic
  ```

### ESLint and Code Formatting with Prettier

- Create `.prettierrc` file and add all properties

  ```json
  {
    "semi": false,
    "bracketSpacing": true,
    "singleQuote": true,
    "useTabs": false,
    "trailingComma": "none",
    "printWidth": 80
  }
  ```

- In `.eslintrc.js`

  ```js
  module.exports = {
    root: true,
    env: {
      node: true,
    },
    extends: ["plugin:vue/vue3-essential", "@vue/standard"],
    parserOptions: {
      parser: "@babel/eslint-parser",
    },
    rules: {
      "no-console": process.env.NODE_ENV === "production" ? "warn" : "off",
      "no-debugger": process.env.NODE_ENV === "production" ? "warn" : "off",
      "space-before-function-paren": off, // <- add this line
    },
  };
  ```

### Routes in Vue.js

There are three different ways of importing components

```js
import HomeView from "../views/HomeView.vue";

const routes = [
  {
    path: "/",
    name: "home",
    /* option 1 */
    component: HomeView,
  },
  {
    path: "/about",
    name: "about",
    // route level code-splitting
    // this generates a separate chunk (about.[hash].js) for this route
    // which is lazy-loaded when the route is visited.
    /* option 2 */
    component: () =>
      import(/* webpackChunkName: "about" */ "../views/AboutView.vue"),
  },
  {
    path: "/contact",
    name: "contact",
    /* option 3 */
    component: () =>
      import(
        /* webpackChunkName: "about", webpackPrefetch: true */ "../views/ContactView.vue"
      ),
  },
];
```

- option 1: import component at the top and add imported component. This option will import and load the view as the app starts

- option 2: add inline import component. This option will import and load the view as user click the link to show the view. This is good for light-weight views with less chance of opening.

- option 3: add inline import component with `webpackPrefetch: true` option. This option prefetch the view as the app starts and store in the cache. This is good for any view with large amount of data to load.
