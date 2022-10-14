# Lua 开发环境配置

![](img/Snipaste_2022-10-14_20-36-02.png)

<b>官网链接：[http://www.lua.org/](http://www.lua.org/) </b>

<hr/>

### 使用IDEA（JetBrains公司所有的IDE）配置插件搭建 Lua 开发环境

1. 下载 Lua SDK：

[Lua 解释器 下载地址](https://sourceforge.net/projects/luabinaries/files/5.3.4/Tools%20Executables/lua-5.3.4_Win64_bin.zip)

下面是官方提供的源码下载地址，可以自行编译：

![](img/Snipaste_2022-10-14_20-45-45.png)

下载完成之后，在windows中某个目录解压:

![](img/Snipaste_2022-10-14_21-46-59.png)

2. 进入IDEA（JetBrains公司所有的IDE）中，下载安装 Lua插件: Emmylua,安装后重启idea：

![](img/Snipaste_2022-10-14_20-49-51.png)

3. 配置编译器位置。在创建的工程中，创建一个Lua文件源目录，编写Lua脚本，配置解释器位置：

![](img/Snipaste_2022-10-14_21-51-25.png)

配置Lua 解释器的地址（注意是 luaXXX.exe !!!）：

![](img/Snipaste_2022-10-14_21-51-57.png)

4. 解释执行程序：

![](img/Snipaste_2022-10-14_21-54-02.png)

<hr>

### 使用 Windows安装包方法安装：

[👉👉 Lua Windows解释器 GitHub地址](https://github.com/rjpcomputing/luaforwindows)

进入Releases 中下载 exe 执行文件（Lua 解释器安装包），双击下一步安装！

![](img/Snipaste_2022-10-14_21-58-10.png)
