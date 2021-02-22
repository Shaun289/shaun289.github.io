---
layout: post
title: WSL2 네트워크를 브리지 모드로 연결하기
#subtitle: Each post also has a subtitle
#gh-repo: daattali/beautiful-jekyll
cover-img: /assets/img/wsl/network-3357642_1920.jpg
gh-badge: [star, fork, follow]
tags: [wsl,network,brigde,hyperv]
comments: true
---

# 개요
- WSL2의 출시와 함께 설치후 가장 크게 실망한 부분은 네트워크입니다.
- Bridge 모드로 동작하지 않고 내부네트워크로 동작하여 외부와 NAT로 동작한다면 개발을 하며 사용하는 여러 서버에 제약이 생기게 됩니다.
- 하지만 WSL2가 Hyper-v 기반이라는 이야기를 접하고 Bridge 모드로 사용이 불가능할리 없다는 판단에 수많은 시도끝에 방법을 찾아냈습니다.
- 이상하긴 합니다.
- 매번 부팅시 수행해야 해서 번거로워 찾아보니 스크립트가 있었습니다만, Windows 스크립트는 돌릴 줄 몰라서 포기했습니다. 많이 하다보니 익숙해져서 그렇게 번거롭지 않습니다.

## WSL2 Bridge 설정
- 부팅후 일단 WSL2 Ubuntu 를 한번 열었다 닫음
- winkey-s - hyper-v 관리자 실행
- 제어판 - 네트워크 및 인터넷 - 어댑터 옵션 변경 실행

![Network and Hyper-v](/assets/img/wsl/wsl_bridge_3.PNG)

- vEthernet (WSL) 이 보이지 않을 경우 WSL2 우분투를 실행후 닫습니다.
- 이더넷 속성에서 "Hyper-V 확장 가능 가상 스위치" 체크 해제

![Ethernet property](/assets/img/wsl/wsl_bridge_4.PNG)

- Hyper-v 관리자 우측 중단의 "가상스위치관리자"

![가상스위치관리자](/assets/img/wsl/wsl_bridge_8.PNG)

- WSL - "외부 네트워크 설정" 후 확인. 에러메시지 발생

![외부 네트워크 설정](/assets/img/wsl/wsl_bridge_5.PNG)

- 실패 후 다시 "외부 네트워크 설정" 후 확인. 에러메시지 발생 안함
- 다음과 같이 설정되었음을 확인

![설정 결과](/assets/img/wsl/wsl_bridge_9.PNG)

## WSL2 외부 네트워크 설정
- WSL2 가 가상컴퓨터이다보니 네트워크 설정을 매번 해줘야하는 번거러움이 있습니다.
- 전 다음과 같이 스크립트를 작성하여 sudo 권한으로 실행합니다.

```
ifconfig eth0 192.168.1.202 netmask 255.255.0.0
route add default gw 192.168.1.1 dev eth0
service rpcbind restart
service nfs-kernel-server restart
service ssh restart
service xinetd restart
service tftpd-hpa restart
echo "nameserver 8.8.8.8" >> /etc/resolv.conf
```

- 스크립트 실행 결과

![스크립트 결과](/assets/img/wsl/wsl_bridge_7.PNG)

