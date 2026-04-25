---
title: "6. 로컬에서 블로그 미리보기"
date: 2026-04-25 09:50:00 +0900
nav_order: 6
---

# 로컬에서 블로그 미리보기

테마와 기본 페이지를 만들었다면 이제 로컬에서 블로그를 실행해본다. 로컬 미리보기는 GitHub에 올리기 전에 오류를 찾고, 글이 어떻게 보이는지 확인하는 가장 좋은 방법이다.

## 의존성 설치하기

프로젝트 루트에서 다음 명령을 실행한다.

```bash
bundle install
```

Bundler는 `Gemfile`을 읽고 Jekyll, Just the Docs, 플러그인을 설치한다.

설치가 끝나면 `Gemfile.lock` 파일이 생길 수 있다. 이 파일은 실제로 설치된 gem 버전을 기록한다. 협업하거나 배포 환경과 버전을 맞추고 싶다면 커밋하는 것이 좋다.

## Jekyll 서버 실행하기

다음 명령으로 로컬 서버를 실행한다.

```bash
bundle exec jekyll serve
```

정상적으로 실행되면 보통 다음 주소에서 사이트를 확인할 수 있다.

```text
http://localhost:4000
```

브라우저로 이 주소에 접속하면 GitHub Pages에 올리기 전의 블로그 화면을 볼 수 있다.

## `bundle exec`를 붙이는 이유

Jekyll 명령을 실행할 때 다음처럼 직접 실행할 수도 있다.

```bash
jekyll serve
```

하지만 프로젝트에서는 다음처럼 실행하는 편이 좋다.

```bash
bundle exec jekyll serve
```

`bundle exec`는 현재 프로젝트의 `Gemfile` 기준으로 설치된 gem을 사용하게 해준다. 컴퓨터 전체에 설치된 다른 버전의 Jekyll과 충돌하는 문제를 줄일 수 있다.

## 변경 사항 확인하기

Jekyll 서버가 실행 중일 때 Markdown 파일을 수정하면 사이트가 다시 빌드된다. 대부분의 경우 브라우저를 새로고침하면 수정 내용이 반영된다.

확인해볼 항목은 다음과 같다.

- 홈 페이지가 정상적으로 보이는가
- 사이드바 메뉴가 원하는 순서로 보이는가
- 블로그 글 목록이 보이는가
- 포스트 본문이 깨지지 않는가
- 검색 입력창이 나타나는가

## 자주 만나는 오류

`bundle install`에서 오류가 난다면 Ruby 설치 상태를 먼저 확인한다.

```bash
ruby --version
bundle --version
```

`jekyll serve`에서 테마를 찾을 수 없다는 오류가 난다면 `Gemfile`에 `just-the-docs`가 들어 있는지 확인한다.

```ruby
gem "just-the-docs", "0.12.0"
```

`_config.yml`에도 테마 설정이 필요하다.

```yaml
theme: just-the-docs
```

## `_site` 폴더는 커밋하지 않기

로컬에서 Jekyll을 실행하면 `_site` 폴더가 생성된다. 이 폴더에는 빌드된 HTML 결과물이 들어 있다.

하지만 `_site`는 원본이 아니라 결과물이다. 그래서 `.gitignore`에 추가해 Git이 추적하지 않도록 한다.

```gitignore
_site/
.jekyll-cache/
.jekyll-metadata
```

GitHub Actions에서도 사이트를 새로 빌드하므로 `_site`를 직접 저장소에 올릴 필요가 없다.

## 이번 단계에서 확인할 것

로컬 미리보기에서 다음이 확인되면 다음 단계로 넘어가도 된다.

- `bundle install`이 성공한다.
- `bundle exec jekyll serve`가 실행된다.
- `http://localhost:4000`에서 사이트가 열린다.
- 홈, 글 목록, 포스트가 정상적으로 보인다.

다음 글에서는 변경 사항을 Git에 커밋하고 GitHub로 푸시한다.
