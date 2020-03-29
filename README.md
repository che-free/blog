## GitHub Pages를 이용한 블로그
- GitHub Pages
- Jekyll

## 윈도우에서 Jekyll 테마 실행 준비
1. Ruby, Jekyll 설치 - [윈도우에서 Jekyll 설치](https://blog.enjoydev.com/2019/jekyll-on-windows/)
2. Git clone
3. bundle install 실행
3. run.cmd 실행
4. 접속 확인
	> [http://127.0.0.1:4000/](http://127.0.0.1:4000/)

## 블로그 글 작성
작성일자(YYYY-MM-DD)를 포함해서 영문명으로 만든다.
- 공백은 하이픈(-)으로 대신 입력한다.
- 한글명으로 만들면 빌드는 되지만 페이지가 열리지 않는다.
- 한글 내용을 포함하는 경우 UTF-8(BOM 없음) 형식으로 변환해서 저장 한다.
> Ex) 2019-12-31-welcome-to-jekyll.md

## 블로그 글 작성 템플릿
```yml
---
title: "글 제목"
excerpt: "글 요약 내용"
categories:
- Jekyll
tags:
- Jekyll
---

내용 시작...
```
