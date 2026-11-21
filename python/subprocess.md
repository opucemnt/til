# Python：subprocess 跑外部命令

```python
import subprocess

r = subprocess.run(["ls", "-la"], capture_output=True, text=True)
print(r.returncode)
print(r.stdout)

# 出错就抛异常，别继续往下走
subprocess.run(["git", "status"], check=True)
```

- 参数用列表传，别拼字符串 + `shell=True`，有注入风险。
- `capture_output=True` 抓输出，`text=True` 直接给字符串而不是 bytes。
- `check=True` 让非零退出码抛 `CalledProcessError`，不用手动判断。
