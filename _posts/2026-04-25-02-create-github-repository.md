---
title: "2. GitHub에서 새 저장소 만들기"
date: 2026-04-25 09:10:00 +0900
nav_order: 2
categories: [GitHub Pages]
tags: [github, repository, blog]
---

# GitHub에서 새 저장소 만들기

이제 블로그가 올라갈 GitHub 저장소를 만들 차례다. GitHub Pages 블로그는 결국 하나의 GitHub 저장소에서 시작한다. 저장소에는 블로그 설정, 글, 테마 구성, 배포 워크플로가 모두 들어간다.

## 저장소 이름 정하기

GitHub Pages에서는 저장소 이름에 따라 주소가 달라진다. 크게 두 가지 방식이 있다.

첫 번째는 사용자 페이지 방식이다.

```text
username.github.io
```

이 이름으로 저장소를 만들면 블로그 주소는 보통 다음처럼 된다.

```text
https://username.github.io/
```

두 번째는 프로젝트 페이지 방식이다.

```text
my-blog
```

이 경우 블로그 주소는 다음처럼 저장소 이름이 뒤에 붙는다.

```text
https://username.github.io/my-blog/
```

처음 연습하거나 여러 개의 사이트를 운영할 생각이라면 프로젝트 페이지 방식이 편하다. 이 시리즈에서는 일반 저장소 이름을 사용하는 프로젝트 페이지 방식을 기준으로 설명한다.

## 새 Repository 만들기

GitHub에 로그인한 뒤 오른쪽 위의 `+` 버튼을 누르고 `New repository`를 선택한다.

입력할 항목은 다음과 같다.

- Repository name: 블로그 저장소 이름
- Description: 저장소 설명
- Visibility: Public 또는 Private
- README: 처음에는 선택해도 되고 선택하지 않아도 된다.

GitHub Pages로 공개 블로그를 운영할 계획이라면 보통 `Public` 저장소가 가장 단순하다. GitHub 요금제와 설정에 따라 Private 저장소에서도 Pages를 쓸 수 있지만, 처음에는 Public으로 시작하는 편이 시행착오가 적다.

## README를 만들까?

새 저장소를 만들 때 `Add a README file` 옵션이 있다. 이 옵션을 켜면 GitHub가 기본 `README.md` 파일을 만들어준다.

처음부터 로컬에서 파일을 직접 만들 계획이라면 README 없이 시작해도 된다. 반대로 GitHub 웹 화면에서 바로 저장소를 확인하고 싶다면 README를 포함해도 된다.

이 시리즈에서는 블로그 파일을 직접 구성할 것이므로 README가 이미 있더라도 나중에 내용을 바꿀 수 있다.

## 저장소를 로컬로 가져오기

저장소를 만들었다면 로컬 컴퓨터로 가져온다. GitHub 저장소 화면에서 `Code` 버튼을 누르면 HTTPS 주소를 복사할 수 있다.

```bash
git clone https://github.com/username/my-blog.git
```

명령을 실행하면 현재 폴더 아래에 저장소 이름과 같은 폴더가 생긴다.

```bash
cd my-blog
```

이제 이 폴더 안에서 블로그 파일을 만들고 수정하면 된다.

## 원격 저장소 확인하기

로컬 저장소가 GitHub와 연결되어 있는지 확인하려면 다음 명령을 실행한다.

```bash
git remote -v
```

정상이라면 `origin`이라는 이름으로 GitHub 주소가 보인다.

```text
origin  https://github.com/username/my-blog.git (fetch)
origin  https://github.com/username/my-blog.git (push)
```

`origin`은 로컬 저장소가 바라보는 기본 원격 저장소 이름이다. 나중에 `git push origin main`을 실행하면 이 GitHub 저장소로 변경 사항이 올라간다.

## 기본 브랜치 확인하기

최근 GitHub 저장소의 기본 브랜치는 보통 `main`이다. 다음 명령으로 현재 브랜치를 확인할 수 있다.

```bash
git branch --show-current
```

결과가 `main`이면 이후 예제 명령을 그대로 따라가면 된다.

## 이번 단계에서 확인할 것

이번 글에서는 블로그의 기반이 되는 GitHub 저장소를 만들었다. 아직 Jekyll이나 테마는 적용하지 않았다.

정리하면 다음 상태가 되면 된다.

- GitHub에 새 저장소가 있다.
- 저장소가 로컬 컴퓨터에 clone되어 있다.
- 로컬 저장소에 `origin` 원격 주소가 설정되어 있다.
- 기본 브랜치가 `main`이다.

다음 글에서는 로컬에서 Jekyll을 실행하기 위한 개발 환경을 준비한다.
