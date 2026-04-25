---
title: "9. 배포된 블로그 확인하고 기본 설정 다듬기"
date: 2026-04-25 10:20:00 +0900
nav_order: 9
---

# 배포된 블로그 확인하고 기본 설정 다듬기

GitHub Actions 배포가 성공했다면 이제 실제 Pages 주소로 접속해 블로그를 확인한다. 첫 배포가 성공하면 기본 골격은 완성된 것이다. 이후에는 사이트 제목, 설명, 링크, 내비게이션을 다듬으면 된다.

## Pages 주소 확인하기

GitHub 저장소에서 다음 경로로 이동한다.

```text
Settings > Pages
```

배포가 완료되면 Pages URL이 표시된다.

프로젝트 페이지 방식이라면 보통 다음 형태다.

```text
https://username.github.io/repository-name/
```

브라우저에서 이 주소를 열어 홈 화면이 정상적으로 보이는지 확인한다.

## 사이트 제목 바꾸기

사이트 제목은 `_config.yml`의 `title` 값으로 관리한다.

```yaml
title: My Blog
```

블로그 이름을 정했다면 이 값을 바꾼다.

```yaml
title: Dev Notes
```

제목은 브라우저 탭, 검색 결과, 테마의 상단 영역 등에 사용될 수 있다.

## 사이트 설명 바꾸기

설명은 `description`에 적는다.

```yaml
description: A GitHub Pages blog powered by Just the Docs.
```

블로그의 주제를 짧게 설명하는 문장으로 바꾼다.

```yaml
description: 개발 공부와 프로젝트 기록을 정리하는 블로그입니다.
```

## `url`과 `baseurl`

Jekyll에서는 사이트 주소를 `url`과 `baseurl`로 관리한다.

프로젝트 페이지 방식이라면 보통 다음처럼 생각할 수 있다.

```yaml
url: "https://username.github.io"
baseurl: "/repository-name"
```

다만 GitHub Actions workflow에서 `--baseurl`을 넘겨 빌드한다면 환경에 맞게 baseurl이 처리될 수 있다. 그래도 사이트 운영이 안정화되면 `_config.yml`에 명시적으로 적어두는 것도 좋다.

## 내비게이션 순서 조정하기

Just the Docs에서는 각 페이지의 front matter에 `nav_order`를 넣어 메뉴 순서를 조정할 수 있다.

```markdown
---
title: Blog
layout: default
nav_order: 2
---
```

숫자가 작을수록 앞쪽에 표시된다.

홈은 `1`, 블로그 목록은 `2`, 참고 문서는 `3`처럼 정하면 읽기 쉽다.

## 외부 링크 추가하기

`_config.yml`에 외부 링크를 추가할 수 있다.

```yaml
nav_external_links:
  - title: GitHub
    url: https://github.com/username
    hide_icon: false
```

GitHub 프로필, 포트폴리오, 이력서, 프로젝트 링크 등을 연결하면 블로그가 개인 허브 역할을 할 수 있다.

## footer 문구 바꾸기

하단 문구는 `footer_content`로 설정할 수 있다.

```yaml
footer_content: "Powered by <a href=\"https://just-the-docs.com\">Just the Docs</a>."
```

블로그 소개나 저작권 문구를 넣을 수도 있다.

```yaml
footer_content: "Copyright &copy; 2026. All rights reserved."
```

## 검색 기능 확인하기

Just the Docs는 검색 입력창을 제공한다. 검색이 켜져 있는지 확인한다.

```yaml
search_enabled: true
```

배포된 사이트에서 글 제목이나 본문 일부를 검색해본다. 글이 정상적으로 검색된다면 블로그 글이 테마에 잘 연결된 것이다.

## 이번 단계에서 확인할 것

배포 후에는 다음 항목을 확인한다.

- Pages URL로 접속된다.
- CSS가 깨지지 않는다.
- 홈, 글 목록, 포스트 링크가 정상이다.
- 사이트 제목과 설명이 원하는 값이다.
- 사이드바 순서가 자연스럽다.
- 검색 기능이 작동한다.

다음 글에서는 앞으로 꾸준히 글을 쓰기 위한 운영 규칙을 만든다.
