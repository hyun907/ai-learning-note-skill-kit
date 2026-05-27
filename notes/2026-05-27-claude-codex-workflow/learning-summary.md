# Learning Summary

> 이 문서는 학습 자료에서 **확인 가능한 내용만** 정리한다.
> 사용자의 실제 해석처럼 단정하지 않는다. 해석은 `my-note-template.md`에 사용자가 직접 작성한다.

## 자료 정보
- 제목: Claude Code와 Codex Skills를 활용한 AI 학습 기록 워크플로우
- 출처(URL 또는 경로): `notes/2026-05-27-claude-codex-workflow/input-learning-material.md` (소스: 본 레포의 `README.md`, `CLAUDE.md`, `AGENTS.md`, `docs/workflow.md`, `docs/guardrails.md`, `docs/roles.md`, `docs/limitations.md`, `.claude/skills/ai-learning-note/SKILL.md`, `.agents/skills/ai-learning-note/SKILL.md`)
- 작성일/수정일: 자료마다 상이 (이 레포 내부 문서, 본 테스트 시점 기준)
- 검토 시점: 2026-05-27

## 1. 핵심 주장
- "AI가 만든 요약이 내 생각처럼 보이는 문제"를 막기 위한 Kit이다. (`README.md`)
- AI는 자료에서 확인 가능한 사실만 Summary로 정리하고, 사용자는 자기 해석을 My Note에 직접 작성하며, 결과물 리뷰는 Codex Skill이 Reviewer 역할로 담당한다. (`README.md`)
- "모든 작업은 plan과 사용자 승인을 거친다." (`README.md`)
- "Reviewer는 직접 파일을 고치지 않는다." (`docs/roles.md`)
- "로그가 없는 작업은 재현 불가로 간주한다." (`docs/guardrails.md`)

## 2. 중요한 변화
- 자료 정리(Summary)와 해석(My Note)을 **도구·파일 단위로 분리**한다. (`README.md` "핵심 문제" 섹션)
- Writer와 Reviewer를 **다른 도구(Claude / Codex)에 분리 배정**한다. (`README.md` 역할 차이 표)
- 작업 흐름을 8단계로 고정하고, 각 단계에 사용할 템플릿을 매핑표로 명시한다. (`docs/workflow.md`)

## 3. 주요 개념
- **plan-first approval gate** — 모든 파일 생성·수정 전 plan을 먼저 작성하고, 사용자의 명시적 승인 이후에만 작업을 시작한다. (`docs/guardrails.md`)
- **Summary와 My Note 분리** — `learning-summary-template.md`는 자료에서 확인 가능한 사실만, `my-note-template.md`는 사용자가 직접 작성한 해석만 담는다. (`docs/guardrails.md`)
- **Writer / Reviewer 분리** — Claude Skill은 Writer, Codex Skill은 Reviewer. Reviewer는 `review-findings-template.md`로 문제·근거·영향도·수정 제안만 남긴다. (`README.md`, `docs/roles.md`)
- **Prompt Log / Work Log** — `prompt-log-template.md`는 요청·프롬프트 흐름을, `work-log-template.md`는 실제 수행 결과를 기록한다. (`docs/workflow.md` 매핑표)
- **8단계 워크플로우** — Intake → Plan → Approval → Learning Summary → My Note → README Draft → Prompt/Work Log → Review. (`docs/workflow.md`)

## 4. 적용 아이디어 후보
- `examples/` 폴더에 가상 자료로 전체 흐름을 한 번 돌린 결과가 시연되어 있다. (`README.md` "사용 예시" 섹션)
- "실제 학습 노트 레포에 본 Kit을 적용해 첫 사례 운영"이 Next Steps에 명시되어 있다. (`README.md`)
- "Codex Skill의 인식 경로를 실제 실행 환경에서 확인"이 Next Steps에 명시되어 있다. (`README.md`)
- "Writer / Reviewer 사이의 수정 권한 경계 가이드 보강"이 Next Steps에 명시되어 있다. (`README.md`)

## 5. 생각해볼 질문
- 본 Kit의 8단계 중 어떤 단계가 실제로 가장 자주 생략되기 쉬운가? (자료에 답은 없음)
- Writer가 Reviewer 결과를 반영할 때, 어느 시점부터 새 plan을 다시 작성해야 하는가? (`CLAUDE.md`는 "plan-first approval"을 명시하지만 구체적 기준은 자료에 없음)
- `.agents/skills/` 경로가 인식되지 않는 Codex 환경에서는 어떤 대안 경로를 선택해야 하는가? (`AGENTS.md`, `docs/limitations.md`에 "사용자가 자신의 Codex 설정에 맞춰 경로를 옮길 수 있다"고만 명시)
- 한국어 외 언어로 본 Kit을 쓸 때, 템플릿 번역 외에 추가로 검토할 가드레일이 있는가? (`docs/limitations.md`에 한국어 기준 설계임만 명시)
