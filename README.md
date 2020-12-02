﻿# VSCode配置OpenGL工程

### 第一步：

首先配置C++环境，已配置的可跳过这一步，没配置的可以点下面链接：

https://github.com/hu243285237/Cpp_Study/tree/master/VSCodeConfigCpp

### 第二步：

构建我们开发OpenGL的工具，我这里使用的GLFW_3.2.1，可以到它的官网下载：

https://www.glfw.org/download.html

（Windows pre-compiled binaries是指已经构建好的GLFW，可以直接下载来使用，如果你和我一样是Win10系统并且用的MinGW32位编译，可以直接下载这个，这里我们下载32位的）

（SourcePackage指的是源文件，下载完之后还需要使用CMake之类的工具来构建GLFW，如果你不确定你电脑的环境能否支持Windows pre-compiled binaries里已经构建好的GLFW，可以下载SourcePackage，但流程也会相对复杂，这里不详细说明）

![ScreenShot](https://raw.githubusercontent.com/hu243285237/VSCodeConfigOpenGL/master/images/screenshot01.png)

### 第三步：

现在新建一个vscode工程（就是一个文件夹），在.vscode文件夹创建一个c_cpp_properties.json，还是用之前C++配置的，直接拷贝过来就好。（经测试，也可以省略这一步，不需要创建json）

![ScreenShot](https://raw.githubusercontent.com/hu243285237/VSCodeConfigOpenGL/master/images/screenshot02.png)

### 第四步：

将刚才下载的glfw-3.2.1.bin.WIN32解压，找到lib-mingw和include这两个文件夹，将里面的.h文件.a文件.dll文件都拷贝到工程里。

然后再找到MinGW的安装目录，将lib文件夹里的libopengl32.a也拷贝进工程。

![ScreenShot](https://raw.githubusercontent.com/hu243285237/VSCodeConfigOpenGL/master/images/screenshot03.png)

### 第五步：

必要的文件我们都有了，这时候创建一个main.cpp文件，就可以使用GLFW和GL的库来编写OpenGL代码了，代码案例可以参考Demo_1的main.cpp（在外面一层目录）。

### 第六步：

在终端输入以下两条命令：

g++ main.cpp -o test libglfw3dll.a libopengl32.a

.\test

就可以看到绘制出来的窗口了

![ScreenShot](https://raw.githubusercontent.com/hu243285237/VSCodeConfigOpenGL/master/images/screenshot04.png)

![ScreenShot](https://raw.githubusercontent.com/hu243285237/VSCodeConfigOpenGL/master/images/screenshot05.png)