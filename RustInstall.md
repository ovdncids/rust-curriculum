# Rust 설치
* https://rust-lang.org

## Mac (rustc@1.100.0)
```sh
# Xcode가 설치 되었는지 확인
xcode-select --install

# rustc, cargo, rustup 설치
# $PATH에 ~/.cargo/bin 추가됨
curl --proto '=https' --tlsv1.2 -sSf https://sh.rustup.rs | sh

# rustc@1.100.0
rustc --version
# cargo@1.100.0
cargo --version
# rustup@1.29.3 (rustup default로 버전이 변경해도 rustup 버전은 고정)
rustup --version

# 다른 버전 설치
rustup toolchain install 1.82.0

# 설치된 버전들 확인
rustup toolchain list

# 버전 변경
rustup default 1.82.0
```
