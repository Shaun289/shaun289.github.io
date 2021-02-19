---
layout: post
title: find로 찾은 파일들 복사하기
#subtitle: Each post also has a subtitle
#gh-repo: daattali/beautiful-jekyll
cover-img: /assets/img/shell/bash-148836_640.png
gh-badge: [star, fork, follow]
tags: [shell,bash]
comments: true
---

# find로 찾은 파일들 복사하기
- find로 찾은 파일들의 목록에 자동으로 명령을 내리는 방법입니다.

```sh
# cp 복사
find . -name *.ko -exec cp {} ../ \;
```

- 전 verbose 로그를 남길수 있는 install -v 를 애용합니다.

```sh
# install -v 복사
find . -name *.ko -exec install -vins {} ../ \;
`./Drivers/i2c.ko' -> `../i2c.ko'
```

- find의 -exec 는 find에서만 사용할 수 있기때문에 범용으로 사용할 수 있는 xargs 를 사용합니다. ls와 같이 -exec 가 없는 다른 명령어를 조합할 수 있는 강력한 방법입니다.

```sh
# xargs 와 install -v 복사
find . -name *.ko | xargs -i install -v {} ../
`./Drivers/i2c.ko' -> `../i2c.ko'
```
