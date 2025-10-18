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

如希望生成 Windows 的 nmake 编译，可以：

```bash
cmake -G "NMake Makefiles" ..
```

如生成 Windows 的某个版本的 Visual Studio 工程：

```bash
cmake -G "Visual Studio 17 2022" .
```
