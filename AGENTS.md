# AGENTS.md

> 본 문서는 Codex(및 다른 자동화 에이전트)가 이 레포에서 따라야 할 프로젝트 지침이다.
> 보조 문서는 `docs/`에 있다. 본 문서는 **규칙 선언**에 집중하고, 상세 설명은 그쪽으로 위임한다.

## 핵심 규칙

1. **plan-first approval**
   - 어떤 파일도 사용자 승인 전에는 생성·수정하지 않는다.
   - 작업 시작 전 plan 템플릿을 사용해 plan을 작성한다.

2. **Summary와 My Note 분리**
   - `learning-summary-template.md`는 자료에서 확인 가능한 사실만 담는다.
   - `my-note-template.md`는 사용자가 직접 작성한다.
   - 두 파일의 경계를 흐리지 않는다.

3. **사용자 해석을 AI가 임의로 작성하지 않는다**
   - AI는 자료 외 해석·단정을 출력하지 않는다.
   - "사용자는 이렇게 이해할 것이다"라는 식의 표현 금지.

4. **Reviewer는 직접 수정하지 않는다**
   - 발견한 문제·근거·영향도·수정 제안을 `review-findings-template.md`로만 남긴다.
   - 실제 수정은 Writer 또는 Implementer가 별도의 승인 흐름에서 진행한다.

5. **README Draft는 완성본이 아니라 초안이다**
   - Draft를 그대로 게시하지 않고, 사용자가 검토·수정한 뒤 사용한다.

6. **prompt-log와 work-log로 작업 흐름을 기록한다**
   - 모든 작업은 두 로그에 남긴다.
   - 로그가 없는 작업은 재현 불가로 간주한다.

## Skill 경로

- Claude Writer: `.claude/skills/ai-learning-note/SKILL.md`
- Codex Reviewer: `.agents/skills/ai-learning-note/SKILL.md`

`.agents/skills/` 위치는 Codex의 repository skill 위치로 사용할 수 있도록 의도되었으나, **실제 실행 환경에서 Codex가 해당 skill을 인식하는지는 사용 전 확인이 필요하다.** 인식되지 않으면 사용자가 자신의 Codex 설정에 맞춰 경로를 옮길 수 있다.

## Relationship with CLAUDE.md

- 본 문서(`AGENTS.md`)는 Codex(Reviewer) 지침이다.
- [`CLAUDE.md`](CLAUDE.md)는 Claude Code(Writer) 지침이다.
- Reviewer는 직접 수정하지 않고 문제와 제안만 `review-findings`로 남긴다.
- Writer가 Reviewer 결과를 반영할 때도 **plan-first approval**을 따른다.

## 참고

- Claude Code(Writer) 지침: [`CLAUDE.md`](CLAUDE.md)
- 전체 흐름: `docs/workflow.md`
- 원칙 상세: `docs/guardrails.md`
- 역할 분리: `docs/roles.md`
- 한계: `docs/limitations.md`
