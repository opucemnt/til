# Rust：Vec 最常用的方法

```rust
fn main() {
    let mut v = vec![1, 2, 3];
    v.push(4);
    v.pop(); // 返回 Option<i32>

    // 遍历（借用）
    for x in &v {
        println!("{}", x);
    }

    // 常用操作
    println!("{:?}", v.iter().map(|x| x * 2).collect::<Vec<_>>());
    println!("{}", v.contains(&2)); // true
    println!("{}", v.len());

    // 排序（就地）
    let mut nums = vec![3, 1, 2];
    nums.sort();
    println!("{:?}", nums); // [1, 2, 3]
}
```

- `vec![]` 是宏，`Vec::new()` 是空 Vec，`Vec::with_capacity(n)` 预分配。
- `push` 可能扩容，事先知道大小就用 `with_capacity`。
- `iter()` 借用，`into_iter()` 拿走所有权，`iter_mut()` 可变借用。
