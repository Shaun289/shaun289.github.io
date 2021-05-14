---
layout: post
title: String Length.rust
cover-img: /assets/img/rust/rust.png
gh-badge: [star, fork, follow]
tags: [rust]
comments: true
---


# [스트링](https://rinthel.github.io/rust-lang-book-ko/ch08-02-strings.html) 길이
- Rust는 String을 기본적으로 UTF-8을 사용합니다. UTF-8 에 대한 설명을 할 건 아니지만 UTF-8 문자의 크기는 가변임은 반드시 알아야합니다. 그렇기에 byte count 와 String character length 두가지를 구분해야합니다.


```rust
fn string_length(s: &String) -> usize {
    s.chars().count()
}

fn main() {
    println!("Hello, world!");
    let s = String::from("테스트");
    println!("{} utf-8 length : {} byte length : {} ", s, string_length(&s), s.len());
}


```

- 결과는 이렇습니다.

```
$ cargo run
   Compiling study v0.1.0 (/home/ubuntu/work/github/everything/rust/study)
    Finished dev [unoptimized + debuginfo] target(s) in 0.82s
     Running `target/debug/study`
Hello, world!
테스트 utf-8 length : 3 byte length : 9
```

## [String::len()](https://doc.rust-lang.org/std/string/struct.String.html#method.len)
- String이 Vec<u8> 을 Wrapping 했기때문에 byte length()를 의미합니다.


## [String::chars()](https://doc.rust-lang.org/std/string/struct.String.html#method.chars)
- String Slices의 Iterator 를 반환합니다. String Slice는 UTF-8로 구성되었기 때문에 count()의 값이 3이 됩니다.

# 후기
- 예제가 아닌 간단한 프로그램을 작성하는데 처음이라 그런지 저 짧은 프로그램 하나 짜는데 디버깅을 10분했네요. 그러면서 배우는거죠...고통스럽다...
