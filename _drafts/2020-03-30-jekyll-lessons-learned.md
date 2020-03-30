---
title:  "Jekyll lessons learned"
#toc: true
---

Jekyll을 사용해보고 알게된 내용들 정리.


## Jekyll
정적 사이트 생성기. [GitHub Pages](https://pages.github.com/)는 Jekyll을 이용해서 동작한다.

## TOC(Table of content) 사용 방법

### 1. Jekyll kramdown 기본 기능 이용
```
* TOC
{:toc}
```
Posts MD 파일에서 사용하거나 Posts MD 파일에서 Include하는 파일에서는 사용할 수 있는데
레이아웃 파일, 레이아웃에서 Include하는 파일에서는 사용할 수 없다.

### 2. jekyll-toc 플러그인 사용
```liquid
{.% toc %}
```
레이아웃 파일에서도 TOC를 사용할 수 있다.<br>
하지만 GitHub Pages에서는 [화이트리스트의 플러그인](https://pages.github.com/versions)만 작동하므로 GitHub Pages를 이용하는 경우에는 jekyll-toc 플러그인을 사용할 수 없다.

> https://github.com/toshimaru/jekyll-toc

### 3. Jekyll Pure Liquid
```
{.% include toc.html html=content %}
```
레이아웃 파일에서도 TOC를 사용할 수 있다.

> https://github.com/allejo/jekyll-toc


