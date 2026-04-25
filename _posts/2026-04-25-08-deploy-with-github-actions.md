---
title: "8. GitHub Actions로 Pages 배포하기"
date: 2026-04-25 10:10:00 +0900
nav_order: 8
categories: [GitHub Pages]
tags: [github-actions, deployment, jekyll]
---

# GitHub Actions로 Pages 배포하기

GitHub에 블로그 파일을 올렸다면 이제 배포 자동화를 설정한다. GitHub Pages는 여러 방식으로 배포할 수 있지만, 이 시리즈에서는 GitHub Actions를 사용한다.

GitHub Actions를 사용하면 `main` 브랜치에 push가 발생할 때마다 Jekyll 사이트를 빌드하고 Pages에 배포할 수 있다.

## workflow 파일 위치

GitHub Actions 워크플로 파일은 다음 위치에 둔다.

```text
.github/workflows/pages.yml
```

`.github/workflows` 폴더 안의 YAML 파일을 GitHub가 자동으로 인식한다.

## 기본 workflow 작성하기

Jekyll 사이트를 GitHub Pages로 배포하는 workflow 예시는 다음과 같다.

{% raw %}
```yaml
name: Deploy Jekyll site to Pages

on:
  push:
    branches: ["main"]
  workflow_dispatch:

permissions:
  contents: read
  pages: write
  id-token: write

concurrency:
  group: "pages"
  cancel-in-progress: true

jobs:
  build:
    runs-on: ubuntu-latest
    steps:
      - name: Checkout
        uses: actions/checkout@v6

      - name: Setup Ruby
        uses: ruby/setup-ruby@v1
        with:
          ruby-version: "3.3"
          bundler-cache: true

      - name: Setup Pages
        id: pages
        uses: actions/configure-pages@v5

      - name: Build with Jekyll
        run: bundle exec jekyll build --baseurl "${{ steps.pages.outputs.base_path }}"
        env:
          JEKYLL_ENV: production

      - name: Upload artifact
        uses: actions/upload-pages-artifact@v4

  deploy:
    environment:
      name: github-pages
      url: ${{ steps.deployment.outputs.page_url }}
    runs-on: ubuntu-latest
    needs: build
    steps:
      - name: Deploy to GitHub Pages
        id: deployment
        uses: actions/deploy-pages@v4
```
{% endraw %}

## workflow가 하는 일

이 workflow는 크게 두 단계로 나뉜다.

첫 번째는 `build` job이다.

- 저장소 코드를 가져온다.
- Ruby를 설치한다.
- Bundler 캐시를 사용해 gem을 설치한다.
- Jekyll 사이트를 빌드한다.
- 빌드 결과물을 artifact로 업로드한다.

두 번째는 `deploy` job이다.

- build job이 끝난 뒤 실행된다.
- 업로드된 artifact를 GitHub Pages에 배포한다.
- 배포된 Pages URL을 기록한다.

## Repository Settings에서 Pages 설정하기

workflow 파일을 추가했다면 GitHub 저장소 설정에서 Pages 배포 방식을 바꿔야 한다.

GitHub 저장소에서 다음 경로로 이동한다.

```text
Settings > Pages
```

`Build and deployment` 항목에서 `Source`를 `GitHub Actions`로 선택한다.

이 설정을 해야 GitHub가 Actions workflow의 배포 결과를 Pages 사이트로 사용한다.

## Actions 실행 확인하기

설정을 마친 뒤 `main` 브랜치에 push하면 Actions 탭에서 workflow 실행을 볼 수 있다.

확인할 상태는 다음과 같다.

- `queued`: 실행 대기 중
- `in_progress`: 실행 중
- `completed`: 실행 완료
- `success`: 성공
- `failure`: 실패

실패했다면 로그를 열어 어느 단계에서 문제가 생겼는지 확인한다.

## baseurl을 workflow에서 처리하는 이유

프로젝트 페이지 방식에서는 사이트 주소에 저장소 이름이 붙는다.

```text
https://username.github.io/my-blog/
```

이때 CSS나 링크 경로가 깨지지 않도록 baseurl 처리가 필요하다. 위 workflow에서는 GitHub Pages가 제공하는 base path 값을 사용해 Jekyll을 빌드한다.

{% raw %}
```yaml
bundle exec jekyll build --baseurl "${{ steps.pages.outputs.base_path }}"
```
{% endraw %}

이렇게 하면 사용자 페이지와 프로젝트 페이지 양쪽에서 경로 문제를 줄일 수 있다.

## 이번 단계에서 완료된 것

이번 글에서는 GitHub Actions로 Jekyll 블로그 배포를 자동화했다.

완료 상태는 다음과 같다.

- `.github/workflows/pages.yml`이 있다.
- GitHub Pages Source가 GitHub Actions로 설정되어 있다.
- Actions workflow가 성공한다.
- Pages URL이 생성된다.

다음 글에서는 배포된 블로그에 접속하고 기본 설정을 다듬는다.
