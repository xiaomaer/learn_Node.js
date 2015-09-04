本节将记录我在window7 64bit操作系统上如何安装Node.js v0.12.7？

### 1、如何在window上安装Node.js v0.12.7？ 
* 根据自己电脑的配置，在Node.js官网上下载Windows Installer (.msi)文件，[点击这里进入下载网址](https://nodejs.org/en/download/)。
* 双击下载好的“node-v0.12.7-x64.msi”文件进行安装，出现“finish”界面表示安装完成。
* 通过以上步骤会将node.exe文件安装到自己指定的路径下，并将该该路径添加到系统的PATH环境变量。默认路径为“C:\Program Files (x86)\nodejs\”，我把它安装在“D:\Program Files\nodejs\”。

### 2、安装好Node.js下一步做什么呢？
* 从开始菜单找到Node.js文件夹，然后点击该文件夹下的“Node.js command prompt”打开命令行窗口，如下图所示：

* 在该命令行窗口直接输入以下命令查看Node.js的版本号  
        node -v
显示Node.js的版本号 
        v0.12.7
* 在该命令行窗口直接输入以下命令，Node.js将会切换到命令行交互界面，你可以在这里执行JavaScript代码。如下图所示：
        node
* 也可以点击“开始菜单”Node.js文件夹下的Node.js打开交互界面，如下图所示： 

### 3、简单使用
* 执行JavaScript代码
* 在交互界面输入“console.log("Hello World");”，然后按回车键。Node便开始执行该代码，并输出“Hello World”，同时打印出“undefined”。这是因为每条命令都会返回一个值，而console.log没有任何返回，故输出“undefined”。代码如下图所示： 

* 使用"node xx.js"命令执行JavaScript文件 
* 首先创建js文件，如文件名为helloword.js，在该文件中输入以下代码： 
        console.log('Hello World!');
* 然后在命令行界面输入"node helloword.js"命令，执行文件中JavaScript代码，并输出“Hello World”。如下图所示： 

### 4、注意和问题
* Node.js V0.6.0版本以后，NPM已经包含在在Node.js安装包中了，因此不再需要单独安装Node.js和NPM了。
* 使用"node xx.js"命令运行JS文件时，注意把路径切换到"xx.js"所在的路径下，如xx.js在"d:\Program Files\nodejs\nodePrj\"文件夹下，但是命令运行窗口默认路径是"d:\Program Files\nodejs",要先通过cd等命令切换到"d:\Program Files\nodejs\nodePrj\"下，在执行命令。
* Node.js运行的JS文件应该放在哪里？  
* 对于初学者的我，在学习的过程中遇到了这样的问题，记录于此，希望帮助和我一样迷茫的同学。 
* 对于该问题，通过查询资料和自己的测试，答案如下：
* 对于普通的JS文件，没用使用任何模块（Node.js内置的模块还是NPM提供的模块）,在这种情况下，JS文件可以放在任意位置。
* 对于只使用Node.js内置的模块或自定义的模块的JS文件，JS文件也是可以放在任意位置。  
* 对于使用了NPM提供的模块的JS文件，JS文件位置必须放在Node.js安装路径下面。例如：在我的电脑上，Node.js安装在“D:\Program Files\nodejs"下，因此使用了NPM提供包的JS文件必须放在该目录下，否则在运行JS文件时，会报错（找不到文件使用的模块）。
    
