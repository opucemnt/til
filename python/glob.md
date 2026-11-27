# Python：glob 按模式找文件

```python
import glob

print(glob.glob("*.py"))            # 当前目录的 py 文件
print(glob.glob("src/**/*.py", recursive=True))  # 递归找
print(glob.glob("data/*.csv"))
```

- `*` 匹配一层，`**` 配 `recursive=True` 才递归。
- 返回的是路径字符串列表，顺序不保证，展示前先 `sorted()`。
- 只要文件名模式匹配用 glob；要按内容、时间筛，再配合 `os.path` 或 `pathlib`。
