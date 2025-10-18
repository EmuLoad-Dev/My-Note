> 官方安装地址

https://cmake.org/download/

> 简单示例

```cmake
cmake_minimum_required(VERSION 3.10)
project(MyProject CXX)

# 添加源文件
add_executable(MyExecutable
    source/main.cpp
)

# 设置 C++ 标准
set(CMAKE_CXX_STANDARD 11)
```


> 指定编译生成方式

Windows NMake：

```bash
cmake -G "NMake Makefiles" ..
```

Windows Visual Studio 17 2022：

```bash
cmake -G "Visual Studio 17 2022" .
```
