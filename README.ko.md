<div align="center">

# 🧠 Trading Second Brain

### 차트, 거래, 실수, PDF, 슬라이드, 손글씨 메모를 다시 사용할 수 있는 트레이딩 기억으로.

트레이더를 위한 멀티모달 AI 지식 시스템.

[English](./README.md) · [简体中文](./README.zh-CN.md) · [日本語](./README.ja.md) · **한국어**

**Fork하고 거래 기록을 쌓아, 과거의 거래가 다음 의사결정에 참여하게 하세요.**

</div>

---

## 왜 만들었나요?

대부분의 트레이더에게는 이미 '두 번째 뇌'가 있습니다. 다만 모든 정보가 흩어져 있습니다.

TradingView 스크린샷은 사진 폴더에, 체결 기록은 브로커 CSV에, 리서치는 PDF에, 아이디어는 Notion·SNS 북마크·PowerPoint·손글씨 노트에 남아 있습니다. 매일 복기를 해도 다음 거래에서 다시 찾아보는 경우는 드뭅니다.

**Trading Second Brain은 이 자료들을 AI Agent가 검색하고, 비교하고, 업데이트할 수 있는 구조화된 트레이딩 메모리로 바꿉니다.**

> 더 많은 정보를 저장하는 것이 목적이 아닙니다.  
> 필요한 순간에 과거의 정보를 다시 사용할 수 있게 만드는 것이 목적입니다.

---

## 일반 트레이딩 저널과의 차이

| 일반 저널 | Trading Second Brain |
|---|---|
| 오늘 있었던 일을 기록 | 오늘의 경험을 미래 의사결정에 연결 |
| 주로 텍스트 | 텍스트 + 이미지 + PDF + PPT + 손글씨 + CSV |
| 하루 단위 복기 | 여러 거래에 걸친 패턴 탐지 |
| 노트가 반복 생성됨 | 기존 주제 파일을 우선 업데이트 |
| 규칙을 만든 이유를 잊기 쉬움 | Decision Log에 이유와 근거 보존 |
| AI가 현재 질문만 봄 | AI가 과거 거래 기록을 검색 가능 |

---

## 핵심 루프

```text
스크린샷 / PDF / PPT / 손글씨 / CSV / 메모
                     ↓
                   inbox/
                     ↓
                   AI 인식
                     ↓
             추출 / 분류 / 검증
                     ↓
 knowledge / strategies / journal / trades
                     ↓
                LEARNINGS.md
                     ↓
                decisions.md
                     ↓
                  MEMORY.md
                     ↓
                   AI Agent
                     ↓
                 다음 거래일
```

**모든 거래가 다음 거래를 더 똑똑하게 만들어야 합니다.**

---

## 멀티모달을 기본으로 설계

다음 자료를 시스템에 넣을 수 있습니다.

- 📈 TradingView / 브로커 스크린샷
- 🧱 GEX, Dealer Gamma, Option Wall 차트
- 📄 PDF 논문과 리서치 보고서
- 🖥️ PowerPoint / 슬라이드
- ✍️ 휴대폰으로 촬영한 손글씨 노트
- 📊 거래 CSV
- 📝 일일 복기와 전략 노트

Agent는 **먼저 보이는 사실을 추출하고 그 다음 해석**합니다. 원본을 보존하고 기존 지식과 비교한 뒤 적절한 장기 파일에 정리합니다.

---

## Repository 구조

```text
trading-second-brain/
├── CLAUDE.md       # AI Agent 운영 규칙
├── MEMORY.md       # 장기 컨텍스트와 하드 룰
├── LEARNINGS.md    # 반복 증거로 확인된 학습
├── decisions.md    # 규칙을 바꾼 이유
├── knowledge/      # 시장 지식
├── strategies/     # 실행 가능한 전략
├── journal/        # 일일 거래 복기
├── trades/         # 구조화된 거래 기록
├── screenshots/    # 차트 및 체결 이미지
├── research/       # PDF / PPT 원본
├── inbox/          # 아직 처리하지 않은 자료
├── templates/      # 복사해서 쓰는 템플릿
└── prompts/        # AI 워크플로우
```

---

## 5분 Quick Start

1. 이 Repository를 Fork합니다.
2. `MEMORY.md`에 주요 시장, 거래 스타일, 최대 손실, 반복되는 행동 약점 등 장기적으로 유지되는 정보만 작성합니다.
3. 이미지, PDF, PPT, 손글씨 사진, CSV를 `inbox/`에 넣습니다.
4. 멀티모달 Agent로 `prompts/inbox-triage.md`를 실행합니다.
5. 장 마감 후 `prompts/daily-review.md`, 주말에는 `prompts/weekly-review.md`를 실행합니다.

---

## One Topic = One Maintainable File

`notes-final-v2.md` 같은 파일을 계속 만드는 대신 독립적으로 이해하고 관리할 수 있는 지식 단위로 나눕니다.

```text
knowledge/
├── dealer-gamma.md
├── gamma-flip.md
├── put-wall.md
├── call-wall.md
├── vwap.md
└── 0dte-gamma.md
```

---

## 모든 정보가 바로 Memory가 되지는 않습니다

```text
raw source
   ↓
journal / knowledge
   ↓
repeated evidence
   ↓
LEARNINGS.md
   ↓
decisions.md
   ↓
MEMORY.md
```

한 번의 손실이나 감정적인 거래가 영구적인 규칙으로 굳어지는 것을 막기 위한 구조입니다.

---

## 가장 중요한 네 파일

**`CLAUDE.md`** — Agent가 무엇을 먼저 읽고 어디를 검색하며 이미지·문서를 어떻게 처리해야 하는지 정의합니다.

**`MEMORY.md`** — 시장, 스타일, 리스크 한도, 반복되는 행동 패턴과 장기 규칙을 저장합니다.

**`LEARNINGS.md`** — 여러 거래의 증거로 지지되지만 미래의 증거에 따라 수정될 수 있는 학습입니다.

**`decisions.md`** — 규칙이 왜 만들어지거나 변경되었는지를 근거와 함께 기록합니다.

---

## 준비된 AI Prompt

| Prompt | 역할 |
|---|---|
| `inbox-triage.md` | 멀티모달 자료 자동 분류 |
| `screenshot-analysis.md` | 차트 이미지 분석 |
| `research-extraction.md` | PDF / PPT 지식 추출 |
| `handwritten-notes.md` | 손글씨 인식 및 분류 |
| `daily-review.md` | 일일 거래 복기 |
| `weekly-review.md` | 주간 패턴 분석 |

---

## 데이터가 쌓이면 이런 질문을 할 수 있습니다

- 하루 중 어느 시간대에서 가장 많이 잃는가?
- 두 번 연속 수익 후 다음 거래의 성과는 어떤가?
- Positive Gamma와 Negative Gamma에서 어떤 전략이 가장 잘 작동하는가?
- 같은 손절 규칙을 위반한 거래를 모두 찾아줘.
- 손실 거래 스크린샷에서 반복되는 Price Action이 있는가?
- 이 규칙은 언제 처음 만들어졌고 왜 만들어졌는가?

---

## Public Repo와 Private Brain 분리

```text
Public Repo  = OS / Template / Prompt
Private Repo = 실제 Trading Brain
```

계좌번호, API Key, Broker Statement, 비공개 PnL과 민감한 거래 데이터는 Public Repo에 커밋하지 마세요.

---

## Disclaimer

이 프로젝트는 트레이딩 지식 관리 프레임워크입니다. 투자 조언, 금융 조언 또는 자동 거래 추천 시스템이 아닙니다. 시장 거래에는 큰 위험이 있습니다.

<div align="center">

**스크린샷도 데이터입니다. 실수도 데이터입니다. 규칙도 데이터입니다.**

**검색 가능하게 만들고, 다시 사용할 수 있게 만드세요.**

</div>
