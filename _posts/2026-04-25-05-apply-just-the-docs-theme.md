---
title: "5. Just the Docs 테마 적용하기"
date: 2026-04-25 09:40:00 +0900
nav_order: 5
categories: [Jekyll]
tags: [jekyll, theme, just-the-docs]
---

# Just the Docs 테마 적용하기

이제 Jekyll 블로그에 Just the Docs 테마를 적용한다. Just the Docs는 문서형 사이트에 잘 어울리는 Jekyll 테마다. 사이드바, 검색, 깔끔한 본문 스타일이 기본으로 제공되어 학습 기록이나 개발 블로그에도 잘 맞는다.

## Gemfile에 테마 추가하기

먼저 `Gemfile`에 Jekyll과 Just the Docs를 추가한다.

```ruby
source "https://rubygems.org"

gem "jekyll", "~> 4.4.1"
gem "just-the-docs", "0.12.0"
```

버전을 고정하면 나중에 테마가 업데이트되어도 갑자기 사이트 모양이나 동작이 바뀌는 일을 줄일 수 있다. 최신 버전을 항상 쓰고 싶다면 버전 번호를 제거할 수도 있지만, 처음 운영할 때는 고정하는 편이 안정적이다.

## `_config.yml`에 테마 설정하기

다음으로 `_config.yml`에 테마를 지정한다.

```yaml
title: My Blog
description: A GitHub Pages blog powered by Just the Docs.
theme: just-the-docs
```

이 설정만으로 Jekyll은 Just the Docs 테마의 레이아웃과 스타일을 사용한다.

## 기본 플러그인 추가하기

블로그 운영에는 feed와 sitemap이 있으면 좋다.

```yaml
plugins:
  - jekyll-feed
  - jekyll-sitemap
```

그리고 `Gemfile`에도 같은 플러그인을 추가한다.

```ruby
group :jekyll_plugins do
  gem "jekyll-feed", "~> 0.17"
  gem "jekyll-sitemap", "~> 1.4"
end
```

`jekyll-feed`는 RSS 피드를 만들고, `jekyll-sitemap`은 검색 엔진이 사이트 구조를 이해할 수 있도록 sitemap을 만든다.

## 검색과 제목 링크 켜기

Just the Docs는 검색 기능을 제공한다. `_config.yml`에서 검색을 켤 수 있다.

```yaml
search_enabled: true
heading_anchors: true
```

`heading_anchors`를 켜면 글 안의 제목에 앵커 링크가 붙는다. 긴 글에서 특정 섹션을 공유할 때 유용하다.

## 홈 페이지 만들기

`index.md`는 사이트의 첫 화면이다.

```markdown
---
title: Home
layout: home
nav_order: 1
---

# My Blog

GitHub Pages and Just the Docs are ready.
```

`layout: home`을 사용하면 Just the Docs의 홈 레이아웃을 적용할 수 있다.

## 글 목록 페이지 만들기

블로그 글을 모아 보여줄 페이지도 만든다. 예를 들어 `blog/index.md`를 만들 수 있다.

```markdown
---
title: Blog
layout: default
nav_order: 2
has_children: true
permalink: /blog/
---
```

본문에서는 `site.posts`를 반복해서 글 목록을 출력한다.

```liquid
{% raw %}{% for post in site.posts %}
## [{{ post.title }}]({{ post.url | relative_url }})
{{ post.date | date: "%Y-%m-%d" }}
{{ post.excerpt }}
{% endfor %}{% endraw %}
```

## 첫 번째 글 작성하기

`_posts` 폴더에 첫 글을 만든다.

```text
_posts/2026-04-25-welcome.md
```

본문은 다음처럼 시작할 수 있다.

```markdown
---
title: Welcome
date: 2026-04-25 09:00:00 +0900
---

# Welcome

첫 번째 글입니다.
```

Jekyll은 파일명과 front matter를 읽고 이 글을 블로그 포스트로 처리한다.

## 이번 단계에서 완성된 것

이제 블로그에는 다음 요소가 생겼다.

- Just the Docs 테마
- 사이트 기본 설정
- 홈 페이지
- 블로그 글 목록 페이지
- 첫 번째 포스트
- 검색과 heading anchor 설정

다음 글에서는 이 블로그를 로컬에서 실행해 실제 화면을 확인한다.
