# Linux：wc 统计行数

```bash
wc -l file.txt      # 行数
wc -w file.txt      # 词数
wc -c file.txt      # 字节数
cat *.log | wc -l   # 统计多个文件的总行数
```

- `wc -l` 统计换行符个数，最后一行没换行符会少算一行。
- `wc` 不给参数时同时输出行数、词数、字节数。
- `grep -c` 也能计数，但 `wc -l` 更通用，管道过来什么都能数。
