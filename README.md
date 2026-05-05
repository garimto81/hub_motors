# Hub Motors — Wheel-On

휠복원·판금 공장(2~3인 매장)의 1인 병목을 해체하는 B2B AI-SaaS 플랫폼.

## 한 줄 미션

> 휠 도장 부스에서 페인터가 장갑 낀 손으로도 견적·예약·재고·고객 응대를 손바닥 안에 가둔다.

## 현재 상태

- **Phase**: PRD v2.0 DRAFT
- **다음 산출물**: Phase 1 화면 와이어프레임 + API 계약 + M1 Atomic Tasks
- **MVP 출시 목표**: 2개월 (베타 매장 10곳)
- **GA 매장 수 목표**: M6 시점 200곳

## 프로젝트 구조

```
hub_motors/
├── docs/
│   ├── 00-prd/
│   │   └── wheel-on.prd.md    # PRD v2.0 (1,690줄)
│   └── gemini.md              # 원본 기획안 (참조용)
├── apps/                      # (예정) mobile / web / api
├── packages/                  # (예정) core / ai / ui / config
└── README.md
```

## 핵심 결정

| 영역 | 채택 | 이유 |
|------|------|------|
| 모바일 | React Native + Expo | OTA 업데이트 + 웹과 코드 공유 |
| 백엔드 | Vercel Functions (icn1) | 한국 리전 + Fluid Compute |
| DB | Neon Postgres | branching + RLS |
| AI | Vercel AI Gateway | OpenAI ↔ Gemini 폴백 |
| 음성 | OpenAI Realtime + VITO | 한국어 native + 분당 350원 |
| 알림 | 카카오 알림톡 (SOLAPI) | 정보성 발송 한정 |
| 결제 | 토스페이먼츠 빌링키 + PopBill | 정기과금 + 세금계산서 자동 |

## 핵심 기능 (Phase 1)

1. 디지털 작업 카드 + 칸반 보드
2. 카카오 알림톡 정보성 자동 발송
3. Before/After 사진 갤러리
4. 토스 빌링 + PopBill 세금계산서

## 핵심 기능 (Phase 2~3)

5. AI 손상 라벨링 + 표준 공임 추천
6. 자재 재고 + 가격비교 (네이버 쇼핑 API)
7. AI 통화 자동 응대 (OpenAI Realtime)
8. 쇼츠 자동 편집 (FFmpeg + GPT-4o)

## 비용 모델 (검증)

| 항목 | 매장당 월 |
|------|:--------:|
| SaaS 정액 매출 | 99,000원 |
| 변동비 | 32,400원 |
| **매장당 마진** | **86,600원 (67%)** |

Break-even ≈ 매장 800곳.

## 문서

- [PRD v2.0](./docs/00-prd/wheel-on.prd.md) — 1,690줄, 16개 챕터
- [원본 기획안](./docs/gemini.md) — gemini.md (참조용)

## 라이센스

Private.
