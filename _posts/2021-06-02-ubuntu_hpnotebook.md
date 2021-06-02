---
layout: post
title: 오래된 듀얼 그래픽카드 노트북에 우분투 설치
#subtitle: Each post also has a subtitle
#gh-repo: daattali/beautiful-jekyll
cover-img: /assets/img/linux/ubuntu.png
gh-badge: [star, fork, follow]
tags: [ubuntu,linux,install]
comments: true
---

# HP Pavilion dv6
대략 12~13년 정도 된 노트북인데 윈도7만 깔수 있는 독특한 노트북입니다.  이유는 그래픽카드가 두개가 달려있고 윈도7 드라이버만 있기 때문입니다.  Radeon HD6750인가?하고 내장 그래픽하구요.  

이 노트북으로 신나게 롤..을 했었죠.

시간이 흘러 SSD까지 달아줘서 훌륭한 인터넷+줌 머신이 되어줬지만, 윈도7 지원이 끝나면서 새로운 노트북으로 대체되어 구석에 쳐박혔습니다.

# 설치실패
사실 당시에도 우분투를 깔아보려 했지만 실패했었죠.  구글링해보면 hp dv6 듀얼 그래픽카드 시리즈는 우분투를 잘 지원한다고 되어있었지만, 실제로 부팅usb를 꼽아보면 설치 UI 뜨고 10초후에 멈춰서 진행할 수 없었습니다.  대략 Dual 그래픽카드 문제일거라는 예상은 했지만 귀차니즘에 냅뒀었죠.

# 재시도
그러다 요즘 뭐 하려고 봤더니 PC며 노트북이며 애들이 다 붙잡고 있어서 이녀석을 꺼내게 되었습니다.  그리고 대망의 삽질끝에 성공한 후기를 남깁니다.

1. safe graphic 모드로 들어가서 우분투 설치
2. safe graphic 모드로 들어가서 부팅
3. 다음과 같이 수정

```sh
$ sudo vi /etc/default/grub

" ... quiet splash modprobe radeon.modeset=0"

$ sudo update-grub 
$ sudo reboot
```

짜잔! 부팅 완료!

대부분의 문서에는 modeset을 1로 하라고 합니다.  성능좋은 radeon 그래픽카드 모드로 쓰기 위해서죠.  하지만 제 노트북은 radeon 그래픽카드가 고장난 듯 합니다.  그래서 modeset을 0으로 바꾼 후 정상동작하게 되었네요.


#노인학대




