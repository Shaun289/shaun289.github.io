---
layout: post
title: Makefile 기본 shell 설정 에러
#subtitle: Each post also has a subtitle
#gh-repo: daattali/beautiful-jekyll
cover-img: /assets/img/shell/bash-148836_640.png
gh-badge: [star, fork, follow]
tags: [shell,bash,Makefile]
comments: true
---

# Makefile 에러

```
/bin/sh: 1: Syntax error: word unexpected (expecting ")")
```

- 위와 같은 에러나 echo -e 관련된 에러가 발생했을때 대처법입니다.
- 일단 man echo를 보면 다음과 같이 정의되어있습니다.

```
-e     enable interpretation of backslash escapes
```

- echo 안에 backslash가 들어있고 그걸 처리하도록 -e 옵션이 잘 들어가있는데 에러가 발생해서 난감했습니다.
- bash에 -e옵션이 잘 되어있다면 Makefile 기본 shell이 sh로 동작하는거라 예상하고 검색해보니..

# 해결책
- [stackoverflow](https://stackoverflow.com/questions/589276/how-can-i-use-bash-syntax-in-makefile-targets) 형님들 감사합니다!
- Makefile 최상단에 다음 라인을 넣으면 해결됩니다.

```
SHELL := /bin/bash
```

