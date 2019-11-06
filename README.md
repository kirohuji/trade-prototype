# 贸易网站 基本原型阶段

## 目标

此阶段,将生成一个静态网站,网站参考:[gemfanhobby](http://www.gemfanhobby.com/)

## 前置条件

项目使用pattern lab,界面基于sketch进行设计和开发

# 搭建pattern lab


```javascript
  npm create pattern-lab
```

# 项目基本环境搭建

## 初始化项目

从 Gitlab 中项目之后,请执行

```javascript
  npm init
```

## 下载 Gulp 工具进行构建

```javascript
  npm install gulp -g
```

进行项目的初始化

> 目前`Semantic ui`官方版本出现了一些问题,所以我们使用社区分支`Fomantic-ui`

## 构建 Semantic ui

第一步,下载 fomantic-ui:

```javascript
   npm install --save fomantic-ui
```

第二步,根据提示生成 `semantic` 文件夹(请不要将 `semantic` 跟踪到 `git` 中):

如果没有触发生成的脚本命令

首先到`node_modules`中,之后到`semantic-ui`目录下,可以看到有个`gulpfile.js`,这个文件是用来进行管理项目构建的

使用

```javascript
  gulp install
```

即可构建项目

最终结果,你应该会在根目录中生成一个你要的`semantic`文件夹,或者你自己制定的文件夹,之后在`package.json`也能看到你的依赖

第三步,你将需要构建您在网站上使用的 CSS 和 JavaScript 的分发版本.

这是`semantic/dist`.为此，在安装程序创建的目录(`semantic/`)中运行以下命令.

```javascript
  npx gulp build
```

完成后，您应该有一个`dist/`包含所有 CSS 和 JavaScript 文件的新目录.

还有一个 semantic.json,这个文件是用来配置 semantic.json 构建的

## 自动安装和持续集成 2.2 的新功能

我们 `semantic.json` 在 `2.2` 中添加了新设置，以帮助简化 `CLI` 或其他自动化部署的使用。

在环境 `semantic.json` 配置中指定`autoInstall: true` 将阻止运行时 `npm install`允许自动部署的任何用户提示。

第四步,引入文件到网页中

```html
<!-- 你 必须 包含 jQuery 在 Fomantic 之前 -->
<script src="https://cdn.jsdelivr.net/npm/jquery@3.3.1/dist/jquery.min.js"></script>
<link rel="stylesheet" type="text/css" href="/semantic/dist/semantic.min.css" />
<script src="/semantic/dist/semantic.min.js"></script>
```

## 更新

如果您通过 NPM 使用 Fomantic-UI

```javascript
  npm update fomantic-ui
```

这将安装最新版本,并将运行交互式安装程序以安装所需的任何新文件.安装程序完成后,您将需要重建 `Fomantic-UI`.

## 项目控件版本更新

如果`git pull` 项目之后发现`semantic.json`有改动时,请参考改动的信心,重新`gulp install`和`npx gulp build`
