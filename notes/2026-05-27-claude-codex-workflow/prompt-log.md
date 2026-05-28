# Prompt Log

> 작업의 재현성을 위해 사용자 요청과 프롬프트 흐름을 기록한다.

## 메타
- 작업 날짜: 2026-05-27
- 작업 ID/주제: 2026-05-27-claude-codex-workflow — AI Learning Note Skill Kit 실제 워크플로우 테스트
- 작성자: Claude Code (Writer)

## 사용자 요청
> 이제 AI Learning Note Skill Kit을 실제로 한 번 테스트하고 싶다.
>
> 목표: 현재 레포의 Claude Writer 워크플로우를 사용해서 짧은 AI 학습 자료 하나를 학습 기록으로 정리하는 테스트를 진행한다.
>
> 테스트 주제: Claude Code와 Codex Skills를 활용한 AI 학습 기록 워크플로우
>
> 중요: plan-first approval을 지켜라. 바로 파일을 생성하거나 수정하지 말고, 먼저 테스트 실행 plan만 작성해라.
>
> 테스트 산출물은 실제 notes 디렉터리 아래에 만들고 싶다. 권장 경로: `notes/2026-05-27-claude-codex-workflow/`.
>
> 생성하고 싶은 파일: `input-learning-material.md`, `plan.md`, `learning-summary.md`, `my-note.md`, `readme-draft.md`, `prompt-log.md`, `work-log.md`.
>
> 주의: `my-note.md`는 AI가 채우지 말고 빈 템플릿으로만. `readme-draft.md`는 `my-note.md` 작성 이후 별도 승인 후 생성. 승인 전에는 어떤 파일도 생성·수정 금지.

후속 1차 승인 메시지(요약):
> plan 좋다. 1차 승인한다. 단, `my-note.md`는 기존 템플릿 구조 그대로 사용. My Note 항목은 5개로 고정 (이 자료를 읽은 이유 / 내가 이해한 핵심 / 내 학습이나 프로젝트에 연결할 점 / 아직 헷갈리는 점 / 다음 액션). `readme-draft.md`는 아직 생성 금지. 기존 `README.md`, `CLAUDE.md`, `AGENTS.md`, `docs/*`, `templates/*` 수정 금지.

## 사용 도구
- Claude Code (CLI)
- 파일 작성용 내부 도구 (Read / Write / Bash)
- Task 추적 도구 (TaskCreate / TaskUpdate)

## 적용 Skill
- `.claude/skills/ai-learning-note/SKILL.md` (Writer)

## 계획 요약
- 8단계 워크플로우 중 1차 승인 범위: 6개 파일 생성 (`input-learning-material.md`, `plan.md`, `learning-summary.md`, `my-note.md` 빈 템플릿, `prompt-log.md`, `work-log.md`).
- 2차 승인 범위: 사용자가 `my-note.md`를 채운 뒤 별도 plan 승인을 거쳐 `readme-draft.md` 작성.
- 가드레일: 승인 전 파일 생성·수정 금지, `my-note.md`는 AI가 답변 칸 채우지 않음, 기존 레포 문서는 수정하지 않음.

## 승인 여부
- 사용자 승인: 예 (1차 승인)
- 승인 시각: 2026-05-27 (사용자 메시지 기준)
- 승인된 plan 버전: `notes/2026-05-27-claude-codex-workflow/plan.md`
- 승인 범위: 위 6개 파일 생성까지. `readme-draft.md`는 2차 승인 필요.

## 주요 프롬프트 흐름
1. 사용자 — 워크플로우 테스트 요청과 함께 plan 항목(목적/Skill/생성·수정 파일/순서/My Note 지점/리스크/승인) 8가지를 명시. README Draft는 별도 승인.
2. AI(Writer) — `ai-learning-note` Skill 트리거 후 plan-template 기반 plan을 텍스트로 제시. 파일은 만들지 않음.
3. 사용자 — 1차 승인. `my-note.md` 항목 5개 고정 조건 추가. 기존 레포 문서는 수정 금지 재확인.
4. AI(Writer) — 1차 승인 범위 6개 파일 생성. `my-note.md`는 `my-note-template.md` 원문 그대로 (답변 칸 빈 줄).
5. 사용자 — `my-note.md` 5개 항목 직접 작성 완료.
6. 사용자 — README Draft 생성을 위한 2차 plan 작성 요청.
7. AI(Writer) — 2차 plan v1 텍스트로 제시 (입력 파일 3개 / 생성 예정 파일 / 수정 예정 파일 / 작성 원칙 / 리스크 / 승인 요청 포함).
8. 사용자 — 2차 plan 수정 요청. ① `readme-draft-template.md` 8개 섹션 구조 사용, ② My Note 반영 원칙 수정(의미 추가 금지, 표현 가벼운 정리 허용). 파일 생성 금지 유지.
9. AI(Writer) — 2차 plan v2 텍스트로 제시. 템플릿 8개 섹션 고정, 섹션별 입력 출처 매핑표 추가.
10. 사용자 — 2차 승인. 5가지 조건(섹션 구조 고정 / My Note 기반 4개 섹션 엄수 / Summary 기반 핵심 내용 분리 / 한 줄 기록 원칙 / 작업 범위 3개 파일만) 명시.
11. AI(Writer) — `readme-draft.md` 생성, `prompt-log.md`·`work-log.md` 갱신.

## 결과물
- 생성 파일:
  - `notes/2026-05-27-claude-codex-workflow/input-learning-material.md`
  - `notes/2026-05-27-claude-codex-workflow/plan.md`
  - `notes/2026-05-27-claude-codex-workflow/learning-summary.md`
  - `notes/2026-05-27-claude-codex-workflow/my-note.md` (사용자 직접 작성 완료)
  - `notes/2026-05-27-claude-codex-workflow/prompt-log.md`
  - `notes/2026-05-27-claude-codex-workflow/work-log.md`
  - `notes/2026-05-27-claude-codex-workflow/readme-draft.md` (2차 승인 후 생성)
- 수정 파일:
  - `notes/2026-05-27-claude-codex-workflow/prompt-log.md` (2차 승인 내용 추가)
  - `notes/2026-05-27-claude-codex-workflow/work-log.md` (readme-draft.md 생성 결과 추가)

## 확인 필요 사항
- `readme-draft.md`가 `readme-draft-template.md` 8개 섹션 구조를 그대로 따르는지 확인.
- My Note 기반 4개 섹션("내가 이해한 점", "내 학습이나 프로젝트에 연결할 점", "아직 더 공부할 점", "다음 액션")에 Summary 내용이 섞이지 않았는지 확인.
- "한 줄 기록"이 `my-note.md`에 있는 문장에서 선택되었는지 확인.
- Reviewer(Codex) 흐름은 본 테스트 이후 별도 진행.
