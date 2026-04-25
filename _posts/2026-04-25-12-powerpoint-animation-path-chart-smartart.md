---
title: "12. PowerPoint에서 이동 경로, 차트, 스마트아트 애니메이션 만들기"
date: 2026-04-25 10:50:00 +0900
nav_order: 12
categories: [PowerPoint]
tags: [powerpoint, animation, chart, smartart]
image:
  path: /assets/images/posts/animation-making/powerpoint-animation-08.png
  alt: PowerPoint animation preview
---

# PowerPoint에서 이동 경로, 차트, 스마트아트 애니메이션 만들기

PowerPoint 애니메이션은 단순히 개체를 나타나게 하는 기능만 있는 것이 아니다. 개체가 특정 경로를 따라 움직이게 만들 수도 있고, 차트나 스마트아트 그래픽이 항목별로 나타나도록 설정할 수도 있다.

이번 글에서는 문서의 예제 흐름을 바탕으로 두 가지 작업을 정리한다.

| 구분 | 예제 파일 | 결과 파일 |
|---|---|---|
| 이동 경로 애니메이션 | `나비_이동경로.pptx` | `나비_이동경로_완성.pptx` |
| 차트와 스마트아트 애니메이션 | `보안_애니메이션.pptx` | `보안_애니메이션_완성.pptx` |

## 1. 경로를 따라 이동하는 애니메이션 만들기

첫 번째 작업은 나비 개체가 지정한 경로를 따라 움직이도록 만드는 것이다. PowerPoint의 `추가 이동 경로` 기능을 사용하면 직선뿐 아니라 곡선, 물결 모양 같은 다양한 이동 경로를 적용할 수 있다.

### 나비 개체 선택 후 추가 이동 경로 열기

화면 왼쪽의 나비 개체를 선택한다. 그다음 상단 메뉴에서 `애니메이션` 탭을 열고, `애니메이션` 그룹의 `자세히` 단추를 클릭한다. 목록이 열리면 `추가 이동 경로`를 선택한다.

![나비 개체를 선택하고 추가 이동 경로 메뉴 열기]({{ "/assets/images/posts/animation-making/powerpoint-animation-01.png" | relative_url }})

이동 경로 메뉴는 기본 목록에 보이지 않는 더 많은 이동 애니메이션을 선택할 때 사용한다. 예제처럼 나비가 화면을 가로질러 이동해야 하는 경우에는 먼저 적절한 이동 경로를 고른 뒤, 경로 길이를 다시 조정하는 방식이 편하다.

![추가 이동 경로 선택 화면]({{ "/assets/images/posts/animation-making/powerpoint-animation-02.png" | relative_url }})

### 작아지는 물결 경로 선택하기

`이동 경로 변경` 대화상자가 열리면 `직선 및 곡선 경로`에서 `작아지는 물결`을 선택하고 `확인`을 클릭한다.

![이동 경로 변경에서 작아지는 물결 선택]({{ "/assets/images/posts/animation-making/powerpoint-animation-03.png" | relative_url }})

이 설정을 적용하면 나비 옆에 이동 경로가 나타난다. PowerPoint에서는 시작 위치, 실제 이동 경로, 마지막 위치를 화면 위에서 확인할 수 있다.

### 이동 경로 길이 조정하기

애니메이션 경로가 나타나면 종료 지점의 조절점을 오른쪽으로 드래그한다. 이렇게 하면 나비가 이동하는 거리를 더 길게 만들 수 있다.

![이동 경로가 나타난 화면]({{ "/assets/images/posts/animation-making/powerpoint-animation-04.png" | relative_url }})

경로를 가로 방향으로 길게 수정한 뒤에는 `애니메이션` 탭의 `애니메이션` 그룹에서 `추가 효과 옵션 표시` 아이콘을 클릭한다. 이 설정 창에서 이동 속도와 부드럽게 시작/종료 옵션을 조정할 수 있다.

![이동 경로를 길게 조정한 화면]({{ "/assets/images/posts/animation-making/powerpoint-animation-05.png" | relative_url }})

### 효과와 타이밍 조정하기

`작아지는 물결` 대화상자가 열리면 먼저 `효과` 탭을 확인한다. `부드럽게 시작`과 `부드럽게 종료` 값을 모두 `0초`로 지정한다.

![효과 탭에서 부드럽게 시작과 종료 조정]({{ "/assets/images/posts/animation-making/powerpoint-animation-06.png" | relative_url }})

다음으로 `타이밍` 탭을 선택한다. `재생 시간`에서 `3초(느리게)`를 선택한 뒤 `확인`을 클릭한다.

![타이밍 탭에서 재생 시간을 3초로 설정]({{ "/assets/images/posts/animation-making/powerpoint-animation-07.png" | relative_url }})

`부드럽게 시작`과 `부드럽게 종료`가 설정되어 있으면 애니메이션이 시작과 끝에서 천천히 움직이고, 중간 구간에서 조금 더 빠르게 재생된다. 일정한 속도로 움직이는 효과를 원한다면 두 값을 `0초`로 맞추는 것이 좋다.

### 미리보기로 확인하기

설정이 끝나면 `애니메이션` 탭의 `미리보기` 그룹에서 `미리보기`를 클릭한다. 나비가 지정한 경로를 따라 움직이는지 확인한다.

![미리보기로 이동 경로 애니메이션 확인]({{ "/assets/images/posts/animation-making/powerpoint-animation-08.png" | relative_url }})

애니메이션을 확인하는 방법은 여러 가지가 있다.

| 방법 | 설명 |
|---|---|
| `F5` | 처음부터 슬라이드 쇼를 실행한다. |
| ![쇼 보기 아이콘]({{ "/assets/images/posts/animation-making/powerpoint-animation-09.png" | relative_url }}) 쇼 보기 | 현재 슬라이드 쇼 보기로 실행한다. |
| ![읽기용 보기 아이콘]({{ "/assets/images/posts/animation-making/powerpoint-animation-10.png" | relative_url }}) 읽기용 보기 | 읽기용 보기에서 애니메이션을 확인한다. |

### 이동 경로 애니메이션 위치 이해하기

이동 경로 애니메이션을 적용하면 개체가 마지막으로 이동할 위치에 투명한 이미지가 나타난다. 이 이미지를 고스트 이미지처럼 생각하면 된다.

| 표시 요소 | 의미 |
|---|---|
| ![시작 위치 표시]({{ "/assets/images/posts/animation-making/powerpoint-animation-11.png" | relative_url }}) 시작 위치 | 애니메이션이 시작되는 개체의 위치 |
| 점선 경로 | 애니메이션이 재생될 때 개체가 따라가는 이동 경로 |
| ![종료 위치 표시]({{ "/assets/images/posts/animation-making/powerpoint-animation-12.png" | relative_url }}) 종료 위치 | 애니메이션이 끝났을 때 개체가 도착하는 위치 |

아래 화면처럼 시작 위치, 점선 경로, 종료 위치를 함께 보면 개체가 어떤 방향으로 얼마나 이동하는지 쉽게 파악할 수 있다.

![이동 경로 애니메이션의 시작 위치와 종료 위치]({{ "/assets/images/posts/animation-making/powerpoint-animation-13.png" | relative_url }})

## 2. 차트와 스마트아트 그래픽에 애니메이션 설정하기

두 번째 작업은 차트와 스마트아트 그래픽에 애니메이션을 적용하는 것이다. 일반 도형과 달리 차트나 스마트아트는 전체 개체를 한 번에 나타나게 할 수도 있고, 항목별 또는 수준별로 순차적으로 나타나게 할 수도 있다.

### 차트에 닦아내기 애니메이션 적용하기

1번 슬라이드의 차트를 선택한다. `애니메이션` 탭에서 `애니메이션` 그룹의 `자세히` 단추를 클릭한 뒤, `나타내기` 항목의 `닦아내기`를 선택한다.

![차트에 닦아내기 애니메이션 적용]({{ "/assets/images/posts/animation-making/powerpoint-animation-14.png" | relative_url }})

슬라이드 쇼 단추를 눌러 애니메이션 효과를 확인한 뒤, `ESC`를 눌러 편집 화면으로 돌아온다.

![차트 애니메이션 슬라이드 쇼 확인]({{ "/assets/images/posts/animation-making/powerpoint-animation-15.png" | relative_url }})

### 차트 애니메이션을 항목별로 설정하기

슬라이드로 돌아오면 `애니메이션` 탭에서 `효과 옵션`을 클릭한다. `시퀀스` 항목에서 `항목별로`를 선택한다.

![차트 효과 옵션에서 항목별로 선택]({{ "/assets/images/posts/animation-making/powerpoint-animation-16.png" | relative_url }})

이렇게 설정하면 차트 전체가 한 번에 나타나는 대신, 항목이 순서대로 나타난다. 자료 설명을 단계적으로 진행할 때 유용하다.

설정 후에는 `미리 보기`를 클릭해 결과를 확인한다.

![차트 항목별 애니메이션 미리 보기]({{ "/assets/images/posts/animation-making/powerpoint-animation-17.png" | relative_url }})

### 스마트아트에 확대/축소 애니메이션 적용하기

이번에는 2번 슬라이드의 스마트아트 그래픽을 선택한다. `애니메이션` 탭의 `애니메이션` 그룹에서 `자세히` 단추를 클릭하고, `나타내기` 항목의 `확대/축소`를 선택한다.

![스마트아트에 확대/축소 애니메이션 적용]({{ "/assets/images/posts/animation-making/powerpoint-animation-18.png" | relative_url }})

슬라이드 쇼를 실행해 효과를 확인한 뒤 `ESC`를 눌러 다시 편집 화면으로 돌아온다.

![스마트아트 애니메이션 슬라이드 쇼 확인]({{ "/assets/images/posts/animation-making/powerpoint-animation-19.png" | relative_url }})

### 스마트아트 시퀀스를 수준별로 설정하기

스마트아트는 구성 요소가 계층 구조를 가질 수 있다. 슬라이드로 돌아온 뒤 `애니메이션` 탭에서 `효과 옵션`을 클릭하고, `시퀀스`에서 `수준(한 번에)`를 선택한다.

![스마트아트 효과 옵션에서 수준 한 번에 선택]({{ "/assets/images/posts/animation-making/powerpoint-animation-20.png" | relative_url }})

이 설정을 사용하면 스마트아트의 같은 수준에 있는 항목들이 함께 나타난다. 전체 구조를 한 번에 보여주기보다 계층별로 설명하고 싶을 때 적합하다.

마지막으로 `미리보기` 또는 `슬라이드 쇼`를 실행하여 설정한 애니메이션이 원하는 순서대로 재생되는지 확인한다.

![스마트아트 애니메이션 최종 확인]({{ "/assets/images/posts/animation-making/powerpoint-animation-21.png" | relative_url }})

## 설정 요약

| 작업 | 애니메이션 | 핵심 설정 |
|---|---|---|
| 나비 이동 | 추가 이동 경로, 작아지는 물결 | 경로 길이 조정, 부드럽게 시작/종료 `0초`, 재생 시간 `3초(느리게)` |
| 차트 | 닦아내기 | 효과 옵션에서 시퀀스 `항목별로` |
| 스마트아트 | 확대/축소 | 효과 옵션에서 시퀀스 `수준(한 번에)` |

PowerPoint 애니메이션은 많이 넣는 것보다 의도에 맞게 조절하는 것이 중요하다. 이동 경로는 개체의 움직임을 설명할 때 좋고, 차트와 스마트아트의 시퀀스 옵션은 발표 흐름에 맞춰 정보를 순서대로 보여줄 때 효과적이다.
