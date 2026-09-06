---
title: "공마고의 도둑들"
date: 2025-01-05
description: "공주마이스터고등학교에서 제작해 1등을 수상한 공용 냉장고 음식 도난 방지 시스템"
tags: ["IoT", "AWS", "JavaScript", "C"]
architecture: "/images/projects/gmst-architecture.svg"
architectureAlt: "공마고의 도둑들 시스템 구성도. 장치와 사용자, AWS Cloud의 S3 및 VPC 내부 Private subnet의 EC2, 웹 클라이언트를 표시합니다."
school: "공주마이스터고등학교"
award: "금상 (1위)"
awardTitle: "프로젝트 발표대회"
awardDate: "2026.01.05."
awardIssuer: "공주마이스터고등학교장"
awardTeam: "공동수상 · 4인"
awardScope: "1학년 66명"
---

## 공용 냉장고에서 시작된 질문
공주마이스터고등학교에서 진행한 프로젝트입니다. 공용 냉장고의 음식이 자꾸 사라지는 문제를 해결하기 위해 스마트 보안 시스템을 제작했고, 교내 프로젝트에서 1등을 수상했습니다.

## 동작 흐름
1. 아두이노 UNO가 초음파 센서로 냉장고 문 열림을 감지합니다.
2. 문이 일정 시간 이상 열려 있으면 UNO가 ESP32-CAM에 촬영 신호를 보냅니다.
3. ESP32-CAM이 사진을 촬영해 업로드 서버로 전송합니다.
4. 서버가 사진을 AWS S3에 저장하고, 성공 여부를 ESP32-CAM과 UNO에 전달합니다.
5. 문이 오래 열려 있으면 UNO가 RGB LED와 부저로 경고합니다.

## 구현 포인트
- 문 상태는 초음파 측정값을 여러 번 샘플링해 안정적으로 판정합니다.
- ESP32-CAM과 UNO 사이에 READY, TRIGGER, COMPLETE 신호를 두어 촬영 상태를 동기화합니다.
- 한 번의 문 열림에 최대 4회 촬영하고, 업로드 성공과 실패를 서로 다른 펄스로 구분합니다.
- Terraform으로 VPC, S3, Lambda, API Gateway 인프라를 코드로 관리했습니다.

## 사용 기술
- **하드웨어:** ESP32, 아두이노 UNO
- **클라우드:** AWS (EC2, S3)
- **웹:** Vercel (JavaScript)
- **언어:** C
