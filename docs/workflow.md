# Workflow

AI Learning Note Skill Kit의 전체 흐름. 모든 작업은 아래 8단계를 따른다.

## 8단계 흐름

1. **Intake** — 사용자가 학습 자료(링크 또는 텍스트)와 정리 목적을 제시한다.
2. **Plan** — Writer(AI)는 `plan-template.md`로 작업 계획을 먼저 작성한다.
3. **Approval** — 사용자가 plan을 검토하고 명시적으로 승인한다. 승인 전까지 파일 생성·수정은 일어나지 않는다.
4. **Learning Summary** — Writer가 자료에서 확인 가능한 사실만 `learning-summary-template.md`로 정리한다.
5. **My Note** — 사용자가 직접 `my-note-template.md`를 작성한다. AI는 채우지 않는다.
6. **README Draft** — Summary와 My Note를 결합해 `readme-draft-template.md`로 초안을 만든다.
7. **Prompt / Work Log** — 전 과정을 `prompt-log-template.md`와 `work-log-template.md`로 기록한다.
8. **Review** — Reviewer(Codex)가 결과물을 검토하고 `review-findings-template.md`로 문제만 남긴다. 직접 수정하지 않는다.

## 단계별 템플릿 매핑표

| 단계 | 사용 템플릿 | 작성 주체 |
|------|--------------|----------|
| Plan | `plan-template.md` | Writer (AI) |
| Learning Summary | `learning-summary-template.md` | Writer (AI) |
| My Note | `my-note-template.md` | 사용자 |
| README Draft | `readme-draft-template.md` | Writer (AI, My Note 기반) |
| Prompt Log | `prompt-log-template.md` | Writer (AI) |
| Work Log | `work-log-template.md` | Writer (AI) |
| Review | `review-findings-template.md` | Reviewer (Codex) |

## 흐름의 핵심 원칙

- **plan-first**: 모든 작업은 plan과 사용자 승인 이후에만 시작한다.
- **AI 해석 금지**: AI는 자료 외 해석을 추가하지 않는다.
- **Reviewer 직접 수정 금지**: 리뷰어는 문제와 제안만 남긴다.

상세 원칙은 [`guardrails.md`](guardrails.md), 역할별 책임은 [`roles.md`](roles.md), 한계는 [`limitations.md`](limitations.md)를 참고한다.
