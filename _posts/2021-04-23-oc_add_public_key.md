---
layout: post
title: 오라클 클라우드 Public Key 추가
cover-img: /assets/img/oraclecloud/oracle-cloud.png
gh-badge: [star, fork, follow]
tags: [oracle cloud, VM instance, SSH, Public Key]
comments: true
---

# Instance에 Public Key 추가하기
- kibua20 님의 블로그에 의하면 그냥 일반 리눅스처럼 ssh key 를 직접 .ssh/authorized_keys 에 등록해야하는군요. 확실한 보안이긴 하지만 불편하겠네요. 다른 pc의 public key 를 해당 pc로 가져와서 등록해야하니...

# 레퍼런스
- [Add a New Public Key to an Oracle Cloud Instance](https://docs.oracle.com/en/cloud/paas/goldengate-cloud/add-public-key/)
- [Oracle Cloud SSH Key 여러 개 등록하기 (여러 PC에서 Cloud Access)](https://kibua20.tistory.com/125)
- [Support Multiple Key Pairs for Secure Shell (SSH) Access](https://docs.oracle.com/en/cloud/paas/big-data-cloud/csbdi/support-multiple-key-pairs-secure-shell-ssh-access.html)
