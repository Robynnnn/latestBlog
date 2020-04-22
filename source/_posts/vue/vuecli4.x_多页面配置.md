---
title: vuecli4.x多页面配置
tags: vue
categories: vue
date: 2020-04-22
---

此篇文章教你手把手撸一个多页面的vue脚手架

### 1. 安装脚手架以及创建相应的项目
来自官网的引用：
```javascript
npm install -g @vue/cli
# OR
yarn global add @vue/cli
```
你可以用以下命令查看自己的脚手架版本：
```javascript
 vue --version
```
此篇文章写的时候用的是 @vue/cli 4.3.1

运行以下命令来创建一个新项目：
```javascript
vue create vuecli4.x_MPA
```

具体看官网的相关文章，这里不过多描述，你可以选默认的包含了基本的 Babel + ESLint 设置的 preset，也可以选“手动选择特性”来选取需要的特性。

### 2. 目录结构
当你安装完之后，如果你的脚手架版本也是 @vue/cli 4.3.1，那么应该跟我以下的目录结构基本一致：

    |-- .browserslistrc
    |-- .editorconfig
    |-- .eslintrc.js
    |-- .gitignore
    |-- babel.config.js
    |-- package-lock.json
    |-- package.json
    |-- README.md
    |-- public
    |   |-- favicon.ico
    |   |-- index.html
    |-- src
        |-- App.vue
        |-- main.js
        |-- assets
        |   |-- logo.png
        |-- components
        |   |-- HelloWorld.vue
        |-- router
        |   |-- index.js
        |-- store
        |   |-- index.js
        |-- views
            |-- About.vue
            |-- Home.vue


现在开始调整目录结构，移除掉 src/views, src/router, src/App.vue, src/main.js, src/store,

新增 src/pages, src/js, src/css, src/api, vue.config.js

最终生成的demo目录结构如下：

    |-- .browserslistrc
    |-- .editorconfig
    |-- .eslintrc.js
    |-- .gitignore
    |-- babel.config.js
    |-- package-lock.json
    |-- package.json
    |-- README.md
    |-- vue.config.js
    |-- public
    |   |-- favicon.ico
    |   |-- index.html
    |-- src
        |-- api
        |-- assets
        |   |-- logo.png
        |-- components
        |   |-- HelloWorld.vue
        |-- css
        |-- js
        |-- pages
            |-- index
                |-- App.vue
                |-- index.html
                |-- main.js

### 3. vue.config.js 配置

```javascript

const path = require('path')
const glob = require('glob')

// 配置pages多页面获取当前文件夹下的html和js
function getEntry (globPath) {
  const entries = {}
  let basename; let tmp; let pathname

  glob.sync(globPath).forEach(function (entry) {
    basename = path.basename(entry, path.extname(entry))
    // console.log(entry)
    tmp = entry.split('/').splice(-3)
    pathname = basename // 正确输出js和html的路径

    // console.log(pathname)
    entries[pathname] = {
      entry: 'src/' + tmp[0] + '/' + tmp[1] + '/main.js',
      template: 'src/' + tmp[0] + '/' + tmp[1] + '/' + tmp[2],
      title: tmp[2],
      filename: tmp[2],
      chunks: ['chunk-vendors', 'chunk-common', pathname]
    }
  })
  return entries
}

const pages = getEntry('./src/pages/**?/*.html')
// 配置end
module.exports = {
  publicPath: process.env.NODE_ENV && process.env.NODE_ENV.includes('production') ? './' : '/',
  lintOnSave: true,
  productionSourceMap: false,
  pages,
  devServer: {
    index: 'index.html', // 默认启动serve 打开index页面
    open: process.platform === 'darwin',
    host: '',
    port: 8081,
    https: false,
    hotOnly: false
    // proxy: {
    //   '/': {
    //     ws: false,
    //     target: '', // dev环境 测试
    //     changeOrigin: true,
    //     pathRewrite: {
    //       '^/': '/' // 这里理解成用‘/api’代替target里面的地址，后面组件中我们掉接口时直接用api代替 比如我要调用'http://40.00.100.100:3002/user/add'，直接写‘/api/user/add’即可
    //     }
    //   }
    // } // 设置代理
  },
  // css相关配置
  css: {
    extract: true, // 是否使用css分离插件 ExtractTextPlugin
    sourceMap: false, // 开启 CSS source maps?
    loaderOptions: {
      less: {
        javascriptEnabled: true
      }
    }, // css预设器配置项
    modules: false // 启用 CSS modules for all css / pre-processor files.
  },
  chainWebpack: config => {
    config.module
      .rule('images')
      .use('url-loader')
      .loader('url-loader')
      .tap(options => {
        options.limit = 100
        return options
      })
    Object.keys(pages).forEach(entryName => {
      // console.log(entryName, 'entryName')
      config.plugins.delete(`prefetch-${entryName}`)
    })
    if (process.env.NODE_ENV && process.env.NODE_ENV.includes('production')) {
      config.plugin('extract-css').tap(() => [{
        path: path.join(__dirname, './dist'),
        filename: 'css/[name].[contenthash:8].css'
      }])
    }
  },
  configureWebpack: config => {
    // if (process.env.NODE_ENV.includes('production')) {
    //   config.output = {
    //     path: path.join(__dirname, './dist'),
    //     baseUrl: './',
    //     publicPath: './',
    //     filename: 'js/[name].[contenthash:8].js'
    //   }
    // }
  }
}

```




