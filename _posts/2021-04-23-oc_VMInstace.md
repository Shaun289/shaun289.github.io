---
layout: post
title: 오라클 클라우드 VM Instance 생성
cover-img: /assets/img/oraclecloud/oracle-cloud.png
gh-badge: [star, fork, follow]
tags: [oracle cloud, VM instance]
comments: true
---

# 오라클 클라우드 VM Instance 생성
- 기본적으로 wsgvet 의 내용을 참조합니다.
- Ubuntu 20.04 선택
- Add SSH keys
  - Paste public keys 선택
  - WSL 에서 다음의 명령으로 쉴행후 ssh-rsa 로 시작하는 전체를 복사하여 SSH keys에 붙여넣기

``` bash
$ ssh-keygen # 모두 엔터키
$ cat ~/.ssh/id_rsa.pub
```

- WSL에서 접속
  - 생성후 Public IP Address 로 접속. 아이디는 ubuntu

``` bash
$ ssh ubuntu@132.226.???.???
```


# 레퍼런스
- [wsgvet 오라클 클라우드 인스턴스 생성 및 SSH 접속하기](https://www.wsgvet.com/cloud/5)
