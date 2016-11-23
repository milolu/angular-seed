# spa-seed

## 项目介绍
本项目是一个利用webpack架构的**single page web application**脚手架

## 使用说明
- 全局安装webpack和webpack-dev-server，如果已经装过那可以跳过这一步
```bash
$ npm install --global webpack webpack-dev-server
```

- 本项目使用包管理工具NPM，因此需要先把本项目所依赖的包下载下来：
```
$ npm install
```

- 编译程序，生成的所有代码在`build`目录内。
```
$ npm run build # 生成生产环境的代码。用npm run watch或npm run dev可生成开发环境的代码
```

- 启动服务器，推荐直接使用webpack-dev-server
```
$ npm run start
```

- 打开浏览器，在地址栏里输入`http://localhost:8080`，Duang！页面就出来了！


## CLI命令(npm scripts)
| 命令            | 作用&效果          |
| --------------- | ------------- |
| npm run build   | 根据`webpack.config.js`，build出一份生产环境的代码 |
| npm run dev     | 根据`webpack.dev.config.js`，build出一份开发环境的代码 |
| npm run watch   | 在`npm run dev`的基础上添加`-- watch`，实时监控源文件，建议开发时使用这项 |
| npm run start   | 开启webpack-dev-server，然后就可以在 http://localhost:8080/ 查看成品了 |
| npm run profile | 显示编译过程中每一项资源的耗时，用来调优的 |
| npm run dll     | 生成Dll文件，每次升级第三方库时都需要重新执行一遍 |
| npm run clean   | 清除tmp及build文件夹 |


## 目录结构说明
```
├─.tmp # 编译编译临时文件夹
├─build # 编译后生成的所有代码、资源
├─node_modules # 利用npm管理的所有包及其依赖
├─npm-scripts # 一些npm脚本
├─src # 业务代码
├─static # 静态文件夹（将直接拷贝到build文件夹）
├─vendor # 所有不能用npm管理的第三方库（将直接拷贝到build文件夹）
├─.babelrc # babel的配置文件
├─.eslintrc # ESLint的配置文件
├─.jslintrc # ESLint的配置文件, jslint规则
├─package.json # npm的配置文件
├─webpack-config # webpack的配置文件目录
├─webpack.config.js # webpack的发布配置文件
├─webpack.dev.config.js # webpack的开发配置文件
└─src # 当前项目的源码
	├─index.html # 入口html
	├─app.js # 入口js
    ├─resource # 代码中需要引用的资源文件夹
    ├─modules # 各个页面独有的部分，如入口文件、只有该页面使用到的css、模板文件等
    │  	├─index # 业务模块
    │  	│  ├─index.html
    │  	│  ├─index.service.js
    │  	│  └─index.js
    │  	└─user # 业务模块
    │      ├─user.html
    │      ├─user.service.js
    │      └─user.js 
    ├─scss # 样式代码
    └─components # 各个页面使用到的公共组件
	    ├─app.ctrl.js # controller配置
	    ├─app.service.js # service配置
	    ├─app.request.js # 请求配置
	    ├─app.error.js # 公用的图片资源
	    ├─app.common.js # 公共函数
	    ├─tree # 树结构
	    │  ├─tree.js
	    │  ├─tree.scss
	    │  └─img
	    ├─grid # 与业务逻辑无关的库都可以放到这里
	    │  ├─grid.js
	    │  ├─grid.scss
	    │  └─img
	    └─dialog # 业务逻辑
```


## 更新日志

### 1.0.0 (2016-11-23)