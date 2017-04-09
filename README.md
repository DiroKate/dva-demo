# dva-demo
- install `node`

guide from : https://github.com/sorrycc/blog/issues/18

## Step 1: install `dva-cli`
```
npm i dva-cli -g
dva -v
```

## Step 2: install `antd` and `babel-plugin-import`
```
npm i antd --save
npm i babel-plugin-import --save-dev
```

change `.roadhogrc` file and add the following in the field `extraBabelPlugins`:
```
"import",
{
  "libraryName": "antd",
  "style": "css"
}
```

## Step 3: get user data

change `.roadhogrc`, add `"proxy"` settings：
```
"proxy": {
  "/api": {
    "target": "http://jsonplaceholder.typicode.com/",
    "changeOrigin": true,
    "pathRewrite": { "^/api" : "" }
  }
},
```
and run
```
$ npm start
```

## Step 4: generate Route:users
run
```
dva g route users
```

## Step 5: generate users model and services
run
```
dva g model users
```

## Step 6: generate UsersComponent
run
```
dva g component Users/Users
```

1. implete the components by using `antd`
1. update models for component `pagination`
1. update routes for component
1. add constants for `PAGE_SIZE`

## Step 7: add MainLayout
```
-import { MainLayout } from '../components/MainLayout/MainLayout';
+import MainLayout from '../components/MainLayout/MainLayout';
```

## Step 8: add loading
- using dva-loading plugin for data loading.
- run `npm install dva-loading -S` to install.
- update the `index` file and the `users` component.

## Step 9: update pagination
- update pagination, listen the changes of router change.

## Step 10: delete a user
- add ACTION remove
- add remove Service
- add remove EFFECT
