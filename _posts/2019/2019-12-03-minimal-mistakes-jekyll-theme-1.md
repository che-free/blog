---
title: "Minimal Mistakes Jekyll 테마 - 1)준비"
excerpt: "윈도우에서 Minimal Mistakes Jekyll 테마를 실행하고 테스트하기 위한 설명 글"
categories:
  - Jekyll
tags:
  - Jekyll
---

> 윈도우에서 Minimal Mistakes Jekyll 테마를 실행하고 테스트하기 위한 설명 글.

## 준비

1. **Ruby, Jekyll 설치**<br/>
	Jekyll 테마 실행을 위해 Ruby, Jekyll을 설치한다.
	> 참고 : [윈도우에서 Jekyll 설치](/2019/jekyll-on-windows/)
2. **테마 소스 다운로드**<br/>
	[Minimal Mistakes](https://github.com/mmistakes/minimal-mistakes/releases)에서 소스 ZIP 다운로드 받고 압축 춘다.
3. **Gemfile 수정**
	```ruby
	source "https://rubygems.org"

	gem "jekyll", "~> 4.0"
	gem "jekyll-paginate"
	gem "jekyll-sitemap"
	gem "jekyll-gist"
	gem "jekyll-feed"
	gem "jekyll-include-cache"
	gem "wdm", ">= 0.1.0" if Gem.win_platform?
	```
4. **bundle 실행**<br/>
	소스 디렉토리에서 bundle 명령을 실행한다.
	```
    C:\Workspace\jekyll_blog>bundle
    Using public_suffix 4.0.1
    Using addressable 2.7.0
    Using bundler 2.0.2
    Using colorator 1.1.0
    Using concurrent-ruby 1.1.5
    Using eventmachine 1.2.7 (x64-mingw32)
    Using http_parser.rb 0.6.0
    Using em-websocket 0.5.1
    Using multipart-post 2.1.1
    Using faraday 0.17.1
    Using ffi 1.11.3 (x64-mingw32)
    Using forwardable-extended 2.6.0
    Using i18n 1.7.0
    Using sassc 2.2.1 (x64-mingw32)
    Using jekyll-sass-converter 2.0.1
    Using rb-fsevent 0.10.3
    Using rb-inotify 0.10.0
    Using listen 3.2.1
    Using jekyll-watch 2.2.1
    Using kramdown 2.1.0
    Using kramdown-parser-gfm 1.1.0
    Using liquid 4.0.3
    Using mercenary 0.3.6
    Using pathutil 0.16.2
    Using rouge 3.14.0
    Using safe_yaml 1.0.5
    Using unicode-display_width 1.6.0
    Using terminal-table 1.8.0
    Using jekyll 4.0.0
    Using jekyll-feed 0.13.0
    Using sawyer 0.8.2
    Using octokit 4.14.0
    Using jekyll-gist 1.5.0
    Using jekyll-include-cache 0.2.0
    Using jekyll-paginate 1.1.0
    Using jekyll-sitemap 1.4.0
    Using wdm 0.1.1
    Bundle complete! 7 Gemfile dependencies, 37 gems now installed.
    Use `bundle info [gemname]` to see where a bundled gem is installed.
	```
5. **Jekyll 테마 실행**
	```
	chcp 65001
	bundle exec jekyll serve
	```
6. **접속 확인**<br/>
	[http://127.0.0.1:4000/](http://127.0.0.1:4000/) 접속해서 확인한다.
7. **Jekyll 테마 실행 위한 cmd 파일 생성**<br/>
	소스 디렉토리에 아래 내용으로 **run.cmd** 파일 만들어두면 쉽게 실행 할 수 있다.
	```
	@ECHO OFF
	rem 코드 페이지 변경 (UTF-8)
	chcp 65001
	rem 기본 실행
	rem bundle exec jekyll serve
	rem 초안 표시
	bundle exec jekyll serve --draft
	```

## 불필요한 폴더, 파일 삭제
아래 내용을 참고해서 불필요한 폴더, 파일들을 삭제한다.
- /docs 폴더에는 Minimal Mistakes 사이트의 Quick Start Guide, Sample Posts 등이 들어있다. 참고용으로 두던가 필요없으면 삭제한다.
- /docs 폴더 내용을 포함해서 실행하려면 _config.yml 파일에서 exclude의 "/docs" 부분을 주석처리한다.

> _**※ [4.17.2](https://github.com/mmistakes/minimal-mistakes/releases/tag/4.17.2) 버전 기준임**_

| 폴더/파일                       | 삭제 | 설명                                   |
|---------------------------------|------|----------------------------------------|
| .github\                        | 삭제 | Minimal Mistakes GitHub settings       |
| _data\                          |      | Jekyll data                            |
| _includes\                      |      | Jekyll include files                   |
| _layouts\                       |      | Jekyll layout files                    |
| _sass\                          |      | Jekyll sass files                      |
| assets\                         |      | Jekyll assets files                    |
| docs\                           | 삭제 | Minimal Mistakes site documents        |
| test\                           | 삭제 | Minimal Mistakes test                  |
| .editorconfig                   | 삭제 | Minimal Mistakes .editorconfig         |
| .gitattributes                  | 삭제 | Minimal Mistakes Git attributes        |
| .gitignore                      | 삭제 | Minimal Mistakes .gitignore            |
| .travis.yml                     | 삭제 | Travis-CI configuration                |
| _config.yml                     |      | Jekyll configuration                   |
| banner.js                       | 삭제 | banner.js for package.json             |
| CHANGELOG.md                    | 삭제 | Minimal Mistakes changelog             |
| Gemfile                         |      | Ruby Gemfile                           |
| index.html                      |      | index.html                             |
| LICENSE                         | 삭제 | Minimal Mistakes license (MIT license) |
| minimal-mistakes-jekyll.gemspec | 삭제 | Minimal Mistakes gemspec               |
| package.json                    | 삭제 | NPM(Node.js) configuration             |
| package-lock.json               | 삭제 | NPM(Node.js) configuration             |
| Rakefile                        | 삭제 | Ruby build script                      |
| README.md                       | 삭제 | Minimal Mistakes README.md             |
| screenshot.png                  | 삭제 | Minimal Mistakes screenshot            |
| screenshot-layouts.png          | 삭제 | Minimal Mistakes screenshot            |
| staticman.yml                   | 삭제 | Staticman configuration                |

## 글, 페이지를 저장 할 폴더 생성
- /_drafts : 블로그 초안 글 저장 폴더 (테스트 환경에서만 보기 가능)
- /_posts : 블로그 글 저장 폴더
- /_pages : 페이지 저장 폴더
