> zip加密压缩文件
```bash
zip -e archive.zip file.txt
```
-e 加密压缩

> 获取文件的 SHA256 校验值

```bash
shasum -a 256 "README.md"
```

> 配置环境变量

```bash
vim ~/.zshrc
```

接下来仅举例

```zshrc
export PATH="/opt/homebrew/opt/icu4c/sbin:$PATH"
```
