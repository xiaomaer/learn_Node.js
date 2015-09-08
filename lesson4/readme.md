### 本节将使用NPM提供的express模块，创建了一个强大的静态文件服务器。
		示例：你可以通过浏览器请求访问你放在public文件夹中任何文件，并进行展示，包括HTML、图片等任何东西。详细步骤如下:
#### 1、安装express模块
##### 打开cmd命令行界面，使用以下命令安装express模块
		e:
		npm install express
#### 2、创建JS文件:staticsever.js
		在E盘nodePrj目录下，创建staticsever.js文件，并输入以下JavaScript代码：
		var express = require('express'),  
		app = express();   
		app.use(express.static(__dirname + '/public'));  
		app.listen(8080);
#### 3、创建public文件夹
		在E盘nodePrj目录下，创建public文件夹，并把1.jpg、2.jpg、index.html放在public文件夹。
#### 4、切换命令行界面的路径
		使用以下命令，切换命令行界面当前路径到“E:\nodePrj”，并运行staticsever.js文件。
		cd nodePrj
		node staticsever.js
#### 5、访问public文件夹中的图片
		在浏览器中输入“http://localhost:8080/1.jpg”或“http://localhost:8080/index.html”来访问文件。结果如下图所示：
![img1](https://github.com/xiaomaer/learn_Node.js/blob/master/lesson4/3.png)
![img1](https://github.com/xiaomaer/learn_Node.js/blob/master/lesson4/4.png)
#### 6、退出交互界面
		使用Ctrl+C键来退出Node命令行交互界面
#### 详细代码操作见下图所示：
![img1](https://github.com/xiaomaer/learn_Node.js/blob/master/lesson4/1.png)
![img2](https://github.com/xiaomaer/learn_Node.js/blob/master/lesson4/2.png)
