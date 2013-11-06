#Howto JavaScript
===
介绍Javascript的开发工作起步说明

## JavaScript语法
- [官网](https://developer.mozilla.org/zh-CN/docs/Web/JavaScript)
- [中文入门](http://www.w3school.com.cn/js/)

## NodeJS
[NodeJS](http://nodejs.org)是基于Chrome Javascript引擎V8的平台，适用于开发高速、可扩展的网络应用。

### 特点
- `事件驱动`
- `非阻塞I/O`


### Installation

- [NodeJS Download](http://nodejs.org/download/)下载最新版本
- 安装下载版本

创建自己第一个NodeJS应用服务  

 	$ npm install -g express    
	$ express /tmp/foo && cd /tmp/foo  
	$ npm install  
	$ node app  
在浏览器中打开 [http://localhost:3000](http://localhost:3000)

### NPM
NPM [Node Packaged Modules](https://github.com/isaacs/npm)是NodeJS的包管理工具。将你从麻烦的第三方库依赖管理等麻烦事情中解放出来。

搜索存在的第三方库：  

- [npmjs](https://npmjs.org)  
- [node-modules](http://node-modules.com/)  
- [nipster](http://eirikb.github.io/nipster/)  

定位到需要第三方库以后可以根据关键字[安装](https://npmjs.org/doc/install.html)

你也可以通过NPM[发布](https://npmjs.org/doc/publish.html)自己的第三方库


### Express
[express](https://github.com/visionmedia/express)是`NodeJS`中应用最广泛的Web开发框架，没有之一。脱胎于[Ruby](https://www.ruby-lang.org/zh_cn/)的[Sinatra](https://github.com/sinatra/sinatra)框架，轻量级、灵活、快速。

write by [TJ Holowaychuk](https://github.com/visionmedia)

### Jade
[jade](https://github.com/visionmedia/jade)是一种HTML模板引擎，以精炼的语法描述HTML，渲染输出动态的内容。

- Express默认模板引擎
- 通常在后端做渲染，前端浏览器最好预编译成Javascript，否则Jade尺寸较大。

### Mocha
[mocha](https://github.com/visionmedia/mocha)测试框架，支持BDD、TDD等多种形式，我们通常采用BDD中的[should.js](https://github.com/visionmedia/should.js)来进行测试

- `unit test`  模块基本的测试。
- `acceptance test`  最终使用者模拟测试。

### Restful
- `Web Service`的一种，通常在移动互联领域采用这种形式。
- 数据封装格式`JSON`，简单、轻量级、I/O开销小。

### 参考
- [NodeJS入门书籍](http://www.nodebeginner.org/index-zh-cn.html)
- [Expressjs官网](http://expressjs.com/)
- [Restful Sample](http://www.peej.co.uk/articles/restfully-delicious.html)


## AngularJS
[AngularJS](http://angularjs.org/)是前端Web应用框架，可以将业务向客户端方向推移。

### 特性

* 前端动态渲染
* 数据双向绑定
* 服务端通讯
* 组件化

在众多的前端MVC中AngularJS只是其中一种，但是社区比较活跃，成熟的较好的一种。对前端MVC入门的了解可以参考[ToDoMVC](http://todomvc.com/)

### Bower
[bower](https://github.com/bower/bower)是Web前端的一个包管理工具，用了管理前端代码的依赖关系。与NodeJS的NPM很类似。

### 组件
搜索Angular第三方组件

- [ngmodules](http://ngmodules.org/) 需要翻墙。建议[goagent](https://code.google.com/p/goagent/)
 
### 参考

- [AngularJS官网教程](http://docs.angularjs.org/tutorial)
- [AngularJS案例](http://builtwith.angularjs.org/)
- [MEAN AngularJS+Express+Mongo+Node框架](https://github.com/linnovate/mean)

## 工具链

### 编辑器

- [TextMate](https://github.com/textmate/textmate) 开源，Mac OS X Lion 10.7+，很多牛人用。
- [sublieme Text](http://www.sublimetext.com/) USD$70，可以免费试用， 全平台。

上述两种编辑器都是业内比较主流的工具，社区活跃。都支持插件模式，并且插件的种类丰富。