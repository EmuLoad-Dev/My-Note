1. 检查 id_rsa.pub 文件在不在

一般路径
Windows: C:\Users\{UserName}/.ssh/id_ed25519.pub
Linux: ~/.ssh/id_rsa.pub

2. 生成key
```bash
ssh-keygen -t ed25519 -C "xxx@xxx.com"
```
