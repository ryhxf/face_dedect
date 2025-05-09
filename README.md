代码放在release里面了，详情见B站视频讲解

接下来是针对环境安装的补充教程，可能新手会走很多坑。

## C++编译环境解决办法
如果你的本地没有C++编译环境，则需要安装**Visual Studio**，或者可以只安装**Visual Studio Build Tools**，为了简便， 我给了**Visual Studio Build Tools**的网址。
**https://visualstudio.microsoft.com/zh-hans/visual-cpp-build-tools/**
点击下载生成工具即可
打开下载的.exe文件进行安装，安装选项中只需选择**C++ 生成工具**选项即可，至于安装路径按需选择。
安装完成后，打开开始菜单找到并运行：**x64 Native Tools Command Prompt for VS 2022**
即可打开它路径下的命令行窗口，在该窗口下安装**Dlib**自带C++编译环境。

## Cmake安装
进入该网址下载安装包，正常安装即可
(https://github.com/Kitware/CMake/releases/download/v4.0.2/cmake-4.0.2-windows-x86_64.msi)

## python虚拟环境
python虚拟环境怎么建，可以用我视频中给的Conda，但是Conda对于很多人来说,可能安装比较困难，这里我用python虚拟环境来替代
在确保本地有python的情况下，在命令行窗口中
### 创建虚拟环境（此处路径换成你设置的虚拟环境路径，这里以某个face_detect文件夹举例）
```
python -m venv C:\Users\yyx\Desktop\face_detect
```
### 进入该环境（打开该环境的activate文件）
```
C:\Users\yyx\Desktop\face_detect\Scripts\activate
```

## Dlib库安装方法（注意，计算机建议在python虚拟环境下进行，本地python环境不建议，环境容易乱。嵌入式开发板可以无所谓，直接本地运行即可）
把dlib库下载下来
```
git clone https://github.com/davisking/dlib.git
```
跳转到dlib库
```
cd dlib
```
新建build文件夹
```
mkdir build
```
跳转到build文件夹
```
cd build
```
### 接下来是编译安装，要保证电脑上有cmake和其他上述环境，如果没有，自行安装
#### 如果是计算机
```
cmake .. -DDLIB_USE_CUDA=1 -DUSE_AVX_INSTRUCTIONS=1
```
#### 如果是Linux开发板
（以RDK X5为例，因为嵌入式开发板通常自带C++等编译环境，所以嵌入式版本不需要上面复杂的环境安装操作）
```
cmake ..
```



使用Cmake编译
```
cmake --build .
```
如果在过程中报错**No module named 'distutils'**，执行
```
pip install --upgrade setuptools
```
如果提示安装失败，或者没有对应版本，可能需要更新电脑的pip（某些人电脑可能pip版本过老）
```
python.exe -m pip install --upgrade pip
```
运行完再**pip install**即可

跳转回上个文件夹
```
cd ..
```

#### 如果是计算机
```
python setup.py install --set USE_AVX_INSTRUCTIONS=yes --set DLIB_USE_CUDA=yes
```
#### 如果是Linux开发板
```
sudo python setup.py install
```


### 还需要安装的python库
可以用清华源，加(-i https://pypi.tuna.tsinghua.edu.cn/simple)
```
pip install opencv-python -i https://pypi.tuna.tsinghua.edu.cn/simple
```
```
pip install opencv-python -i https://pypi.tuna.tsinghua.edu.cn/simple
```
我想到的可能涉及的环境问题都在里面了，在跑代码的时候，别忘了替换里面的文件路径（视频教程中有讲），为了能在任意条件下都能运行此代码，我用的都是绝对路径，如果觉得麻烦，也可以自行更换成相对路径。
