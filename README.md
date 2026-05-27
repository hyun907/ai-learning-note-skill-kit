# AI Learning Note Skill Kit

> Claude Code와 Codex에서 함께 사용할 수 있는, AI 학습 기록 정리용 Skill Kit.
> 자료는 AI가 정리하고, 해석은 사용자가 직접 쓰고, 리뷰는 Codex가 담당한다. 모든 작업은 plan과 사용자 승인을 거친다.

## 소개

이 Kit은 AI 관련 학습 자료를 다룰 때 흔히 발생하는 문제 — "AI가 만든 요약이 내 생각처럼 보이는 문제"를 막기 위해 만들어졌다.

- AI는 자료에서 **확인 가능한 사실**만 Summary로 정리한다.
- 사용자는 자기 해석을 **My Note에 직접** 작성한다.
- 두 산출물을 합쳐 GitHub README에 붙일 수 있는 **README Draft**를 만든다.
- 모든 작업은 plan과 사용자 승인을 거친다.
- 결과물 리뷰는 **Codex Skill이 Reviewer 역할**로 담당한다. 직접 수정하지 않는다.

## 왜 만들었는가

AI 요약만으로 학습 기록을 만들면 다음 문제가 생긴다.

- 사용자의 해석과 AI의 출력이 섞여 무엇이 자기 생각이고 무엇이 AI 생성인지 구분이 어렵다.
- AI 출력 그대로 README에 붙이면, 자료의 사실과 사용자의 해석이 같은 무게로 보인다.
- 작업이 블랙박스라 같은 흐름을 다시 재현하기 어렵다.

## 핵심 문제

- AI는 사용자의 해석을 임의로 만들어내면 안 된다.
- 그러나 정리·요약·정형화는 AI가 잘하는 영역이다.
- 두 가지를 모두 살리려면 **작성 영역과 해석 영역을 도구·파일 단위로 분리**해야 한다.

## 해결 방식

- **plan-first approval gate**: 모든 파일 생성·수정 전 plan과 사용자 승인.
- **Summary와 My Note 분리**: 자료 사실은 Summary, 사용자 해석은 My Note.
- **Writer / Reviewer 분리**: Claude는 Writer, Codex는 Reviewer.
- **Prompt / Work Log**: 모든 작업을 로그로 남겨 재현 가능하게 한다.

## Claude Skill과 Codex Skill의 역할 차이

| 항목 | Claude Skill (`.claude/skills/ai-learning-note/`) | Codex Skill (`.agents/skills/ai-learning-note/`) |
|---|---|---|
| 역할 | Writer | Reviewer |
| 주요 작업 | Summary, My Note 유도, README Draft 생성, 로그 작성 | 결과물 검토, review-findings 작성 |
| 직접 수정 | 승인된 plan 범위 내에서 가능 | **금지** |
| 산출물 | summary, draft, log | review-findings |
| 공통 원칙 | plan-first / 해석 금지 / Summary와 My Note 분리 / 로그 기록 |

## 사용 흐름

1. **Intake** — 학습 자료와 목적 공유
2. **Plan** — Writer가 plan 작성
3. **Approval** — 사용자 명시적 승인
4. **Learning Summary** — Writer가 자료에서 확인 가능한 내용만 정리
5. **My Note** — 사용자가 직접 작성
6. **README Draft** — Summary와 My Note 결합
7. **Prompt / Work Log** — 전 과정 기록
8. **Review** — Codex Reviewer가 review-findings 작성

상세 흐름은 [`docs/workflow.md`](docs/workflow.md) 참고.

## 폴더 구조

```
.
├── README.md
├── AGENTS.md
├── .claude/
│   └── skills/
│       └── ai-learning-note/
│           ├── SKILL.md
│           └── templates/
│               ├── plan-template.md
│               ├── learning-summary-template.md
│               ├── my-note-template.md
│               ├── readme-draft-template.md
│               ├── prompt-log-template.md
│               └── work-log-template.md
├── .agents/
│   └── skills/
│       └── ai-learning-note/
│           ├── SKILL.md
│           └── templates/
│               ├── plan-template.md
│               ├── learning-summary-template.md
│               ├── my-note-template.md
│               ├── readme-draft-template.md
│               ├── prompt-log-template.md
│               ├── work-log-template.md
│               └── review-findings-template.md
├── examples/
│   ├── input-learning-material.md
│   ├── example-plan.md
│   ├── example-learning-summary.md
│   ├── example-my-note.md
│   ├── example-readme-draft.md
│   ├── example-work-log.md
│   ├── example-review-findings.md
│   └── example-prompt-log.md
└── docs/
    ├── workflow.md
    ├── guardrails.md
    ├── roles.md
    └── limitations.md
```

## 사용 예시

`examples/` 폴더는 본 Kit의 전체 흐름을 한 번 돌린 결과를 가상 자료로 시연한 것이다.

- `examples/input-learning-material.md` — 가상 학습 자료
- `examples/example-plan.md` — plan 작성 예시
- `examples/example-learning-summary.md` — Summary 예시
- `examples/example-my-note.md` — 사용자가 직접 작성한 것으로 가정한 My Note 예시
- `examples/example-readme-draft.md` — README Draft 초안 예시
- `examples/example-work-log.md` — Work Log 예시
- `examples/example-review-findings.md` — Codex Reviewer의 review-findings 예시
- `examples/example-prompt-log.md` — Prompt Log 예시

## Guardrails

- plan-first approval: 어떤 파일도 사용자 승인 전에는 만들지 않는다.
- AI는 사용자의 해석을 임의로 작성하지 않는다.
- Summary와 My Note는 분리한다.
- Reviewer는 직접 수정하지 않는다.
- 모든 작업은 prompt-log / work-log에 기록한다.

상세 원칙은 [`docs/guardrails.md`](docs/guardrails.md) 참고.

## Limitations

- 완전 자동화 도구가 아니다.
- AI 결과는 반드시 사람이 검토해야 한다.
- 해석은 사용자가 직접 작성해야 한다.
- README Draft는 완성본이 아니라 초안이다.
- 공식 문서나 최신 정보가 필요한 경우 별도 확인이 필요하다.

상세는 [`docs/limitations.md`](docs/limitations.md) 참고.

## Next Steps

- 실제 학습 노트 레포에 본 Kit을 적용해 첫 사례 운영.
- Codex Skill의 인식 경로를 실제 실행 환경에서 확인.
- Writer / Reviewer 사이의 수정 권한 경계 가이드 보강.
- 다국어 템플릿 필요 여부 검토.
# ai-learning-note-skill-kit
