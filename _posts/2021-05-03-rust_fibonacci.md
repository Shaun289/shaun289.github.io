---
layout: post
title: 피보나치 수열.rust
cover-img: /assets/img/rust/rust.png
gh-badge: [star, fork, follow]
tags: [rust]
comments: true
---


# [제어문](https://rinthel.github.io/rust-lang-book-ko/ch03-05-control-flow.html) 연습문제 풀이
- 피보나치 수열은 지겹게 풀어봤던거라 그냥 바로 풀이 들어갑니다


```rust
fn fibonacci(n: u32) -> u32 { 
    let mut n1 = 0;
    let mut n2 = 1;
    let mut result = 0;

    if n == 1 { 
        result = n1;
    } 
    else if n == 2 { 
        result = n2;
    } 
    else { 
        for _i in 3..(n+1) {
            result = n1 + n2;
            n1 = n2;
            n2 = result;
            //println!("n1:{} n2:{} result{}", n1, n2, result);
        } 
    } 

    result
}

fn main() { 
    for i in 1..11 {
        println!("{}'s finacci is {}", i, fibonacci(i));
    } 
}

```

- 결과는 이렇습니다.

```
$ cargo run 
   Compiling fibonacci v0.1.0 (/mnt/d/work/github/everything/rust/fibonacci)
    Finished dev [unoptimized + debuginfo] target(s) in 1.76s
     Running `target/debug/fibonacci`
1's finacci is 0
2's finacci is 1
3's finacci is 1
4's finacci is 2
5's finacci is 3
6's finacci is 5
7's finacci is 8
8's finacci is 13
9's finacci is 21
10's finacci is 34
```

- 며칠만에 rust 만졌다고 기본 문법이 기억안나서 혼났습니다.
- for 문에 안쓰이는 i를 만들면 이런 워닝이 뜨는군요. _i로 바꿨습니다.

```
help: if this is intentional, prefix it with an underscore: `_i`
```

- u32 overflow는 무시하기로 합니다.
