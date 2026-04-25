---
title: "7. GitHub에 커밋하고 푸시하기"
date: 2026-04-25 10:00:00 +0900
nav_order: 7
---

# GitHub에 커밋하고 푸시하기

로컬에서 블로그가 정상적으로 보인다면 이제 변경 사항을 GitHub 저장소에 올릴 차례다. GitHub Pages는 저장소에 올라간 파일을 기준으로 사이트를 배포하므로, 로컬 작업을 커밋하고 푸시해야 한다.

## 변경 파일 확인하기

먼저 현재 변경 상태를 확인한다.

```bash
git status
```

새로 만든 파일이나 수정한 파일 목록이 보인다. 짧게 보고 싶다면 다음 명령을 사용할 수 있다.

```bash
git status --short
```

처음 블로그를 구성했다면 다음과 같은 파일들이 보일 수 있다.

```text
?? Gemfile
?? _config.yml
?? index.md
?? _posts/
?? blog/
?? .github/
```

`??`는 아직 Git이 추적하지 않는 새 파일이라는 뜻이다.

## 스테이징하기

커밋에 포함할 파일을 스테이징한다.

```bash
git add .
```

`.`은 현재 폴더 아래의 변경 사항을 모두 추가한다는 의미다.

일부 파일만 추가하고 싶다면 파일명을 직접 적는다.

```bash
git add _config.yml index.md
```

## 커밋 만들기

스테이징한 변경 사항을 커밋한다.

```bash
git commit -m "Set up Just the Docs GitHub Pages blog"
```

커밋 메시지는 나중에 변경 이력을 봤을 때 이해할 수 있게 쓰는 것이 좋다.

좋은 커밋 메시지는 대체로 다음 특징을 가진다.

- 무엇을 바꿨는지 드러난다.
- 너무 길지 않다.
- 한 커밋에 하나의 목적이 담긴다.

예시는 다음과 같다.

```text
Set up Just the Docs GitHub Pages blog
Add first blog posts
Configure GitHub Pages workflow
```

## GitHub로 푸시하기

커밋을 만들었다면 원격 저장소로 푸시한다.

```bash
git push origin main
```

여기서 `origin`은 원격 저장소 이름이고, `main`은 브랜치 이름이다.

처음 푸시하는 브랜치라면 다음 명령을 사용할 수도 있다.

```bash
git push -u origin main
```

`-u` 옵션을 쓰면 이후에는 `git push`만 입력해도 같은 원격 브랜치로 푸시할 수 있다.

## GitHub에서 확인하기

푸시가 끝나면 GitHub 저장소 페이지를 새로고침한다. 로컬에서 만든 파일들이 GitHub에 보이면 성공이다.

확인할 파일은 다음과 같다.

- `_config.yml`
- `Gemfile`
- `index.md`
- `_posts`
- `blog/index.md`
- `.github/workflows/pages.yml`

## 인증 문제가 생길 때

HTTPS 주소로 푸시할 때 GitHub 로그인이 필요할 수 있다. 요즘 GitHub는 비밀번호 대신 토큰 또는 GitHub CLI 인증을 사용한다.

Windows에서는 Git Credential Manager가 로그인 창을 띄워주는 경우가 많다. 브라우저에서 GitHub 로그인을 완료하면 이후 푸시는 자동으로 인증된다.

## 이번 단계에서 완료된 것

이번 글에서는 로컬 블로그 파일을 GitHub 저장소에 올렸다.

정리하면 다음 흐름이다.

```bash
git status
git add .
git commit -m "Set up Just the Docs GitHub Pages blog"
git push origin main
```

다음 글에서는 GitHub Actions를 이용해 GitHub Pages 배포를 자동화한다.
