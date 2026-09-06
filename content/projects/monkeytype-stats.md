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

## API 예시

아래처럼 URL을 Markdown 이미지 주소로 사용하면 실시간 타자 기록 카드를 프로필에 삽입할 수 있습니다.

![Churious MonkeyType stats 예시](https://monkeytype-stats.vercel.app/api?user=Churious&theme=blueberry_dark&mode=time&length=30)

```text
https://monkeytype-stats.vercel.app/api?user=Churious&theme=blueberry_dark&mode=time&length=30
```

## 파라미터

| 파라미터 | 설명 | 기본값 | 사용 예시 |
| --- | --- | --- | --- |
| `username` | **필수** · Monkeytype 사용자 이름 | - | `?username=MiDeco` |
| `theme` | 테마 이름 · [Monkeytype의 모든 테마 지원](https://github.com/monkeytypegame/monkeytype/tree/master/frontend/static/themes) | `dark` | `?theme=serika_dark` |
| `mode` | 타이핑 모드 · `time` 또는 `words` | `time` | `?mode=words` |
| `length` | `time` 모드: `15`, `30`, `60`, `120`; `words` 모드: `10`, `25`, `50`, `100` | `60` | `?length=25` |

## 사용 방법

쿼리 파라미터로 Monkeytype 사용자명과 원하는 설정을 전달하면 됩니다. `theme`, `mode`, `length`를 조합해 각자의 프로필에 맞는 카드를 만들 수 있습니다.

GitHub의 이미지 캐시 특성상 기록이 갱신된 뒤 화면에 반영되기까지 약간의 시간이 걸릴 수 있습니다.

## 구현 포인트

- Go 기반 API로 Monkeytype 데이터를 조회하고 프로필 이미지를 생성합니다.
- Vercel에 배포해 별도 서버 관리 없이 API를 제공합니다.
- Monkeytype의 다양한 테마와 time / words 모드를 지원합니다.
- GitHub README의 Markdown 이미지 링크만으로 사용할 수 있도록 구성했습니다.
