# 前端工程化学习

# *NODE/NPM/WEBPACK/BABEL/ES6/VUE*

## 解决ES6语法兼容性问题--babel

1. 创建工程 npm 

2. npm install --save-dev babel-cli 

3. .babelrc 创建该文件在项目底下,写入以下文件 

```js
 {

 "presets":["es2015", "stage-2"],

 "plugins":["transform-runtime"]

}
```



4. 需要转换成ES2015 安装需要的库

npm install babel-core babel-preset-es2015 babel-transform-runtime babel-preset-stage-2 --save-dev

5. 修改脚本 package.json 中

```js
 "scripts": {

  "test": "echo \"Error: no test specified\" && exit 1",

  "test2": "dir",

  "build": "babel src -d lib" // 添加编译路径

 }
```

6. npm run build 测试 ， lib 下面有转换后的结果



## yarn 的安装使用

```js
npm install -g yarn

yarn config set registry https://registry.npm.taobao.org -g

yarn config set sass_binary_site http://cdn.npm.taobao.org/dist/node-sass -g
```

## webpack 的使用及几个重要概念

### 首先安装webpack webpack-cli

### 在项目根目录创建 webpack.config.js   
约定的文件名，也可修改为其他 ，文件内容如下，注意注释内容

```
const {resolve} = require('path');

module.exports = {

    // entry 默认index.js 不用写 ，
    // Array数组形式， 输出也是一个文件
    // entry:['./src/index.js','./src/main.js'],
    // Object 对象形式，有几个入口文件 就有几个输出
    // entry:{
    //     one:'./src/index.js',
    //     two:'./src/main.js'
    // },
    // special style
    entry:{
        onea:['./src/index.js','./src/main.js'],
        twob:'./src/index.js'
    },

    // 输出值webpack 打包后的资源budles输出到哪
    output:{
        // filename:"build.js",
        filename:"[name].js",
        path:resolve(__dirname, 'build')
    },

    // loader 翻译 处理哪些文件
    module: {
        rules:[

        ]
    },

    // plugins 插件 , 其他功能强大的插件
    plugins:[],

    mode:'development'
}
```