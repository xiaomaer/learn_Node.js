###问题1:Node.js运行的JS文件应该放在哪里？
* 对于初学者的我，在学习的过程中遇到了这样的问题，记录于此，希望帮助和我一样迷茫的同学。
* 对于该问题，通过查询资料和自己的测试，答案如下：
  * JS文件可以放在任意位置。
  * 注意：对于使用了NPM提供的模块的JS文件，JS文件位置必须与NPM安装的模块来自同一祖先目录下（如：父级、父父级等）。例如：NPM把模块安装在“E:\node_modules”下，因此JS文件必须放在E盘目录下（如：“E:\”或“E:\nodePrj”等），否则在运行JS文件时，会报错（cannot find module）。
