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
