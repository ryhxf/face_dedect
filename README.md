代码放在release里面了，详情见B站视频讲解

接下来是针对环境安装的补充教程，可能新手会走很多坑。

如果你的本地没有C++编译环境，则需要安装`Visual Studio`，或者可以只安装`Visual Studio Build Tools`，为了简便， 我给了`Visual Studio Build Tools`的网址。
`https://visualstudio.microsoft.com/zh-hans/visual-cpp-build-tools/`
点击下载生成工具即可
打开下载的.exe文件进行安装，安装选项中只需选择"C++ 生成工具"选项即可，至于安装路径按需选择。
安装完成后，打开开始菜单找到并运行：`x64 Native Tools Command Prompt for VS 2022`
即可打开它路径下的命令行窗口，在该窗口下安装Dlib自带C++编译环境。

Cmake安装
进入该网址下载安装包，正常安装即可
`https://github.com/Kitware/CMake/releases/download/v4.0.2/cmake-4.0.2-windows-x86_64.msi`

python虚拟环境怎么建，可以用我视频中给的Conda，但是Conda对于很多人来说

```
mkdir build
```
