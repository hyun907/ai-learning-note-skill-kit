# Review Findings

> Reviewer는 직접 파일을 고치지 않는다.
> 발견한 문제, 근거, 영향도, 수정 제안만 기록한다.

## 메타
- 리뷰 일자: 2026-05-30
- 리뷰어: Codex Reviewer (`.agents/skills/ai-learning-note/`)
- 리뷰 대상 plan 버전: `notes/2026-05-30-claude-master-guide-ch01/plan.md`

## 리뷰 대상 파일
- `notes/2026-05-30-claude-master-guide-ch01/plan.md`
- `notes/2026-05-30-claude-master-guide-ch01/learning-summary.md`
- `notes/2026-05-30-claude-master-guide-ch01/my-note.md`
- `notes/2026-05-30-claude-master-guide-ch01/readme-draft.md`
- `notes/2026-05-30-claude-master-guide-ch01/prompt-log.md`
- `notes/2026-05-30-claude-master-guide-ch01/work-log.md`

## 참고 기준
- `AGENTS.md`
- `docs/workflow.md`
- `docs/guardrails.md`
- `docs/roles.md`
- `examples/example-review-findings.md`
- `examples/example-prompt-log.md`
- `examples/example-work-log.md`

## 검토 제한
- 원본 PDF 또는 p.1-p.30 텍스트 추출본이 리뷰 대상 폴더에 포함되어 있지 않아, `learning-summary.md`의 모든 사실 주장과 페이지 표기를 원자료와 직접 대조하지는 못했다.
- 현재 레포에는 Skill 문서가 참조하는 `templates/` 디렉터리가 보이지 않아, 실제 템플릿 파일 대신 `examples/` 산출물과 `docs/` 가드레일을 기준으로 구조를 확인했다.

## 발견한 문제 1
- 문제: 원본 학습 자료 또는 chunk 텍스트가 폴더에 보존되어 있지 않아 Summary의 사실성 검토와 작업 재현이 어렵다.
- 근거:
  - `learning-summary.md`는 출처를 `claude-master-guide (1).pdf`, p.1-p.30으로 기록한다.
  - `prompt-log.md`는 사용자가 chunk 텍스트를 제공했다고 기록하지만, 해당 chunk 텍스트 자체는 폴더에 남아 있지 않다.
  - `work-log.md`는 Summary 내용이 p.1-p.30 텍스트 추출본에 근거함을 확인했다고 기록하지만, 검토자가 대조할 수 있는 텍스트 추출본 또는 원본 PDF 경로가 산출물에 포함되어 있지 않다.
  - `docs/guardrails.md`는 모든 작업을 `prompt-log`와 `work-log`에 기록해 재현성을 확보한다고 규정한다.
- 영향도: High
- 수정 제안: Writer 또는 Implementer가 별도 plan-first approval 흐름에서 `input-learning-material.md`처럼 p.1-p.30 입력 텍스트를 박제하거나, 원본 PDF의 접근 가능한 경로·파일 해시·추출 방식·페이지 범위를 로그에 명시한다. 원자료를 저장할 수 없다면, 최소한 Summary의 주요 주장별로 원문 대조가 가능한 인용 또는 위치 정보를 보강한다.

## 발견한 문제 2
- 문제: `readme-draft.md`가 생성되어 있지만, README Draft 생성을 위한 별도 plan/승인 흐름이 `prompt-log.md`와 `work-log.md`에 충분히 기록되어 있지 않다.
- 근거:
  - `plan.md`의 생성할 파일 목록은 `plan.md`, `learning-summary.md`, `my-note.md`, `prompt-log.md`, `work-log.md`까지만 포함하고, README Draft는 My Note 수령 후 별도 단계에서 생성한다고 명시한다.
  - `prompt-log.md`의 주요 프롬프트 흐름과 결과물 목록은 초기 Summary/My Note 템플릿 생성 단계까지만 기록하고, My Note 작성 완료, README Draft 별도 plan, 사용자 승인, `readme-draft.md` 생성 흐름을 기록하지 않는다.
  - `work-log.md`의 생성한 파일 목록에는 `readme-draft.md`가 없지만, 다음 작업 섹션에서는 README Draft 생성이 완료되었다고 표시한다.
  - `docs/workflow.md`와 `docs/guardrails.md`는 plan-first approval과 로그 기록을 핵심 원칙으로 둔다.
- 영향도: High
- 수정 제안: Writer가 별도 plan-first approval 흐름에서 README Draft 생성 단계의 사용자 요청, 별도 plan, 승인 범위, 생성 파일, 검증 내용을 `prompt-log.md`와 `work-log.md`에 보강한다. 별도 승인이 실제로 없었다면, 기존 Draft를 그대로 확정하지 말고 승인 흐름을 다시 밟아 재생성 여부를 판단한다.

## 발견한 문제 3
- 문제: `my-note.md`가 실제 내용으로 채워져 있지만, 사용자가 직접 작성했다는 provenance가 로그에 충분히 남아 있지 않다.
- 근거:
  - `my-note.md`에는 "이 자료를 읽은 이유", "내가 이해한 핵심", "내 학습이나 프로젝트에 연결할 점" 등 사용자의 해석과 적용 방향이 채워져 있다.
  - `prompt-log.md`는 My Note를 빈 템플릿으로 생성했다고만 기록하고, 사용자가 언제 어떤 방식으로 My Note 작성을 완료했는지 기록하지 않는다.
  - `work-log.md`는 주요 변경 내용에서 "My Note: 빈 템플릿만 제공. AI가 내용을 채우지 않음."이라고 기록하면서, 다음 작업 항목에서만 My Note 작성 완료를 취소선으로 표시한다.
  - `AGENTS.md`와 `docs/guardrails.md`는 사용자의 생각, 적용 방향, 평가는 반드시 사용자가 직접 My Note에 작성한다고 규정한다.
- 영향도: Medium
- 수정 제안: Writer가 별도 승인 흐름에서 `prompt-log.md`에 My Note 작성 완료 시점과 작성 주체가 사용자임을 명시한다. 사용자가 직접 작성한 원문을 기반으로 README Draft가 만들어졌다는 연결 관계도 `work-log.md`에 보강한다.

## 발견한 문제 4
- 문제: `readme-draft.md`의 일부 핵심 내용은 `learning-summary.md` 또는 `my-note.md`에서 직접 추적하기 어렵거나 페이지 표기가 맞지 않는다.
- 근거:
  - `readme-draft.md`는 Anthropic Economic Index 항목을 "(Anthropic Economic Index, p.11)"로 표기하지만, `learning-summary.md`의 대응 섹션은 "Anthropic Economic Index 데이터 (p.7)"로 되어 있다.
  - `readme-draft.md`의 "모델이 강해질수록 '너무 넓게 고침', '검증 없이 끝냄'이 더 큰 문제가 된다."는 문장은 `learning-summary.md`의 하네스 정의·예시 또는 `my-note.md`의 대응 문장만으로는 직접 추적하기 어렵다.
  - README Draft 상단은 "내가 이해한 점"은 My Note 기반으로만 정리하고 AI가 임의 해석을 추가하지 않는다고 명시한다.
- 영향도: Medium
- 수정 제안: Writer가 별도 plan-first approval 흐름에서 페이지 표기를 원자료 기준으로 다시 대조한다. Summary/My Note에 없는 문장을 Draft에 유지하려면 원자료 근거를 `learning-summary.md`에 먼저 보강하고, 근거가 없다면 해당 문장을 삭제하거나 My Note 기반 사용자 해석 영역으로 옮기는 것을 고려한다.

---

**리뷰어는 직접 수정하지 않는다.**
**실제 수정은 Writer 또는 Implementer가 별도의 승인 흐름에서 진행한다.**
