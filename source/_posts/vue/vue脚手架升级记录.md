---
title: vue脚手架升级记录
tags: vue
categories: vue
date: 2019-12-19
---


##### 一、版本情况
1. 从脚手架2.x版本升级到4.1.1

##### 二、配置对比
1. 从官网下载2.x 的脚手架下来，然后用文件夹对比工具对比了一下config目录以及build目录，目前自己项目之间改动的差异，发现有以下改动的地方要留意


2. 官网2.x cli 和 官网 4.1.1 cli脚手架目录差异

3. package.json 对比情况

- 官方2.x 对比 官方 4.1.1

- 自己项目 对比 2.x 多的依赖包

##### 三、升级计划
1. 添加相应的 vue.config.js 配置
  1.1 设置代理，看看是否还有 changeOrigin 参数，是否需要添加这个参数（调研发现，继续保留，需要加上）
  1.2 改动端口为8090
  1.3 改动浏览器自动启动（默认关闭）
  1.4 看是否需要重新设置 assetsPublicPath （新版本叫publicPath）
  1.5 看是否还有 productionSourceMap ，需要调整为 false （有，需要调整）
  1.6 引入 babel-polyfill （有所改动，详情在vue.config.js）
  1.7 引入 jq （jq目前本项目用的是script脚本引入，所以不需要额外去配置jq相应的参数）
  1.8 rules 规则 include 调整，将 element-ui 相关的加上 （这个目前已经没有了）
  1.9 生产环境下将相应的调试关闭

```javascript
const UglifyJsPlugin = require('uglifyjs-webpack-plugin')
 new UglifyJsPlugin({
                uglifyOptions: {
                  compress: {
                    warnings: false,
                    drop_debugger: true, //移除 debugger
                    drop_console: true,  //删除所有console语句，可以兼容IE
                    collapse_vars: true,  //内嵌已定义但只使用一次的变量
                    reduce_vars: true,  //提取使用多次但没定义的静态值到变量
                    conditionals:true //优化if等判断以及条件选择
                  }
                },
                sourceMap: false,
                parallel: true
              })

```
  
2. 调整表层目录的文件位置
    2.1 将表层的 index.html 和 static 目录还有 theme 目录全部挪到了 public 下

  2.2 调整目录之后，需要调整相应代码的 static 目录路径，比如 ../../../../static  要改成 ../../../../public/static 等等
    
##### 四、最终 vue.config.js 配置如下：

```javascript
// vue.config.js
const path = require('path');
const resolve = dir => path.resolve(__dirname, dir);
const UglifyJsPlugin = require('uglifyjs-webpack-plugin')
module.exports = {
    publicPath: process.env.NODE_ENV === 'production' ? '/manager/static/mgr/': './',
    productionSourceMap: false,
    devServer: {
        open: true,
        port: 8090,
        proxy: 'http://djdev.qiweioa.cn',
        overlay: {
            warnings: true,
            errors: true
        },
        publicPath: '/'
    },
    configureWebpack: config =>  {
        config.resolve.extensions = ['.js', '.vue', '.json', '.css']
        if (process.env.NODE_ENV === 'production') {
            // 为生产环境修改配置...
            new UglifyJsPlugin({
                uglifyOptions: {
                  compress: {
                    warnings: false,
                    drop_debugger: true, //移除 debugger
                    drop_console: true,  //删除所有console语句，可以兼容IE
                    collapse_vars: true,  //内嵌已定义但只使用一次的变量
                    reduce_vars: true,  //提取使用多次但没定义的静态值到变量
                    conditionals:true //优化if等判断以及条件选择
                  }
                },
                sourceMap: false,
                parallel: true
              })
        } else {
            // 为开发环境修改配置...
        }
      },
      chainWebpack: config => {
        config.resolve.alias
                .set('vue$', 'vue/dist/vue.esm.js')
                .set('@', resolve('src'))
        config.entry.app = ['babel-polyfill', './src/main.js'];
    }
}


```
