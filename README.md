# dva-demo
- install `node`

##Step 1: install `dva-cli`
```
npm i dva-cli -g
dva -v
```

##Step 2: install `antd` and `babel-plugin-import`
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
