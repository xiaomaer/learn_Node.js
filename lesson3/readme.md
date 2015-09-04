          本节将记录如何使用NPM安装、下载和卸载模块（包）？
          上一节中已经介绍了，Node.js v0.6.0以后的版本，NPM已经被包含在Node.js安装包中了，不需要独立安装Node.js和NPM。
          NPM非常强大，它有成千上万个模块可帮我们解决遇到的大部分典型问题，它的代码库集中管理了所有的公共模块。
#### 1、NPM操作模式？
> NPM的操作主要有两种模式：全局和本地。这两种模式会影响包存放的目录结构，以及Node加载包时的顺序。本地模式是NPM的默认操作模式，在这个模式下，NPM只工作在工作目录下，不会造成系统范围的修改，这个模式让你在某个Node程序下尽情地安装，测试模块，而不会影响你电脑上的其他Node程序。全局模式适合那些将被很多程序使用，而且总是被全局加载的公共模块。
>
> 如果你不知道一个模块该用哪个模式安装，那就应该使用本地模式。如果一个模块的作者需要某个模块被全局的安装，通常他会在安装说明里指出。
#### 2、NPM安装模块
##### ①本地安装
> 在命令行窗口输入以下命令：
>
> > npm install 模块名
>
> > 在本地模式下，NPM会把包安装在当前目录下的"node_modules\包名"目录下。例如：运行命令的当前路径为“d:\nodePrj\”,包将会安装到“d:\nodePrj\node_modules\包名”文件夹下;运行命令的当前路径为“E:\”,包将会安装到“e:\node_modules、”文件夹下
>
> 安装某个特定的版本模块，命令如下：
>
> > npm install 模块名@版本号
##### ②全局安装
> 在命令行窗口输入以下命令：
>
> > npm install -g 模块名
>
> >在全局模式下面，NPM会把包安装到C:\Users\Administrator\AppData\Roaming\npm\node_modules\expressm目录下。
>
#### 3、NPM卸载模块
##### ①卸载本地模块
> 在命令行窗口输入以下命令：
>
> > npm uninstall 模块名
##### ②卸载全局模块
> 在命令行窗口输入以下命令：
>
> > npm uninstall -g 模块名
#### 4、NPM更新模块
##### ①更新本地模块
> 在命令行窗口输入以下命令：
>
> > npm update 模块名
②更新全局模块
> 在命令行窗口输入以下命令：
> 
> > npm update -g 模块名
#### 5、处理依赖关系
> NPM不仅安装你需要的模块包，而且还会安装这些模块所依赖的其它模块，例如：安装模块A，而A又依赖模块B和C，那么在你安装A的时候B和C同时会被安装到./node_modules/A/node_modules目录下。
> 
> 使用下面命令安装express模块
>
>　>　npm install express
> >　然后会输出下图所示的信息：
这告诉你nexpress模块依赖escape、merge、array等模块，并且还指出了安装的版本。如果你现在去查看./node_modules/express/node_modules目录，你会发现这x些模块已经被安装了。
⑥使用package.json文件定义依赖关系
package.json文件包含了应用程序的基本信息。其中“dependencies”部分描述了你想安装模块的名称和版本。当开始编写一个应用程序时，可以在应用程序根目录创建一个package.json文件来定义应用程序的元数据。例如：一个叫MyApp的应用程序依赖sax,nano和request模块，只需要建立这样一个package.json：
     {  
                  "name" : "MyApp", 
                  "version" : "1.0.0", 
                  "dependencies" : { 
                                   "sax" : "0.3.x", 
                                   "nano" : "*", 
                                   "request" : ">0.2.0" 
                  } 
      }
以上JSON数据指定了MyApp应用，依赖0.3版本的sax，任意版本的nano，以及版本高于0.2.0的request模块。
注意：你可能发现，如果你指定了name和version字段，NPM会不工作，这只会发生在旧版本的NPM，因为最初NPM是针对公共模块使用的，而不是私有程序。
然后，在应用程序的根目录，执行以下命令自动的下载和安装缺失的模块。
npm install
也可以通过下面的命令把所有本地模块更新到符合你定义的依赖项设置的最新版本：
npm update

##### `注意：`NPM安装模块的位置要与JS文件的位置位于同一祖先级（父级、父父级等）下，例如：NPM把模块安装在“E:\node_modules”下，因此JS文件必须放在E盘目录下（如：“E:\”或“E:\nodePrj”等），否则在运行JS文件时，会报错（cannot find module）。

