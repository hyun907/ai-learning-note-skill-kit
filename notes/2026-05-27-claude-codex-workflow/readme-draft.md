# README Draft

> Summary와 My Note를 바탕으로 만든 **초안**이다. 완성본이 아니다.
> "내가 이해한 점"은 My Note 기반으로만 정리한다. AI는 임의 해석을 추가하지 않는다.

## 학습 주제

Claude Code와 Codex Skills를 활용한 AI 학습 기록 워크플로우

## 정리한 자료

- 제목: Claude Code와 Codex Skills를 활용한 AI 학습 기록 워크플로우
- 출처: `notes/2026-05-27-claude-codex-workflow/input-learning-material.md` (소스: 본 레포의 `README.md`, `CLAUDE.md`, `AGENTS.md`, `docs/workflow.md`, `docs/guardrails.md`, `docs/roles.md`, `docs/limitations.md`, 두 SKILL.md)
- 검토 시점: 2026-05-27

## 핵심 내용

<!-- Learning Summary 기반. 자료에서 확인 가능한 내용만 옮긴다. -->

**핵심 주장**

- "AI가 만든 요약이 내 생각처럼 보이는 문제"를 막기 위한 Kit이다. (`README.md`)
- AI는 자료에서 확인 가능한 사실만 Summary로 정리하고, 사용자는 자기 해석을 My Note에 직접 작성하며, 결과물 리뷰는 Codex Skill이 Reviewer 역할로 담당한다. (`README.md`)
- "모든 작업은 plan과 사용자 승인을 거친다." (`README.md`)
- "Reviewer는 직접 파일을 고치지 않는다." (`docs/roles.md`)
- "로그가 없는 작업은 재현 불가로 간주한다." (`docs/guardrails.md`)

**주요 개념**

- **plan-first approval gate** — 모든 파일 생성·수정 전 plan을 먼저 작성하고, 사용자의 명시적 승인 이후에만 작업을 시작한다. (`docs/guardrails.md`)
- **Summary와 My Note 분리** — `learning-summary-template.md`는 자료에서 확인 가능한 사실만, `my-note-template.md`는 사용자가 직접 작성한 해석만 담는다. (`docs/guardrails.md`)
- **Writer / Reviewer 분리** — Claude Skill은 Writer, Codex Skill은 Reviewer. Reviewer는 `review-findings-template.md`로 문제·근거·영향도·수정 제안만 남긴다. (`README.md`, `docs/roles.md`)
- **8단계 워크플로우** — Intake → Plan → Approval → Learning Summary → My Note → README Draft → Prompt/Work Log → Review. (`docs/workflow.md`)

## 내가 이해한 점

<!-- My Note의 "내가 이해한 핵심" 기반. AI가 가공·확장하지 않는다. -->

이 워크플로우의 핵심은 AI가 모든 것을 대신 작성하는 것이 아니라, AI가 정리할 영역과 사용자가 직접 써야 할 영역을 분리하는 것이다.

AI는 자료에서 확인 가능한 내용을 Summary로 정리하고, 사용자의 생각이나 해석은 My Note에 사용자가 직접 작성한다. README Draft는 이 두 정보를 바탕으로 만들어지는 초안이며, 완성본이 아니다.

Claude와 Codex를 같은 역할로 쓰지 않고, Claude는 Writer로, Codex는 Reviewer로 분리하는 점이 중요하다고 이해했다. Reviewer가 직접 파일을 고치면 또 다른 구현자가 되어버리기 때문에, 문제와 근거, 수정 제안만 남기도록 제한하는 구조가 필요하다.

## 내 학습이나 프로젝트에 연결할 점

<!-- My Note의 해당 섹션 기반. -->

이 구조는 앞으로 AI 관련 자료를 공부할 때 반복해서 사용할 수 있을 것 같다. 자료를 읽고 바로 요약본을 붙여넣는 대신, Summary와 My Note를 분리해서 내 이해가 들어간 학습 기록으로 남길 수 있다.

단순히 "AI를 활용했다"고 말하는 데서 끝나는 것이 아니라, AI가 맡을 수 있는 영역과 사용자가 직접 판단해야 하는 영역을 구분하는 기준이 중요하다고 느꼈다.

plan-first approval, 역할 분리, prompt/work log 같은 장치는 AI 결과물을 그대로 믿는 것이 아니라, 검토 가능하고 재현 가능한 작업 과정으로 만들기 위한 방법이라고 이해했다. 이 흐름은 앞으로 AI를 활용해 개발할 때도 계속 적용해보고 싶은 작업 방식이다.

## 아직 더 공부할 점

<!-- My Note의 "아직 헷갈리는 점" 기반. -->

Claude Skill과 Codex Skill이 실제 각 도구에서 얼마나 안정적으로 인식되는지 직접 확인이 필요하다.

review-findings를 받은 뒤 Writer가 어떤 방식으로 후속 plan을 만들고 수정 작업으로 이어갈지에 대한 흐름은 더 구체화해야 할 것 같다.

이 Skill Kit을 실제 학습 자료에 적용했을 때 Summary 품질이 얼마나 안정적인지, My Note를 작성하는 과정이 부담스럽지 않은지도 테스트가 필요하다.

## 다음 액션

<!-- My Note의 "다음 액션" 기반. -->

1. 수정된 README Draft를 최종 기록으로 사용할지 검토한다.
2. 필요하다면 HTML 주석을 제거한 게시용 버전을 별도로 만든다.
3. 실제 Claude Code/Cowork 관련 외부 자료 일부를 넣어 2차 테스트를 진행한다.
4. Writer 수정 후 Reviewer 재검토가 필요한지 판단한다.

## 한 줄 기록

이 워크플로우의 핵심은 AI가 모든 것을 대신 작성하는 것이 아니라, AI가 정리할 영역과 사용자가 직접 써야 할 영역을 분리하는 것이다.
