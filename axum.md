# axum@0.8.9
* https://docs.rs/axum/latest/axum

## 설치
```sh
# 프로젝트 생성
cargo new rust-axum-study
cd rust-axum-study

# axum 서버 설치
cargo add axum

# tokio 비동기 라이브러기 설치
cargo add tokio --features full
```

* src/main.rs
```rs
use axum::{Router, routing::get};

#[tokio::main]
async fn main() {
    let app = Router::new().route("/", get(|| async { "Hello, Axum!" }));

    let listener = tokio::net::TcpListener::bind("0.0.0.0:3000").await.unwrap();

    println!("Server running on http://localhost:3000");

    axum::serve(listener, app).await.unwrap();
}
```

```sh
# axum 서버 실행
cargo run
```
