---
layout: post
title: "【C++】How to transfer .cpp file to shared file .so 在Linux系统下的QtCreator中进行cpp文件与共享动态库.so文件的转换"
date: 2021-9-1
excerpt: "In qtcreator"
tags: [Notes,C++]
project: ture
timeline: true
---
<script type="text/javascript" src="http://tajs.qq.com/stats?sId=66526224" charset="UTF-8"></script>


	1. 对Project进行构建/重新构建

	2. 在MyProject的build目录下找到要进行转换的.o文件myprogramme.o  yeah！

	3. 在命令行输入 gcc -shared myprogramme.o -o libxxx.so(libxxx中最好不要丢掉前缀),然后就会看到生成的一个.so文件。

    此时已经完成了转换啦！接下来是测试

    4. 用与之前在QTCreator中引入.so动态共享库文件的方法一样，通过自定义库的形式把动态库链接到Project中。
    
    ```
    add_library(<自定义的被链接库名> [SHARED] IMPORTED)
    set_target_properties(
        <自定义的被链接库名>
        PROPERTIES IMPORTED_LOCATION
        ${CMAKE_SOURCE_DIR}/<在目录下自建的文件夹名>/<共享库的文件名.so>
    )
    include_directories(.)
    ```

    5. 把.h文件和.so文件都放入用于测试的main.cpp的目录下，然后照例引入头文件，并在main中调用函数来进行测试。记得注意，如果头文件是用c写的，就要用extern “C”{}括起来



    
