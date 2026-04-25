---
title: "4. Jekyll 기본 프로젝트 구성 이해하기"
date: 2026-04-25 09:30:00 +0900
nav_order: 4
---

# Jekyll 기본 프로젝트 구성 이해하기

Jekyll 블로그는 몇 가지 약속된 파일과 폴더를 중심으로 움직인다. 처음에는 낯설지만, 구조를 한 번 이해하면 글을 추가하고 설정을 바꾸는 일이 단순해진다.

이 글에서는 앞으로 자주 만질 파일들을 먼저 훑어본다.

## 전체 구조

Just the Docs 테마를 적용한 기본 블로그는 대략 다음과 같은 구조를 가진다.

```text
my-blog/
├─ .github/
│  └─ workflows/
│     └─ pages.yml
├─ _posts/
├─ blog/
├─ docs/
├─ _config.yml
├─ Gemfile
├─ index.md
└─ README.md
```

각 파일의 역할을 이해하면 이후 작업이 훨씬 쉬워진다.

## `_config.yml`

`_config.yml`은 Jekyll 사이트의 중심 설정 파일이다. 사이트 제목, 설명, 테마, 플러그인, URL 같은 값이 들어간다.

예시는 다음과 같다.

```yaml
title: My Blog
description: A GitHub Pages blog powered by Just the Docs.
theme: just-the-docs

permalink: pretty

plugins:
  - jekyll-feed
  - jekyll-sitemap
```

블로그 이름을 바꾸고 싶다면 먼저 이 파일을 수정하게 된다. 테마를 바꿀 때도 이 파일의 `theme` 값을 수정한다.

## `Gemfile`

`Gemfile`은 Ruby gem 의존성을 적는 파일이다. Jekyll, Just the Docs, 플러그인 등이 여기에 들어간다.

```ruby
source "https://rubygems.org"

gem "jekyll", "~> 4.4.1"
gem "just-the-docs", "0.12.0"
```

`bundle install`은 이 파일을 읽고 필요한 도구를 설치한다. 프로젝트를 다른 컴퓨터에서 열어도 같은 의존성을 설치할 수 있다.

## `index.md`

`index.md`는 사이트의 첫 화면이다. GitHub Pages 주소로 접속했을 때 가장 먼저 보이는 페이지라고 생각하면 된다.

파일 위쪽에는 front matter라고 부르는 설정 영역이 들어간다.

```markdown
---
title: Home
layout: home
nav_order: 1
---
```

front matter 아래에는 일반 Markdown 본문을 작성한다.

## `_posts`

`_posts` 폴더는 블로그 글을 넣는 곳이다. Jekyll은 이 폴더 안의 파일을 특별하게 처리한다.

파일명은 다음 규칙을 따른다.

```text
YYYY-MM-DD-title.md
```

예를 들어 다음과 같은 파일을 만들 수 있다.

```text
2026-04-25-my-first-post.md
```

각 글에도 front matter가 필요하다.

```markdown
---
title: "첫 번째 글"
date: 2026-04-25 09:00:00 +0900
---
```

## `blog/index.md`

`blog/index.md`는 글 목록 페이지로 사용할 수 있다. Jekyll의 `site.posts`를 이용하면 `_posts` 폴더에 있는 글을 반복해서 보여줄 수 있다.

```liquid
{% raw %}{% for post in site.posts %}
## [{{ post.title }}]({{ post.url | relative_url }})
{{ post.date | date: "%Y-%m-%d" }}
{{ post.excerpt }}
{% endfor %}{% endraw %}
```

이렇게 하면 새 글을 추가할 때마다 목록에 자동으로 표시된다.

## `.github/workflows/pages.yml`

이 파일은 GitHub Actions 설정이다. GitHub에 push가 발생하면 Jekyll 사이트를 빌드하고 GitHub Pages에 배포한다.

블로그를 수동으로 업로드하지 않아도 되는 이유가 바로 이 워크플로 덕분이다.

## `_site`

Jekyll을 빌드하면 `_site` 폴더가 생긴다. 이 폴더에는 최종 HTML 결과물이 들어간다.

하지만 `_site` 폴더는 보통 Git에 커밋하지 않는다. 빌드할 때마다 다시 생성되는 결과물이기 때문이다. 그래서 `.gitignore`에 `_site/`를 추가해둔다.

## 이번 단계에서 기억할 것

Jekyll 블로그를 운영할 때 자주 만지는 파일은 많지 않다.

- 사이트 설정은 `_config.yml`
- 의존성은 `Gemfile`
- 홈 화면은 `index.md`
- 블로그 글은 `_posts`
- 글 목록은 `blog/index.md`
- 배포 자동화는 `.github/workflows/pages.yml`

다음 글에서는 실제로 Just the Docs 테마를 적용한다.
