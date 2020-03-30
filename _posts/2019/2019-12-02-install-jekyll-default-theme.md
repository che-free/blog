---
title:  "Jekyll 기본 테마 설치 및 윈도우 Jekyll 참고 사항"
excerpt: "Jekyll 기본 테마 설치 방법 및 윈도우에서 Jekyll 실행시 참고 사항"
categories:
  - Jekyll
tags:
  - Jekyll
---

## Jekyll 기본 테마 설치
1. 아래 명령으로 [Jekyll 기본 테마](https://github.com/jekyll/minima)를 생성한다.
	```
	jekyll new jekyll-theme
	```
	**jekyll-theme** 이름의 폴더가 만들어지고 **_config.yml**, **Gemfile** 등 기본적인 파일들이 만들어진다.
3. Jekyll 서버를 시작한다.
	```
	cd jekyll-theme
	jekyll serve
	```
4. [http://127.0.0.1:4000/](http://127.0.0.1:4000/) 접속해서 확인한다.

## 윈도우에서 Jekyll 실행시 참고 사항
- UTF-8 환경인 경우 코드 페이지 변경이 필요하다.
	```
	chcp 6501
	```
	>   Conversion error: Jekyll::Converters::Scss encountered an error while converting 'assets/css/main.scss':
                    Invalid CP949 character "\xE2" on line 54
- UTF-8 환경인 경우 *.md, *.html 등 **UTF-8(BOM 없음)**으로 저장해야 한다.
	>  Error: could not read file C:/workspace/jekyll/_drafts/wellcome-to-jeykyll.md: invalid byte sequence in UTF-8
- 소스 디렉토리에 아래 내용으로 run.cmd 파일 만들어두면 쉽게 실행 할 수 있다.
	```
	@ECHO OFF
	rem 코드 페이지 변경 (UTF-8)
	chcp 65001
	rem 기본 실행
	rem bundle exec jekyll serve
	rem 초안 표시
	bundle exec jekyll serve --draft
	```
