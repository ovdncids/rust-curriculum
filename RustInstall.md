# Rust 설치
* https://rust-lang.org

## Mac (rustc@1.100.0)
```sh
# Xcode가 설치 되었는지 확인
xcode-select --install

# rustc, cargo, rustup 설치
curl --proto '=https' --tlsv1.2 -sSf https://sh.rustup.rs | sh
# 설치 완료 후 터미널 재시작 하면 $PATH에 ~/.cargo/bin 추가됨

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

# 해당 폴더만 버전 변경 (.python-version 같은 파일이 생성되지 않고 rustup이 해당 폴더 관리)
rustup override set 1.82.0
```
