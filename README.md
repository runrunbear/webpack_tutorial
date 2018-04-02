最近在学习node，刚开始入门webpack。找到了这个教程，然后手把手做一遍。过程中碰到了一些难题我都标注了出来。

## Webpack 是什么?
> Webpack 是前端资源模块化管理和打包工具。
> Webpack 可以将许多松散的模块按照依赖和规则打包成符合生产环境部署的前端资源。
> Webpack 可以将按需加载的模块进行代码分隔，等到实际需要的时候再异步加载。
> Webpack 通过 loader 的转换，任何形式的资源都可以视作模块，比如 CommonJs 模块、 AMD 模块、 ES6 模块、CSS、图片、 JSON、Coffeescript、 LESS、 SASS 等。

![bundle your assets](http://upload-images.jianshu.io/upload_images/6171922-f40a5af399821919.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

对于模块的组织，通常有如下几种方法：
- 分开写几个 js 文件,使用 script 标签加载.
- CommonJS 进行同步加载, Node.js 就使用这种方式.
- AMD进行异步加载, require.js 使用这种方式.
- 新的 ES6 模块.

## Webpack 的特点
- 丰富的插件，流行的插件都有,方便进行开发工作.
- 大量的加载器，便于处理和加载各种静态资源.
- 将按需加载的模块进行代码分隔，等到实际需要的时候再异步加载.

## Webpack 的优势
- Webpack 以 commonJS 的形式来书写脚本，但对 AMD / CMD / ES6 模块 的支持也很全面，方便旧项目进行代码迁移。
- 所有资源都能模块化。
- 开发便捷，能替代部分 Grunt / Gulp 的工作，比如打包、压缩混淆、图片转 base64、SASS 解析成 CSS 等。
- 扩展性强，插件机制完善，特别是支持模块热替换（见  [**模块热替换**](http://www.css88.com/doc/webpack2/concepts/hot-module-replacement/) ）的功能让人眼前一亮。

## Webpack 与 Grunt / Gulp
 Webpack 和 Gulp / Grunt  并没有太多的可比性，Gulp / Grunt 是一种能够优化前端开发流程的自动化工具，而 Webpack 是一种模块化的解决方案，不过 Webpack 的优点使得 Webpack 可以替代 Gulp / Grunt 一部分工作。

Grunt / Gulp 的工作方式是：在一个配置文件中，指明对某些文件需要进行哪些处理,例如：编译、组合、压缩等任务的具体步骤，Grunt / Gulp 之后可以自动替你完成这些任务。Grunt / Gulp的工作流程如下图：

![Gulp / Grunt](http://upload-images.jianshu.io/upload_images/1031000-d0693c06bb3a00e3.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

Webpack 的工作方式是：把你的项目当做一个整体，通过一个给定的主文件（ 如：index.js ），Webpack 将从这个文件开始找到你的项目的所有依赖文件，使用 loaders 处理它们，最后打包为一个浏览器可识别的 JavaScript 文件。Webpack工作方式如下图：

![Webpack](http://upload-images.jianshu.io/upload_images/1031000-160bc667d3b6093a.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

如果实在要进行比较,Webpack 的处理速度更快更直接,因为 Webpack 的历史包袱小.Webpack 还能打包更多不同类型的文件。

## 开始使用 Webpack
初步了解 Webpack 后，就可以开始学习使用 Webpack。这里会以一个小的 Demo 为例子来一步一步进行动手学习!

### 新建 Webpack 项目

**1.** 创建文件夹
```
mkdir webpack_tutorial
```

**2.** 安装webpack
```
//全局安装
npm install -g webpack
//安装到你的项目目录
npm install --save-dev webpack
```

**3.** 创建package.json
```
cd webpack_tutorial
npm init // just use dufault
```

**4.** 创建app folder, public folder,  add Greeter.js main.js in app folder, and index.html in public folder
```
mkdir app
mkdir public
touch app/Greeter.js
touch app/main.js
touch public/index.html
```






### ------------ ###
感谢，基本上大部分都是从此教程得到的。教程的config的是webpack 2.0 版本 。我在学习中用到了webpack的3.0版本，中间还是有一些不一样的。还是十分感谢https://github.com/longhuicode/webpack-demo
