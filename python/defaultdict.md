# Python：defaultdict 省掉判空

```python
from collections import defaultdict

count = defaultdict(int)
for w in ["a", "b", "a"]:
    count[w] += 1
print(dict(count))  # {'a': 2, 'b': 1}

groups = defaultdict(list)
groups["x"].append(1)
print(dict(groups))  # {'x': [1]}
```

- `defaultdict(int)` 缺 key 时自动补 0；`defaultdict(list)` 自动补 `[]`。
- 普通 dict 写 `d[k] += 1` 会 KeyError，得先 `d[k] = d.get(k, 0) + 1`。
- 只是读数据时别用 defaultdict，误触不存在的 key 会悄悄把它建出来。
