---
layout: post
title: 화씨와 섭씨를 상호 변환.rust
cover-img: /assets/img/rust/rust.png
gh-badge: [star, fork, follow]
tags: [rust]
comments: true
---


# [제어문](https://rinthel.github.io/rust-lang-book-ko/ch03-05-control-flow.html) 연습문제 풀이
- 일단 구글 검색을 통해 계산식을 알아냅니다.

```
# celsius -> fehrenheit
(0°C × 9/5) + 32 = 32°F

# fehrenheit
(0°F − 32) × 5/9 = -17.78°C
```

- 배운것을 통해 작성합니다. 아직 잘 모른다는 좋은 핑계가 있으니 코드가 부끄럽지 않습니다.

```rust
fn main() { 
    print_ctof(0.0);
    print_ctof(100.0);
    print_ftoc(0.0);
    print_ftoc(100.0);
}

fn print_ctof(celsius : f64) { 
    let fehrenheit = (celsius * 9.0/5.0) + 32.0;
    println!("{}°C = {}°F", celsius, fehrenheit);
}

fn print_ftoc(fehrenheit : f64) { 
    let celsius = (fehrenheit - 32.0) * 5.0/9.0;
 () println!("{}°F = {}°C", fehrenheit, celsius);
}

```

- 결과는 이렇습니다.

```
$ cargo run
   Compiling temperature v0.1.0 (/mnt/d/work/github/everything/rust/temperature)
    Finished dev [unoptimized + debuginfo] target(s) in 1.58s
     Running `target/debug/temperature`
0°C = 32°F
100°C = 212°F
0°F = -17.77777777777778°C
100°F = 37.77777777777778°C
```

- println 포맷으로 소수점 둘째자리까지 잘라내는 방법 좀 알아봐야겠네요.
- 만들어놓고 보니 제어문이며 리턴이며 다 안썼네요 이런.. 다음에 쓰죠 뭐

