---
title: "Markdown for Jekyll"
---

Jekyll 글 작성에서 Markdown 문법 정리.


### 링크
```
{% raw %}[Posts]({{ "/posts/" | relative_url }} "Posts")
[Posts]({{ "/posts/" | absolute_url }} "Posts")
See the section on [`code`](#code)
[Google](https://google.com/ "google link")
[Google](https://google.com/ "google link"){: target="_blank"}{% endraw %}
```
- [Posts]({{ "/posts/" | relative_url }} "Posts")
- [Posts]({{ "/posts/" | absolute_url }} "Posts")
- See the section on [code](#code)
- [Google](https://google.com/ "google link")
- [Google](https://google.com/ "google link"){: target="_blank"}



### 이미지
```
{% raw %}![alt text]({{ "/assets/img/image_800x250.png" | absolute_url }}){: .center}
![alt text]({{ "/assets/img/image_800x250.png" | absolute_url }}){: width="100%" .center}
![alt text]({{ "/assets/img/image_800x250.png" | absolute_url }}){: width="300px" height="200px"}
![alt text]({{ "/assets/img/image_800x250.png" | absolute_url }} "설명"){: .center}{% endraw %}
```
![alt text]({{ "/assets/img/image_800x250.png" | absolute_url }}){: .center}
![alt text]({{ "/assets/img/image_800x250.png" | absolute_url }}){: width="100%" .center}
![alt text]({{ "/assets/img/image_800x250.png" | absolute_url }}){: width="300px" height="200px"}
![alt text]({{ "/assets/img/image_800x250.png" | absolute_url }} "설명"){: .center}


### 테이블
{% capture code %}
| Tables        | Are           | Cool  |
| ------------- |:-------------:| -----:|
| col 3 is      | right-aligned | $1600 |
| col 2 is      | centered      |   $12 |
| zebra stripes | are neat      |    $1 |
{% endcapture %}
```
{{- code -}}
```
{{ code }}


### 소스 코드
일반 텍스트
{% capture code %}{% raw %}```
C:\>dir/w
```{% endraw %}{% endcapture %}
<div class="highlighter-rouge"><div class="highlight"><pre class="highlight"><code>{{- code -}}</code></pre></div></div>

Liquid
<div class="highlighter-rouge"><div class="highlight"><pre class="highlight"><code>```
{&permil; raw &permil;}{% raw %}
![alt text]({{ "/assets/img/image_800x250.png" | absolute_url }})
{% endraw %}{&permil; endraw &permil;}
```</code></pre></div></div>

Markdown
{% capture code %}{% raw %}```
## This is H1
```{% endraw %}{% endcapture %}
<div class="highlighter-rouge"><div class="highlight"><pre class="highlight"><code>{{- code -}}</code></pre></div></div>

> **Language 참고**   
> <https://github.com/rouge-ruby/rouge/wiki/List-of-supported-languages-and-lexers>


### 코드
{% capture code %}
- At the command prompt, type `nano`.
- ``Use `code` in your Markdown file.``
{% endcapture %}
```
{{- code -}}
```
{{ code }}






### 강조
{% capture code %}
- *single asterisks*
- _single underscores_
- **double asterisks**
- __double underscores__
- ~~cancelline~~
{% endcapture %}
```
{{- code -}}
```
{{ code }}


### 헤더
{% capture code %}
# This is a H1
## This is a H2
### This is a H3
#### This is a H4
##### This is a H5
###### This is a H6
{% endcapture %}
```
{{- code -}}
```
{{ code }}


### 블럭인용
{% capture code %}
> This is a first blockqute.
>   > This is a second blockqute.
>   >   > This is a third blockqute.
{% endcapture %}
```
{{- code -}}
```
{{ code }}



### 순서있는 목록
{% capture code %}
1. 첫번째
    1. 1-1
    1. 1-2
1. 두번째
1. 세번째
{% endcapture %}
```
{{- code -}}
```
{{ code }}


### 순서없는 목록
{% capture code %}
- 첫번째
    - 1-1
    - 1-2
- 두번째
- 세번째
{% endcapture %}
```
{{- code -}}
```
{{ code }}


### 수평선
{% capture code %}
***
---
{% endcapture %}
```
{{- code -}}
```
{{ code }}


### 줄 바꿈
줄의 끝에 공백 3개 이상을 입력하고 다음 줄 입력하면 줄 바꿈이 적용된다.
{% capture code %}
- 첫 번째 항목   
  첫 번째 항목의 두 번째 줄
- 두 번째 목록
{% endcapture %}
```
{{- code -}}
```
{{ code }}


### Youtube
{% capture code %}
[![alt text](http://img.youtube.com/vi/9bZkp7q19f0/0.jpg)](http://www.youtube.com/watch?v=9bZkp7q19f0)
[![alt text](http://img.youtube.com/vi/9bZkp7q19f0/0.jpg)](http://www.youtube.com/watch?v=9bZkp7q19f0){: target="_blank"}
<iframe width="560" height="315" src="https://www.youtube.com/embed/9bZkp7q19f0" frameborder="0" allowfullscreen></iframe>
{% endcapture %}
```
{{- code -}}
```
{{ code }}



## 참고 사이트
- [마크다운 - 나무위키](https://namu.wiki/w/%EB%A7%88%ED%81%AC%EB%8B%A4%EC%9A%B4){: target="_blank"}
- [Quick Reference - kramdown](https://kramdown.gettalong.org/quickref.html){: target="_blank"}
- [Basic Syntax - Markdown Guide](https://www.markdownguide.org/basic-syntax/){: target="_blank"}


