=================
OmegaT UI
=================

语言资源识别
===================
Java 开发的程序，语言资源一般存储在.properties中，具体到这个项目，需要翻译的内容为：
* scripts文件中的各properties文件
* src/org/omegat中的Bundle.properties



使用Alchemy Catalyst 10进行文件准备
=====================================
因为这是常见格式，Alchemy Catalyst可以直接解析properties文件，具体步骤如下：


#. 新建catalyst项目，将上方资源导入
#. 使用project division功能分发和打包所需翻译资源
#. 翻译完成后merge 分发出的ttk项目
#. 导出中文properties文件


指定程序启动的语言
=============================
在Windows平台下
* cd [full path to OmegaT]
* java -jar OmegaT.jar resource-bundle=[name of bundle with full path]

例如启动中文： ``java -jar OmegaT.jar resource-bundle=Bundle_zh_CN.properties``