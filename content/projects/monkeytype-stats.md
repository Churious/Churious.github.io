---
title: "MonkeyType Stats Viewer"
description: "GitHub 프로필에 Monkeytype 타자 기록을 동적으로 보여주는 카드 생성기"
tags: ["Go", "Vercel", "GitHub", "Monkeytype"]
year: "2025"
posterTitle: "TYPE<br>YOUR<br><em>BEST.</em>"
posterLabel: "MONKEYTYPE STATS"
link: "https://monkeytype-stats.vercel.app"
repo: "https://github.com/Churious/monkeytype-stats"
---

## GitHub 프로필을 위한 타자 기록 카드

Monkeytype Stats Viewer는 Monkeytype 통계를 GitHub 프로필에 동적으로 표시하는 프로젝트입니다. Vercel로 배포한 뒤 사이트에 접속하면 **Monkeytype Stats Builder**에서 사용자명, 테마, 모드, 테스트 길이를 설정하고 나만의 카드를 만들 수 있습니다.

## Builder 사용하기

[Monkeytype Stats Builder 열기 ↗](https://monkeytype-stats.vercel.app)

Builder에서 설정을 바꾸면 미리보기 카드가 즉시 갱신되고, 완성된 Markdown을 클릭해서 복사할 수 있습니다. 복사한 내용을 GitHub 프로필 README에 붙여 넣으면 됩니다.

## 배포

직접 인스턴스를 배포하고 싶다면 저장소를 원하는 플랫폼으로 가져오면 됩니다. Go와의 호환성이 가장 좋은 배포 환경으로 Vercel을 권장합니다.

| 플랫폼 | 배포 |
| --- | --- |
| **Vercel** | [Vercel로 배포하기](https://vercel.com/new/clone?repository-url=https://github.com/Churious/monkeytype-stats) · 권장 |
| **Netlify** | [Netlify로 배포하기](https://app.netlify.com/start/deploy?repository=https://github.com/Churious/monkeytype-stats) |
| **Railway** | [Railway로 배포하기](https://railway.app/new/template?template=https://github.com/Churious/monkeytype-stats) · 체험용 |

## 설정

Builder를 사용하지 않고 직접 카드를 설정할 때는 URL 쿼리 파라미터를 사용할 수 있습니다.

| 파라미터 | 설명 | 기본값 | 사용 예시 |
| --- | --- | --- | --- |
| `username` | **필수** · Monkeytype 사용자 이름 | - | `?username=MiDeco` |
| `theme` | 테마 이름 · [Monkeytype의 모든 테마 지원](https://github.com/monkeytypegame/monkeytype/tree/master/frontend/static/themes) | `dark` | `?theme=serika_dark` |
| `mode` | 타이핑 모드 · `time` 또는 `words` | `time` | `?mode=words` |
| `length` | `time` 모드: `15`, `30`, `60`, `120`; `words` 모드: `10`, `25`, `50`, `100` | `60` | `?length=25` |

### 실제 임베드 예시

![Churious의 Monkeytype 30초 기록 카드](https://monkeytype-stats.vercel.app/api?user=Churious&theme=blueberry_dark&mode=time&length=30)

```text
https://monkeytype-stats.vercel.app/api?user=Churious&theme=blueberry_dark&mode=time&length=30
```

## 참고

- Monkeytype에서 테마 목록을 자동으로 불러옵니다.
- GitHub는 성능을 위해 이미지를 캐시하므로 기록이 즉시 갱신되지 않을 수 있습니다. 보통 10~15분 안에 반영됩니다.
- 테마 이름의 공백은 밑줄로 바꿔야 합니다. 예: `modern dolch` → `modern_dolch`

## 크레딧

카드에 사용한 [Monocraft 폰트](https://github.com/IdreesInc/Monocraft)는 SIL OFL 1.1 라이선스로 제공됩니다.
