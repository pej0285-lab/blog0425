---
title: "3. 로컬 개발 환경 준비하기"
date: 2026-04-25 09:20:00 +0900
nav_order: 3
categories: [GitHub Pages]
tags: [jekyll, ruby, bundler]
---

# 로컬 개발 환경 준비하기

GitHub 저장소를 만들었다면 이제 로컬에서 Jekyll 사이트를 실행할 준비를 해야 한다. GitHub Pages는 GitHub에서 자동으로 사이트를 빌드해주지만, 매번 푸시한 뒤 결과를 확인하면 시간이 오래 걸린다. 로컬에서 미리 확인할 수 있으면 훨씬 편하다.

## 필요한 도구

Jekyll 블로그를 로컬에서 실행하려면 다음 도구가 필요하다.

- Git
- Ruby
- Bundler
- Jekyll

Git은 저장소를 관리하는 도구이고, Ruby는 Jekyll이 동작하는 언어다. Bundler는 Ruby 프로젝트의 의존성을 설치하고 관리한다.

## Git 설치 확인

먼저 Git이 설치되어 있는지 확인한다.

```bash
git --version
```

버전이 출력되면 설치되어 있는 것이다.

```text
git version 2.49.0
```

명령을 찾을 수 없다는 메시지가 나오면 Git을 설치해야 한다. Windows에서는 Git for Windows를 설치하면 된다.

## Ruby 설치 확인

Jekyll은 Ruby 기반 도구다. 다음 명령으로 Ruby 설치 여부를 확인한다.

```bash
ruby --version
```

버전이 출력되면 Ruby가 설치되어 있다.

```text
ruby 3.3.x
```

Windows에서는 RubyInstaller를 사용하는 경우가 많다. 설치할 때 MSYS2 개발 도구까지 함께 설치해두면 Jekyll 관련 gem을 설치할 때 문제가 줄어든다.

## Bundler 설치

Bundler는 `Gemfile`에 적힌 Ruby gem을 설치해주는 도구다.

```bash
gem install bundler
```

설치 후 버전을 확인한다.

```bash
bundle --version
```

Bundler가 준비되면 나중에 다음 명령으로 블로그 의존성을 설치할 수 있다.

```bash
bundle install
```

## Jekyll은 직접 설치해야 할까?

Jekyll을 전역으로 설치할 수도 있다.

```bash
gem install jekyll
```

하지만 프로젝트에서 `Gemfile`을 사용할 예정이라면 꼭 전역 설치가 필요하지는 않다. `Gemfile`에 `jekyll`을 적어두고 `bundle install`을 실행하면 프로젝트 안에서 필요한 버전이 설치된다.

이 방식의 장점은 프로젝트마다 Jekyll 버전을 고정할 수 있다는 점이다.

## Gemfile이 중요한 이유

Ruby 프로젝트에서는 `Gemfile`이 의존성 목록 역할을 한다. Jekyll 블로그에서는 보통 다음과 같은 내용이 들어간다.

```ruby
source "https://rubygems.org"

gem "jekyll", "~> 4.4.1"
gem "just-the-docs", "0.12.0"
```

이 파일을 기준으로 `bundle install`을 실행하면 필요한 gem이 설치된다. 이후에는 `bundle exec`를 붙여서 프로젝트에 설치된 버전으로 명령을 실행한다.

```bash
bundle exec jekyll serve
```

## Windows에서 자주 만나는 문제

Windows 환경에서는 명령이 설치되어 있어도 PATH에 등록되지 않아 터미널에서 찾지 못하는 경우가 있다.

예를 들어 Git이 설치되어 있는데 `git` 명령이 동작하지 않는다면 다음 경로에 실행 파일이 있을 수 있다.

```text
C:\Program Files\Git\cmd\git.exe
```

이런 경우 환경 변수 PATH를 수정하거나, 터미널을 다시 열어 설치 경로가 반영되었는지 확인한다.

Ruby도 마찬가지다. 설치 후 새 터미널을 열어 `ruby --version`을 다시 실행해보는 것이 좋다.

## 이번 단계에서 확인할 것

이번 글에서는 로컬 개발 환경을 준비했다.

다음 항목이 확인되면 충분하다.

- `git --version`이 동작한다.
- `ruby --version`이 동작한다.
- `bundle --version`이 동작한다.
- 프로젝트에서 `bundle install`을 실행할 준비가 되었다.

다음 글에서는 Jekyll 프로젝트의 기본 파일 구조를 살펴본다.
