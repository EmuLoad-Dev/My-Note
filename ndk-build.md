> Mac 下的 ndk-build 一般主目录位置。

```
/Users/[username]/Library/Android/sdk/ndk
```

---

> 检测 so 文件是否是 16KB 对齐的命令行。

```bash
$NDK_ROOT/toolchains/llvm/prebuilt/darwin-x86_64/bin/llvm-objdump -p libtest.so | grep LOAD
```

打印示例如下：

```plaintext
LOAD off    0x0000000000000000 vaddr 0x0000000000000000 paddr 0x0000000000000000 align 2**14
LOAD off    0x0000000000058150 vaddr 0x000000000005c150 paddr 0x000000000005c150 align 2**14
LOAD off    0x000000000005c150 vaddr 0x0000000000064150 paddr 0x0000000000064150 align 2**14
```

最右侧写着 align 2**14，那说明是按 16KB 对齐。

---
