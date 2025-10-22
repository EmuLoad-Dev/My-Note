# 1. 检查 id_rsa.pub 文件在不在

一般路径
Windows: C:\Users\{UserName}/.ssh/id_ed25519.pub
Linux: ~/.ssh/id_rsa.pub

# 2. 生成 key

```bash
ssh-keygen -t ed25519 -C "xxx@xxx.com"
```

生成后可以通过打印日志看到密钥文件所在位置。

# 3. 到 github 处的 settings 配置密钥。

https://github.com/settings/profile

SSH and GPG keys 选项，New SSH key。

将 .ssh/id_ed25519.pub 文本内容拷贝到 Authentication keys 。

