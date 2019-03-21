## CRA(create-react-app)
### npm install create-react-app
```
npm i -g create-react-app
```
### npm install react-router-dom
```
npm install react-router-dom
```

### 关于自定义

1.项目 eject

2.替换 react-scripts 包

3.使用 react-app-rewired

4.scripts 包 + override 组合


自己用[react-app-rewired](https://github.com/timarney/react-app-rewired#3-flip-the-existing-calls-to-react-scripts-in-npm-scripts)这种方式

1) Install react-app-rewired
```
npm install react-app-rewired --save-dev
```
2) Create a config-overrides.js file in the root directory
/* config-overrides.js */
```
module.exports = function override(config, env) {
  //do stuff with the webpack config...
  return config;
}
```
```
+-- your-project
|   +-- config-overrides.js
|   +-- node_modules
|   +-- package.json
|   +-- public
|   +-- README.md
|   +-- src
```
3) 'Flip' the existing calls to react-scripts in npm scripts
  /* package.json */
```
  "scripts": {
-   "start": "react-scripts start",
+   "start": "react-app-rewired start",
-   "build": "react-scripts build",
+   "build": "react-app-rewired build",
-   "test": "react-scripts test --env=jsdom",
+   "test": "react-app-rewired test --env=jsdom"
}

```
4) Start the Dev Server
```
$ npm start
```
5) Build your app
```
$ npm run build

```

6) yarn错误The engine "node" is incompatible with this module
```
yarn config set ignore-engines true
```


参考：[如何扩展 Create React App 的 Webpack 配置](https://juejin.im/post/5a5d5b815188257327399962)
