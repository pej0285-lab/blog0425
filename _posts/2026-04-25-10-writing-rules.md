---
title: "10. 블로그 운영을 위한 글 작성 규칙 만들기"
date: 2026-04-25 10:30:00 +0900
nav_order: 10
categories: [Blogging]
tags: [writing, markdown, workflow]
---

# 블로그 운영을 위한 글 작성 규칙 만들기

블로그를 만드는 것보다 더 중요한 일은 계속 운영하는 것이다. 처음에는 설정과 배포가 어렵게 느껴지지만, 블로그가 만들어진 뒤에는 글을 꾸준히 쓰는 습관과 규칙이 더 중요해진다.

이번 글에서는 Jekyll 블로그를 운영하기 위한 글 작성 규칙을 정리한다.

## 파일명 규칙

Jekyll 포스트는 `_posts` 폴더에 넣고, 파일명은 날짜로 시작한다.

```text
YYYY-MM-DD-title.md
```

예시는 다음과 같다.

```text
2026-04-25-how-to-use-github-pages.md
```

파일명은 URL에도 영향을 준다. 한글 제목을 쓰더라도 파일명은 영어 소문자와 하이픈을 사용하는 편이 관리하기 쉽다.

## front matter 규칙

각 글의 맨 위에는 front matter를 넣는다.

```markdown
---
title: "글 제목"
date: 2026-04-25 09:00:00 +0900
nav_order: 1
---
```

최소한 `title`과 `date`는 넣는 것이 좋다. Just the Docs 내비게이션에서 순서를 조정하고 싶다면 `nav_order`도 사용할 수 있다.

## 글 제목 규칙

제목은 검색과 목록에서 가장 먼저 보인다. 너무 추상적인 제목보다 무엇을 다루는지 드러나는 제목이 좋다.

예를 들어 다음 제목은 모호하다.

```text
설정하기
```

다음 제목은 더 구체적이다.

```text
GitHub Actions로 Jekyll 블로그 자동 배포하기
```

글을 나중에 다시 찾을 때도 구체적인 제목이 유리하다.

## 카테고리와 태그

Jekyll에서는 front matter에 카테고리와 태그를 넣을 수 있다.

```markdown
---
title: "GitHub Pages 배포하기"
date: 2026-04-25 09:00:00 +0900
categories: [github-pages]
tags: [jekyll, github-actions, blog]
---
```

처음부터 너무 많은 태그를 만들 필요는 없다. 자주 쓸 큰 주제 위주로 시작하는 것이 좋다.

예시는 다음과 같다.

- `github-pages`
- `jekyll`
- `frontend`
- `til`
- `project`

## 이미지 저장 위치

글에 이미지를 넣을 계획이라면 저장 위치를 정해두는 것이 좋다.

예를 들어 다음과 같은 구조를 사용할 수 있다.

```text
assets/
└─ images/
   └─ 2026-04-25-github-pages/
      └─ screenshot-01.png
```

본문에서는 다음처럼 연결한다.

{% raw %}
```markdown
![GitHub Pages settings]({{ "/assets/images/2026-04-25-github-pages/screenshot-01.png" | relative_url }})
```
{% endraw %}

`relative_url`을 사용하면 `baseurl`이 있는 GitHub Pages 프로젝트에서도 경로가 깨질 가능성이 줄어든다.

## 코드 블록 규칙

개발 블로그에서는 코드 블록을 자주 사용한다. 언어 이름을 함께 적으면 문법 강조가 적용된다.

````markdown
```bash
bundle exec jekyll serve
```
````

YAML, Ruby, Markdown도 자주 사용한다.

````markdown
```yaml
theme: just-the-docs
```
````

## 글 템플릿 만들기

매번 처음부터 글 구조를 만들기 어렵다면 자신만의 템플릿을 정해두면 좋다.

```markdown
---
title: "제목"
date: YYYY-MM-DD HH:MM:SS +0900
categories: []
tags: []
---

# 제목

## 문제 또는 목표

## 작업 과정

## 결과

## 배운 점
```

글마다 완벽한 형식을 지킬 필요는 없지만, 기본 틀이 있으면 쓰기 시작하기가 쉬워진다.

## 커밋 단위 정하기

블로그 글도 코드처럼 Git으로 관리된다. 글 하나를 작성하거나 수정했다면 의미 있는 단위로 커밋한다.

```bash
git add _posts/2026-04-25-how-to-use-github-pages.md
git commit -m "Add post about GitHub Pages setup"
git push
```

작은 단위로 커밋하면 나중에 어떤 글을 언제 수정했는지 추적하기 쉽다.

## 운영 루틴 만들기

블로그를 오래 운영하려면 부담이 적어야 한다. 처음부터 긴 글만 쓰려고 하면 금방 멈추기 쉽다.

추천하는 운영 루틴은 다음과 같다.

- 짧은 TIL 글을 자주 쓴다.
- 프로젝트를 진행할 때 작업 기록을 남긴다.
- 오류 해결 과정을 그대로 정리한다.
- 긴 튜토리얼은 여러 편으로 나눈다.
- 한 달에 한 번 오래된 글을 업데이트한다.

## 마무리

이제 GitHub 저장소를 만들고, Jekyll과 Just the Docs 테마를 적용하고, GitHub Pages로 배포하는 전체 과정을 마쳤다.

앞으로는 `_posts` 폴더에 글을 추가하고 GitHub에 푸시하면 된다. GitHub Actions가 자동으로 사이트를 빌드하고 배포한다.

블로그는 한 번에 완성되는 결과물이 아니라 계속 다듬는 공간이다. 처음에는 단순하게 시작하고, 글이 쌓이면서 구조와 디자인을 조금씩 개선하면 된다.
