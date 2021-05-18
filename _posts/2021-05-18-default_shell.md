---
layout: post
title: 우분투 기본 쉘을 dash에서 bash로 변경
#subtitle: Each post also has a subtitle
#gh-repo: daattali/beautiful-jekyll
cover-img: /assets/img/shell/bash-148836_640.png
gh-badge: [star, fork, follow]
tags: [ubuntu,shell,bash]
comments: true
---

# 문제
- SDK 빌드하다보면 간혹 이상한 에러가 발생하는 경우가 있습니다. 분명 bash 에서 정상동작하는 스크립트(echo -e 나 printf 같은)가 Makefile에서는 동작하지 않고 에러가 발생해서 골머리를 앓았습니다.
- 혹시나 하는 마음에 확인해보니..

```sh
$ ls -al /bin/sh
lrwxrwxrwx 1 root root 4 May 18 11:26 /bin/sh -> dash
```

- /bin/sh 가 bash가 아니라 dash였어????

# 해결
- 간단한 구글링 검색을 통해 해결책을 찾아내었습니다.
- [우분투 기본 쉘 dash 에서 bash로 변경하기](https://faq.hostway.co.kr/Linux_ETC/7267)
- 새로운 사실도 알게 되었네요. 우분투 기본 쉘이 dash랍니다. 엥????
- 아무튼 위의 링크에서 알려준 해결책을 적용합니다. 아래 명령을 수행하고 No 선택

```sh
sudo dpkg-reconfigure dash
```

![Ubuntu default shell](/assets/img/shell/ubuntu_default_shell.PNG)
