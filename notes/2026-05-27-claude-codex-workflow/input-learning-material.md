# Input Learning Material

> 본 문서는 이번 테스트의 입력 학습 자료다.
> 이 레포의 실제 문서에서 **확인 가능한 사실만** 모았다. 외부 지식·추측은 포함하지 않는다.

## 메타
- 주제: Claude Code와 Codex Skills를 활용한 AI 학습 기록 워크플로우
- 출처(이 레포 내 문서)
  - `README.md`
  - `CLAUDE.md`
  - `AGENTS.md`
  - `docs/workflow.md`
  - `docs/guardrails.md`
  - `docs/roles.md`
  - `docs/limitations.md`
  - `.claude/skills/ai-learning-note/SKILL.md`
  - `.agents/skills/ai-learning-note/SKILL.md`
- 검토 시점: 2026-05-27

## 1. 이 워크플로우가 다루는 문제 (`README.md`)
- 본 Kit은 "AI가 만든 요약이 내 생각처럼 보이는 문제"를 막기 위해 만들어졌다.
- AI 요약만으로 학습 기록을 만들면 다음이 발생한다.
  - 사용자의 해석과 AI 출력이 섞여 구분이 어렵다.
  - AI 출력 그대로 README에 붙이면, 자료 사실과 사용자 해석이 같은 무게로 보인다.
  - 작업이 블랙박스라 같은 흐름을 다시 재현하기 어렵다.

## 2. 해결 방식 (`README.md`)
- plan-first approval gate: 모든 파일 생성·수정 전 plan과 사용자 승인.
- Summary와 My Note 분리: 자료 사실은 Summary, 사용자 해석은 My Note.
- Writer / Reviewer 분리: Claude는 Writer, Codex는 Reviewer.
- Prompt / Work Log: 모든 작업을 로그로 남겨 재현 가능하게 한다.

## 3. 8단계 워크플로우 (`docs/workflow.md`, `README.md`)
1. Intake — 사용자가 학습 자료(링크 또는 텍스트)와 정리 목적을 제시한다.
2. Plan — Writer(AI)는 `plan-template.md`로 작업 계획을 먼저 작성한다.
3. Approval — 사용자가 plan을 검토하고 명시적으로 승인한다.
4. Learning Summary — Writer가 자료에서 확인 가능한 사실만 `learning-summary-template.md`로 정리한다.
5. My Note — 사용자가 직접 `my-note-template.md`를 작성한다. AI는 채우지 않는다.
6. README Draft — Summary와 My Note를 결합해 `readme-draft-template.md`로 초안을 만든다.
7. Prompt / Work Log — 전 과정을 `prompt-log-template.md`와 `work-log-template.md`로 기록한다.
8. Review — Reviewer(Codex)가 결과물을 검토하고 `review-findings-template.md`로 문제만 남긴다.

## 4. Claude Skill과 Codex Skill의 역할 차이 (`README.md`)

| 항목 | Claude Skill (`.claude/skills/ai-learning-note/`) | Codex Skill (`.agents/skills/ai-learning-note/`) |
|---|---|---|
| 역할 | Writer | Reviewer |
| 주요 작업 | Summary, My Note 유도, README Draft 생성, 로그 작성 | 결과물 검토, review-findings 작성 |
| 직접 수정 | 승인된 plan 범위 내에서 가능 | 금지 |
| 산출물 | summary, draft, log | review-findings |

## 5. 역할별 책임과 금지 (`docs/roles.md`)
- Researcher — 자료 수집·출처 기록 / 자료에 없는 내용 만들지 않음, 해석 단정 금지.
- Planner — plan 작성, 작업 범위·리스크·필요한 사용자 입력 명시 / 승인 전 파일 생성·수정 금지.
- Writer — `learning-summary`, `readme-draft`, `prompt-log`, `work-log` 작성 / `my-note` 채우지 않음, `review-findings` 대신 작성 금지.
- Reviewer — `review-findings-template.md`로 문제·근거·영향도(High/Medium/Low)·수정 제안 남김 / 직접 파일 수정·추가·삭제 금지, Writer 작업 대신 수행 금지.

## 6. Guardrails (`docs/guardrails.md`)
1. plan-first approval gate — 명시적 승인("승인. 진행해줘." 류) 이후에만 작업.
2. AI 해석 금지 — 자료에서 확인 가능한 내용만 Summary에. "사용자가 이렇게 이해할 것이다" 류 단정 금지.
3. Summary와 My Note 분리 — 두 파일 경계가 흐려지면 README Draft 신뢰도가 무너진다.
4. Reviewer 직접 수정 금지 — 문제·근거·영향도·수정 제안만 남기고, 실제 수정은 Writer가 별도 승인 흐름에서 진행.
5. 로그로 재현성 확보 — 요청 → 계획 → 승인 → 결과물 흐름을 누락 없이 기록. 로그 없는 작업은 재현 불가로 간주.

## 7. Writer Skill 트리거 조건 (`.claude/skills/ai-learning-note/SKILL.md`)
- 사용자가 "이 자료를 정리해줘", "학습 기록 만들어줘", "README Draft 만들어줘" 같이 학습 정리·기록 요청을 할 때.
- 사용자가 본 Kit의 템플릿 경로를 직접 언급할 때.

## 8. 한계 (`docs/limitations.md`)
- 완전 자동화 도구가 아니다. plan 승인, My Note 작성, Review 결과 반영은 사람의 판단이 들어가야 한다.
- AI 결과는 반드시 사용자가 검토해야 한다.
- 해석은 사용자가 직접 작성해야 한다. My Note를 AI에게 떠넘기면 Kit의 목적이 무너진다.
- README Draft는 완성본이 아니라 초안이다.
- 공식 문서·최신 정보가 필요한 경우 별도 확인이 필요하다.
- `.agents/skills/` 경로가 모든 Codex 실행 환경에서 인식되는지는 사전 확인이 필요하다.
- 본 Kit은 한국어 기준이며, 외부 크롤링·API·CI 통합은 포함되지 않는다.
