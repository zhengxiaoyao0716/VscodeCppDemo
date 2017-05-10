# VSCodeCppDemo
## Try to develop C/C++ use vscode in windows.
***
2017-05-10: Add Linux support. [general-makefile](https://github.com/zhengxiaoyao0716/general-makefile)
***
#### Visual Studio Code确实不错，各方面都挺适合我。
#### 但最近有节数据结构课要用到C，而我电脑上并没有C的开发环境
```
vc6早已卸了（再也不想碰它）
Visual Studio重装电脑时掉，后来也没怎么写C#，就没懒得装了。
当然，虚拟机里倒是有天然的gcc，但用着麻烦。。。
```
##### 本来也试着装了下vs2015community，太大了，下了很久放弃了。
##### v6上的资源也不好用。于是乎，决定用VSC弄个简单的C开发环境，也就写作业将就用用
***
##### 翻查VSC插件时，发现有微软官方C/C++支持时我是欣喜若狂的~~~
##### 支持Ubuntu，支持MacOS，嗯，不错，还跨平台，，，wait——
##### ——纳尼？？？不支持Windows？！ntm在。5西奥。。。
```
不过没关系，本来也没打算得到多完美的支持，能用就行。
就当是巩固基础，断奶自立，从命令行编译开始吧。
于是，就有了这个临时项目。等哪一天Vscode支持windows了，它也就废了。
这个项目本身也没啥可说的，关键就是一个makefile。
从网上找了个通用模板，按需定制了一下。
```
***
### 如果你也需要这么一个轻量的C临时开发环境，又或者想体验一下断奶的生活：
1. 首先装个mingw-w64，配置好环境变量，就有了windows下的gcc环境。具体自行Google
2. 然后整理你的C/C++工程文件结构，像这样：
``` sh
${Project}/
    .vscode/  #vsc配置目录
        task.json  #把本项目的同名文件复制到这
    lib/  #工程依赖
        ...
    out/  #构建目录
        build_win/  # Linux下为.build_lin
            module_yyy/
                ...
            xxx.o
            xxx.d
            ...
        ${Project}.exe  # 构建完成的可执行文件，Linux下无后缀
    src/  #工程源码
        main/  #源文件目录，.cpp
            xxx.cpp
            module_yyy/
                ...
            ...
        head/  #头文件目录，.h
            xxx.h
            module_yyy/
                ...
            ...
    Makefile  #把本项目的Makefile复制到这
    ...
```
或者不喜欢这个文件结构？自己修改makefile好了。
3. 打开Vscode，写个helloworld，敲下Ctrl+Shift+B。
***
最后，不要吐槽那个作为Demo的2048小游戏，很久以前写的了，有已知bug，懒得修复了。
如果你恰巧喜欢或需要它，不妨去看看这个[Android版](https://github.com/zhengxiaoyao0716/Digimon2048)