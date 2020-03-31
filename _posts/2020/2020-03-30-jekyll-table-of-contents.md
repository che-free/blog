---
title:  "Jekyll에서 TOC(Table of contents) 사용하는 방법"
tags: Jekyll
---

Jekyll에서 TOC(Table of contents) 사용하는 방법.

### 방법1) Jekyll kramdown 기본 기능 이용
```liquid
* TOC
{:toc}
```
Posts 파일에서 사용하거나 Posts 파일에서 Include하는 파일에서는 사용할 수 있는데 **레이아웃 파일, 레이아웃에서 Include하는 파일에서는 사용할 수 없다.**

### 방법2) jekyll-toc 플러그인 사용
```liquid
{% raw %}{% toc %}{% endraw %}
```
레이아웃 파일에서도 TOC를 사용할 수 있다.<br>
하지만 GitHub Pages에서는 [화이트리스트의 플러그인](https://pages.github.com/versions)만 작동하므로 **GitHub Pages를 이용하는 경우에는 jekyll-toc 플러그인을 사용할 수 없다.**

> https://github.com/toshimaru/jekyll-toc

### 방법3) Jekyll Pure Liquid
```liquid
{% raw %}{% include toc.html html=content %}{% endraw %}
```
레이아웃 파일에서도 TOC를 사용할 수 있다.

> https://github.com/allejo/jekyll-toc
