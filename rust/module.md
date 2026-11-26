# Rust：模块系统，pub 是关键

```rust
// lib.rs
pub mod utils {
    pub fn hello() {
        println!("hi");
    }

    fn secret() {} // 没 pub，外面看不到
}

// main.rs
use mycrate::utils::hello;

fn main() {
    hello();
}
```

- 模块默认私有，`pub` 才对外可见，函数、struct、字段都要单独 pub。
- `mod` 声明模块，`use` 引入路径，`crate` 指当前 crate 根。
- 文件和模块的对应：`utils.rs` 或 `utils/mod.rs` 都行，别自己发明路径。
- 2018 版之后 `use` 从 crate 根算起，`crate::` 前缀是显式写法。
