> 生成 release 版本的 so。

1. 用 ndk-build 命令行指定

```bash
ndk-build NDK_BUILD_TYPE=release
```

2. 在 Application.mk 文件直接指定。

```cmake
# Application.mk 文件内
APP_OPTIM := release
```

> Mac 下的 ndk-build 一般主目录位置。

```
/Users/[username]/Library/Android/sdk/ndk
```

> 检测 so 文件是否是 16KB 对齐的命令行。

```bash
$NDK_ROOT/toolchains/llvm/prebuilt/darwin-x86_64/bin/llvm-objdump -p libtest.so | grep LOAD
```

打印示例

```plaintext
LOAD off    0x0000000000000000 vaddr 0x0000000000000000 paddr 0x0000000000000000 align 2**14
LOAD off    0x0000000000058150 vaddr 0x000000000005c150 paddr 0x000000000005c150 align 2**14
LOAD off    0x000000000005c150 vaddr 0x0000000000064150 paddr 0x0000000000064150 align 2**14
```

最右侧写着 align 2**14，说明按 16KB 对齐。

