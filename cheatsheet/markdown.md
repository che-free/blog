---
title: "Markdown cheatsheet"
---

### 링크
```md
[Jekyll snippets]({{ "/jekyll/snippets/" | absolute_url }}){: target="_blank"}
[Google](https://google.com/ "google link")
[Google](https://google.com/ "google link"){: target="_blank"}
```

### 이미지
```md
![test image]({{ "/assets/img/image_800x250.png" | absolute_url }}){: .center}
![test image]({{ "/assets/img/image_800x250.png" | absolute_url }}){: width="100%" .center}
![test image]({{ "/assets/img/image_800x250.png" | absolute_url }}){: width="300px" height="200px"}
![test image]({{ "/assets/img/image_800x250.png" | absolute_url }} "설명"){: .center}
```

### 테이블
```md
| Tables        | Are           | Cool  |
| ------------- |:-------------:| -----:|
| col 3 is      | right-aligned | $1600 |
| col 2 is      | centered      |   $12 |
| zebra stripes | are neat      |    $1 |
```

### 헤더
```
# This is a H1
## This is a H2
### This is a H3
#### This is a H4
##### This is a H5
###### This is a H6
```

### 블럭인용
```md
> This is a first blockqute.
>   > This is a second blockqute.
>   >   > This is a third blockqute.
```

### 순서있는 목록
```md
1. 첫번째
    1. 1-1
    1. 1-2
1. 두번째
1. 세번째
```

### 순서없는 목록
```md
- 첫번째
    - 1-1
    - 1-2
- 두번째
- 세번째
```

### 수평선
```md
***
---
```

### 강조
```md
*single asterisks*
_single underscores_
**double asterisks**
__double underscores__
~~cancelline~~
```
- *single asterisks*
- _single underscores_
- **double asterisks**
- __double underscores__
- ~~cancelline~~


### 줄 바꿈
줄의 끝에 공백 3개 이상을 입력하고 다음 줄 입력하면 줄 바꿈이 적용된다.
```md
- 첫 번째 항목        
  첫 번째 항목의 두 번째 줄
- 두 번째 목록
```
- 첫 번째 항목        
  첫 번째 항목의 두 번째 줄
- 두 번째 목록

### Youtube
```md
[![alt text](http://img.youtube.com/vi/uaiGYmsX44Y/0.jpg)](http://www.youtube.com/watch?v=uaiGYmsX44Y)
<iframe width="560" height="315" src="https://www.youtube.com/embed/uaiGYmsX44Y" frameborder="0" allowfullscreen></iframe>
```

