# Minirs
### Rust minimal bin size boilerplate
---

The goal of this boilerplate is to make a lightweight binary file without making your project look like a fucking mess.
Current release size is: `30872 bytes`


### Setup
1) [Install Rust](https://rustup.rs)
2) Install rake
3) Clone repo 
`git clone https://github.com/axvm/minirs`
4) Call setup rake task 
`rake setup`
5) ...
6) Profit!

### Usage
In development you can use `cargo build` and `cargo run` but to build release binary files you need to specify target platform in `Rakefile` before compilation.

##### How to get your target platform
Call `rustc -vV`, your platform next to `Host` label. 
Example:
```bash
$> rustc -vV
rustc 1.43.0-nightly (58b834344 2020-02-05) 
binary: rustc
commit-hash: 58b834344fc7b9185e7a50db1ff24e5eb07dae5e
commit-date: 2020-02-05
host: x86_64-unknown-linux-gnu
release: 1.43.0-nightly
LLVM version: 9.0
```
Place your platform value to `TARGET` variable in `Rakefile`

##### How to rename binary file
To change name of your binary you need to update Rakefile and Cargo.toml
Rakefile:
```ruby
TARGET='....'
BIN='my-awesome-custom-name'
...
```
Cargo.toml:
```toml
[package]
name = "my-awesome-custom-name"
...
```
