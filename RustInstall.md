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

```sh
# Rust 프로젝트 만들기
cargo new rust-study
cd rust-study
cargo run
```

* rust-toolchain.toml (버전 고정)
```toml
[toolchain]
channel = "1.100.0"
```

* Cargo.toml (최소 버전 지정)
```toml
[package]
rust-version = "1.82"
```

* VSCode + rust-analyzer

### rustfmt@1.11.0
* https://github.com/rust-lang/rustfmt
* https://rust-lang.github.io/rustfmt/?version=v1.10.0&search=
```sh
# rustup에 기본 내장
rustfmt --version

# 최신 버전 확인
rustup component add rustfmt

# fmt 체크
cargo fmt --check

# fmt 수정
cargo fmt
```

* rustfmt.toml
```toml
# Cargo.toml의 edition
edition = "2024"

# 기본 들여쓰기와 줄 길이
tab_spaces = 4
max_width = 100

# import 정렬
reorder_imports = true
```

* .vscode/settings.json (저장과 동시에 fmt 적용)
```json
{
  "[rust]": {
    "editor.defaultFormatter": "rust-lang.rust-analyzer",
    "editor.formatOnSave": true
  }
}
```
