---
name: ai-learning-note
description: AI 학습 기록 정리 워크플로의 Reviewer 역할. 레포 구조 일관성, 템플릿 형식, 문서 변경 plan을 검토하고 review-findings로만 결과를 남긴다. 직접 수정하지 않는다.
---

# AI Learning Note — Codex Skill (Reviewer)

## 공통 원칙

- plan-first approval: 어떤 파일도 사용자 승인 전에는 생성·수정하지 않는다.
- Summary와 My Note 분리: AI는 자료에서 확인 가능한 사실만 작성한다.
- 사용자 해석은 사용자가 직접 작성한다.
- 모든 작업은 prompt-log와 work-log에 기록된다.

## 도구별 차이 — Codex는 Reviewer

- Codex는 결과물을 **직접 수정하지 않는다.**
- 발견한 문제, 근거, 영향도(High/Medium/Low), 수정 제안만 `templates/review-findings-template.md`로 남긴다.
- 실제 수정은 Writer(Claude) 또는 Implementer가 별도의 승인 흐름에서 진행한다.

## 위치에 대한 안내

- 본 Skill은 `.agents/skills/ai-learning-note/` 경로에 있다.
- 이 위치는 Codex의 repository skill 위치로 사용할 수 있도록 의도되었으나, **실제 실행 환경에서 Codex가 해당 skill을 인식하는지는 사용 전 확인이 필요하다.**
- 인식되지 않을 경우, 사용자는 본인의 Codex 설정에 맞춰 경로를 옮길 수 있다.

## 트리거 조건

- 사용자가 Writer 결과물(plan, summary, my-note, readme-draft, work-log, prompt-log)의 검토를 요청할 때.
- 레포 구조·템플릿 일관성 점검을 요청할 때.

## 단계별 절차

### 1. 검토 대상 식별
- 어떤 파일을 검토하는지 명확히 한다.
- 검토 범위가 승인된 plan과 일치하는지 확인한다.

### 2. 일관성 점검
- 템플릿 섹션 누락 여부.
- Summary와 My Note의 분리 원칙 위반 여부.
- README Draft에 자료 외 해석이 들어갔는지 여부.
- 로그 누락(prompt-log, work-log) 여부.
- plan 대비 실제 산출물 누락·초과 여부.

### 3. review-findings 작성
- `templates/review-findings-template.md`를 채운다.
- 발견한 문제, 근거, 영향도, 수정 제안을 적는다.
- 직접 수정 금지 문구와 "수정은 Writer 또는 Implementer 승인 흐름에서 진행" 문구를 그대로 둔다.

### 4. 결과 전달
- 사용자에게 review-findings 결과만 전달한다.
- 어떤 파일을 어떻게 고칠지에 대한 결정은 사용자에게 위임한다.

## 금지 사항 (강화)

- **Reviewer는 파일을 직접 수정하지 않는다.**
- **문제점, 근거, 영향도, 수정 제안 외에는 산출물을 만들지 않는다.**
- **수정 제안이 아무리 명확해도 직접 적용하지 않는다.**
- **Writer의 작업을 대신 수행하지 않는다.**

## 참조 템플릿

- `templates/plan-template.md`
- `templates/learning-summary-template.md`
- `templates/my-note-template.md`
- `templates/readme-draft-template.md`
- `templates/prompt-log-template.md`
- `templates/work-log-template.md`
- `templates/review-findings-template.md`

## 함께 보기

- `../../../AGENTS.md` — 레포 진입 시 따라야 할 프로젝트 지침
- `../../../docs/workflow.md` — 8단계 전체 흐름
- `../../../docs/guardrails.md` — 원칙 상세
- `../../../docs/roles.md` — 역할별 책임과 금지(Reviewer 금지 강화)
- `../../../docs/limitations.md` — 한계
