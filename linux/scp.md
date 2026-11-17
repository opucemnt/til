# Linux：scp 在两台机器间传文件

```bash
scp file.txt user@host:/tmp/          # 传文件到远端
scp user@host:/tmp/file.txt ./        # 从远端拿回来
scp -r dir/ user@host:/tmp/           # 传整个目录
scp -P 2222 file.txt user@host:/tmp/  # 远端 ssh 不是 22 端口
scp -i ~/.ssh/key.pem file.txt user@host:/tmp/  # 指定密钥
```

- `scp` 就是"ssh + cp"，认证方式和 ssh 一样。
- 传大文件用 `rsync -avz` 代替，断了能续传，scp 断了要重来。
- 目标路径的冒号别漏：`host:/tmp/` 有冒号才是远端，没冒号就是本地文件名。
