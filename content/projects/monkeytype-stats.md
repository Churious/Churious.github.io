---
title: "MonkeyType Stats Viewer"
description: "Monkeytype 타자 기록을 GitHub 프로필용 이미지로 동적으로 보여주는 서비스"
tags: ["Go", "Vercel", "GitHub", "API"]
year: "2025"
posterTitle: "TYPE<br>YOUR<br><em>BEST.</em>"
posterLabel: "MONKEYTYPE STATS"
link: "https://monkeytype-stats.vercel.app"
repo: "https://github.com/Churious/monkeytype-stats"
---

## 프로필에 움직이는 기록을

Monkeytype의 타자 기록을 GitHub 프로필 README에 바로 넣을 수 있는 이미지 API로 만들었습니다. 사용자가 지정한 테마, 모드, 기록 길이에 맞춰 결과 이미지를 동적으로 생성합니다.

## 사용 방법

쿼리 파라미터로 Monkeytype 사용자명과 원하는 설정을 전달하면 됩니다. `theme`, `mode`, `length`를 조합해 각자의 프로필에 맞는 카드를 만들 수 있습니다.

GitHub의 이미지 캐시 특성상 기록이 갱신된 뒤 화면에 반영되기까지 약간의 시간이 걸릴 수 있습니다.

## 구현 포인트

- Go 기반 API로 Monkeytype 데이터를 조회하고 프로필 이미지를 생성합니다.
- Vercel에 배포해 별도 서버 관리 없이 API를 제공합니다.
- Monkeytype의 다양한 테마와 time / words 모드를 지원합니다.
- GitHub README의 Markdown 이미지 링크만으로 사용할 수 있도록 구성했습니다.
