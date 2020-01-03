### Jw-client脚手架

#### 一、介绍

jw-client是一个基于React+(Antd或Material-ui)进行快速开发Joywok项目的辅助工具。

#### 二、安装

```shell
npm install jw-client -g
```

#### 三、使用方法
	
##### jw-client init [name]

1. 使用哪种UI框

	Material https://material-ui.com/zh/

	Antd https://ant.design/index-cn

2. 项目名称
	
	如果在命令行后面不输入名称，此时需要输入在本地生成的文件夹名称。如果已经存在则会提示是否覆盖已存在目录。

3. 项目注释

	在package.json中的description字段。

4. 所有者

	在package.json中的author字段。

5. 开发平台(平台不同，引入的组件库不同)（此命令仅限基于antd生成的框架使用）
	
	Web（开发web平台使用antd）

	Mobile（开发Mobile平台是用antd-mobile）

	开发不同的平台则使用的Joywok的封装的ui组件不同。web平台使用jw-components,Mobile平台是用jw-components-mobile

6. 是否包含JSSDK开发框架（此命令仅限基于antd生成的框架使用）
	
		是否引入JSSDK开发文件

```shell
	<script type="text/javascript" src="https://www.joywok.com/dist/scripts/jssdk.js"></script>
	Joywok 面向开发者提供的基于 Joywok 手机客户端封装（移动端拍照、选图、语音等手机系统能力）的工具包
	<script type="text/javascript" src="https://www.joywok.com/public/scripts/connect-ide.js"></script>
	Joywok 面向开发者提供的 IDE 链接文件
```

7. 是否包含JSSDK免登功能（此命令仅限基于antd生成的框架使用）

	项目中是否包含JSSDK免登功能，此功能需要上面的JSSDK开发框架

```shell
	jw.config({
		debug: false,
		appid: "xxxxxxxx", 
		timestamp: 0, 
		nonceStr: "", 
		signature: "",
		app_access_token: "",
		corpid: "xxxxxxx"
	});
	jw.ready = function () {
		app.router(require("./router"));
		app.start("#root");
	}
```

8. 使用什么方式安装node_module

	有两种选择，npm install和yarn install

```shell
温馨提示：在~./npmrc文件中添加registry=https://registry.npm.taobao.org 可以用设置npm install的源为淘宝源。
```

后续程序将会自动下载选择的UI框架的基础开发包，替换对应的文件，并自动安装node_modules依赖模块。

一切就绪后，使用npm start启动项目即可开始开发。

##### jw-client module

此命令目前仅限基于antd生成的框架，用于快速生成开发模块（包含Model、Servers、Routers等）。

	
