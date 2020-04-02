---
title:  "윈도우에서 Jekyll 설치"
excerpt: "윈도우에서 Jekyll 실행 위한 Ruby, Jekyll 설치 방법"
categories:
  - Jekyll
tags:
  - Jekyll
toc: true
---

## Ruby, Jekyll 설치
1. [RubyInstaller Downloads](https://rubyinstaller.org/downloads/)에서 **Ruby+Devkit** 버전을 다운로드 받고 설치한다.<br/>
   기본 옵션으로 설치를 진행한다.
2. 설치 마지막 단계에서 **"ridk install"**을 선택하고 진행한다.
3. **"ridk install"** 설치 화면에서 **"1 - MSYS2 base installation"**을 선택하고 진행한다.
4. 설치 완료 후 **도스창(cmd.exe)**을 열고 Jekyll, Bundler를 설치한다.
```
gem install jekyll bundler
```
5. Jekyll 설치 버전을 확인한다.
```
jekyll -v
```
> 2019/12 현재 설치된 버전
> -  Ruby+Devkit 2.6.5-1
> -  Jekyll 4.0.0

<!--
### ridk install 설치 화면
```
 _____       _           _____           _        _ _         ___
|  __ \     | |         |_   _|         | |      | | |       |__ \
| |__) |   _| |__  _   _  | |  _ __  ___| |_ __ _| | | ___ _ __ ) |
|  _  / | | | '_ \| | | | | | | '_ \/ __| __/ _` | | |/ _ \ '__/ /
| | \ \ |_| | |_) | |_| |_| |_| | | \__ \ || (_| | | |  __/ | / /_
|_|  \_\__,_|_.__/ \__, |_____|_| |_|___/\__\__,_|_|_|\___|_||____|
                    __/ |           _
                   |___/          _|_ _  __   | | o __  _| _     _
                                   | (_) |    |^| | | |(_|(_)\^/_>

   1 - MSYS2 base installation
   2 - MSYS2 system update (optional)
   3 - MSYS2 and MINGW development toolchain

Which components shall be installed? If unsure press ENTER [1,2,3] 1

> sh -lc true
'C:\WINDOWS\system32\drivers\etc\hosts' -> '/etc/hosts'
'C:\WINDOWS\system32\drivers\etc\protocol' -> '/etc/protocols'
'C:\WINDOWS\system32\drivers\etc\services' -> '/etc/services'
'C:\WINDOWS\system32\drivers\etc\networks' -> '/etc/networks'
gpg: /etc/pacman.d/gnupg/trustdb.gpg: trustdb created
...
```
-->

## RubyInstaller 설치 화면
![Ruby installer]({{ "/assets/posts/jekyll-on-window/ruby-install-01.png" | absolute_url }}){: .center}

![Ruby installer]({{ "/assets/posts/jekyll-on-window/ruby-install-02.png" | absolute_url }}){: .center}

![Ruby installer]({{ "/assets/posts/jekyll-on-window/ruby-install-03.png" | absolute_url }}){: .center}

![Ruby installer]({{ "/assets/posts/jekyll-on-window/ruby-install-04.png" | absolute_url }}){: .center}

![Ruby installer]({{ "/assets/posts/jekyll-on-window/ruby-install-05.png" | absolute_url }}){: .center}

![Ruby installer]({{ "/assets/posts/jekyll-on-window/ruby-install-06.png" | absolute_url }}){: .center}

![Ruby installer]({{ "/assets/posts/jekyll-on-window/ruby-install-07.png" | absolute_url }}){: .center}

![Ruby installer]({{ "/assets/posts/jekyll-on-window/ruby-install-08.png" | absolute_url }}){: .center}

### 관련 사이트
- [Jekyll on Windows](https://jekyllrb.com/docs/installation/windows/)
- [윈도우즈에서의 Jekyll](https://jekyllrb-ko.github.io/docs/windows/)
- [RubyInstaller](https://rubyinstaller.org/)
- [RubyInstaller download](https://rubyinstaller.org/downloads/)
