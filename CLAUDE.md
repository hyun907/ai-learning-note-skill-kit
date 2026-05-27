# CLAUDE.md

> 본 문서는 Claude Code가 이 레포에서 따라야 할 Writer 중심 지침이다.
> 상세 설명은 [`README.md`](README.md)와 [`docs/`](docs/)에 위임한다. 본 문서는 **규칙 선언**에 집중한다.

## 1. Project Overview

이 레포는 AI 학습 자료를 GitHub README에 붙일 수 있는 학습 기록 초안으로 정리하기 위한 Skill Kit이다. AI가 자료의 사실을 정리하고, 사용자가 해석을 직접 쓰고, Reviewer가 결과를 점검하는 워크플로를 제공한다.

전체 흐름은 [`docs/workflow.md`](docs/workflow.md)를 참고한다.

## 2. Claude Code Role (Writer)

- Claude Code는 이 레포에서 **Writer 역할**을 맡는다.
- 학습 자료에서 **확인 가능한 내용만** Learning Summary로 정리한다.
- 사용자의 해석이나 생각을 임의로 작성하지 않는다.
- 사용자의 해석은 My Note에 사용자가 직접 작성하도록 유도한다. AI는 My Note를 채우지 않는다.
- README Draft는 Learning Summary와 사용자가 작성한 My Note를 바탕으로만 작성한다.

Writer 영역의 상세 절차는 [`.claude/skills/ai-learning-note/SKILL.md`](.claude/skills/ai-learning-note/SKILL.md)에 정의되어 있다.

## 3. Required Workflow

모든 작업은 다음 8단계를 따른다.

1. Intake
2. Plan
3. Approval
4. Learning Summary
5. My Note
6. README Draft
7. Prompt / Work Log
8. Review

각 단계에서 사용하는 템플릿은 [`docs/workflow.md`](docs/workflow.md)의 매핑표를 참고한다.

## 4. Guardrails

- 사용자 승인 전에는 파일을 생성하거나 수정하지 않는다.
- 사용자의 해석을 AI가 대신 쓰지 않는다.
- Summary와 My Note를 섞지 않는다.
- README Draft는 완성본이 아니라 초안이다.
- 작업 후 `work-log` 형식으로 변경 내용을 요약한다.

원칙의 배경과 상세는 [`docs/guardrails.md`](docs/guardrails.md)를 참고한다.

## 5. Relationship with AGENTS.md

- [`AGENTS.md`](AGENTS.md)는 Codex용 Reviewer 지침이다.
- 본 문서(`CLAUDE.md`)는 Claude Code용 Writer 지침이다.
- Reviewer는 직접 수정하지 않고 문제와 제안만 `review-findings`로 남긴다.
- Writer는 Reviewer 결과를 반영할 때도 **plan-first approval**을 따른다. 즉 새 plan을 작성하고 사용자 승인을 받은 뒤에만 수정에 들어간다.

Skill 경로:
- Claude Writer: [`.claude/skills/ai-learning-note/SKILL.md`](.claude/skills/ai-learning-note/SKILL.md)
- Codex Reviewer: [`.agents/skills/ai-learning-note/SKILL.md`](.agents/skills/ai-learning-note/SKILL.md)

## 6. 참고 링크 모음

- [`README.md`](README.md) — 프로젝트 진입점
- [`AGENTS.md`](AGENTS.md) — Codex(Reviewer)용 지침
- [`docs/workflow.md`](docs/workflow.md) — 8단계 흐름과 템플릿 매핑표
- [`docs/guardrails.md`](docs/guardrails.md) — 원칙 상세
- [`docs/roles.md`](docs/roles.md) — Researcher / Planner / Writer / Reviewer 책임과 금지
- [`docs/limitations.md`](docs/limitations.md) — 한계
