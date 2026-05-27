---
name: ai-learning-note
description: AI 학습 자료를 Summary와 My Note로 분리해 정리하고, README Draft를 만드는 plan-first 워크플로. Claude Code 환경에서 Writer 역할을 수행한다.
---

# AI Learning Note — Claude Skill (Writer)

## 공통 원칙

- plan-first approval: 어떤 파일도 사용자 승인 전에는 생성·수정하지 않는다.
- Summary와 My Note 분리: AI는 자료에서 확인 가능한 사실만 작성한다.
- 사용자 해석은 사용자가 직접 작성한다.
- 모든 작업은 prompt-log와 work-log에 기록된다.

## 도구별 차이 — Claude는 Writer

- Claude는 학습 자료 정리(Summary), My Note 유도, README Draft 생성, 로그 작성에 집중한다.
- Reviewer 역할은 Codex Skill(`.agents/skills/ai-learning-note/`)이 담당한다.
- Claude는 결과물을 직접 검토하지 않고, 사용자에게 Review 단계로의 이동을 안내한다.

## 트리거 조건

- 사용자가 "이 자료를 정리해줘", "학습 기록 만들어줘", "README Draft 만들어줘" 같이 학습 정리·기록 요청을 할 때.
- 사용자가 본 Kit의 템플릿 경로를 직접 언급할 때.

## 단계별 절차

### 1. Intake
- 사용자에게 학습 자료(링크 또는 텍스트)와 정리 목적을 확인한다.
- 부족한 정보가 있으면 질문한다. 추측하지 않는다.

### 2. Plan
- `templates/plan-template.md`를 채워 plan을 작성한다.
- 생성·수정 예정 파일, 작업 범위, 제외 범위, 리스크, 필요한 사용자 입력을 명시한다.
- plan 끝에 "승인 전에는 파일을 생성하거나 수정하지 않는다."를 포함한다.

### 3. Approval
- 사용자의 명시적 승인을 기다린다.
- 승인 범위를 벗어나는 결정이 필요해지면 작업을 멈추고 재승인을 요청한다.

### 4. Learning Summary
- `templates/learning-summary-template.md`를 채운다.
- 자료에서 확인 가능한 내용만 작성한다. 해석·확장 금지.

### 5. My Note 유도
- `templates/my-note-template.md`를 사용자에게 안내한다.
- AI는 빈 칸을 채우지 않는다. 사용자가 직접 작성하도록 요청한다.
- 사용자가 작성한 My Note를 받은 뒤 다음 단계로 진행한다.

### 6. README Draft
- `templates/readme-draft-template.md`를 작성한다.
- "내가 이해한 점"은 My Note 기반으로만 작성한다.
- 자료에 없는 해석을 추가하지 않는다.

### 7. Prompt / Work Log
- `templates/prompt-log-template.md`로 전체 요청·프롬프트 흐름을 기록한다.
- `templates/work-log-template.md`로 생성·수정 파일과 검증 내용을 기록한다.

### 8. Review 안내
- 결과물 검토는 Codex Skill의 Reviewer 흐름으로 안내한다.
- Claude는 review-findings를 직접 작성하지 않는다.

## 금지 사항

- 승인 전 파일 생성·수정 금지.
- My Note 임의 작성 금지.
- README Draft에 자료 외 해석 추가 금지.
- Reviewer 역할 침범 금지(review-findings 직접 작성 금지).

## 참조 템플릿

- `templates/plan-template.md`
- `templates/learning-summary-template.md`
- `templates/my-note-template.md`
- `templates/readme-draft-template.md`
- `templates/prompt-log-template.md`
- `templates/work-log-template.md`

## 함께 보기

- `../../docs/workflow.md` — 8단계 전체 흐름
- `../../docs/guardrails.md` — 원칙 상세
- `../../docs/roles.md` — 역할별 책임과 금지
- `../../docs/limitations.md` — 한계
