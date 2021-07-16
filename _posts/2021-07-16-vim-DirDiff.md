---
layout: post
title: vim 플러그인 소개 - Vim-DirDiff
#subtitle: Each post also has a subtitle
#gh-repo: daattali/beautiful-jekyll
cover-img: /assets/img/vim/vim-27718_1280.png
gh-badge: [star, fork, follow]
tags: [vim, plugin, dirdiff]
comments: true
---


# [DirDiff](https://vimawesome.com/plugin/vim-dirdiff) 
- Vim plugin to diff two directories
- 두 디렉토리의 차이점을 쉽게 확인할 수 있는 플러그인입니다.

## 설치
- 지난 [YCM 설치 포스트](/2021-02-16-vim-ycm/)에서 vundle을 설치하셨다면 쉽게 설치됩니다.

```
File: ~/.vimrc

Plugin 'will133/vim-dirdiff'
```

Vim 재실행 후 다음 명령 실행

```
:source %
:PluginInstall
```

## 사용방법

```
:DirDiff <dir1> <dir2>
```

![DirDiff](/assets/img/vim/vim-dirdiff.png)

- vim에서 위의 명령을 수행하면dir1과 dir2를 비교해 다른 파일 리스트를 보여줍니다.
- 파일을 이동하면 해당 파일을 비교합니다.
- 자세한 사용 방법은 [DirDiff](https://vimawesome.com/plugin/vim-dirdiff)  참고 바랍니다.

