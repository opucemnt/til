# Python：读写文本文件

```python
# 写
with open("a.txt", "w", encoding="utf-8") as f:
    f.write("hello")

# 读全部
with open("a.txt", encoding="utf-8") as f:
    text = f.read()

# 逐行读（大文件别用 read()，内存会炸）
with open("a.txt", encoding="utf-8") as f:
    for line in f:
        print(line.rstrip())
```

- `with open(...)` 会自动关文件，别再手写 `f.close()`。
- `encoding="utf-8"` 显式写上，Windows 默认编码不是 UTF-8 会乱码。
- 逐行遍历文件对象是惰性的，几 GB 的日志也能一行一行处理。
