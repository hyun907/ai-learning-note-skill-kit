# Guardrails

AI Learning Note Skill Kit이 지키는 원칙. 모든 Skill과 템플릿은 이 가드레일 안에서 동작한다.

## 1. plan-first approval gate

- 모든 파일 생성·수정 전 plan을 먼저 작성한다.
- 사용자의 명시적 승인("승인. 진행해줘." 같은 표현) 이후에만 작업을 시작한다.
- 승인 범위를 벗어나는 결정이 필요해지면 작업을 멈추고 재승인을 요청한다.

## 2. AI 해석 금지

- AI는 학습 자료에서 확인 가능한 내용만 Summary로 정리한다.
- "사용자가 이렇게 이해할 것이다", "이 자료는 결국 이런 뜻이다" 같은 단정·해석을 추가하지 않는다.
- 사용자의 생각, 적용 방향, 평가는 반드시 사용자가 직접 My Note에 작성한다.

## 3. Summary와 My Note 분리

- `learning-summary-template.md`는 자료에서 확인 가능한 사실만 담는다.
- `my-note-template.md`는 사용자가 직접 작성한 해석만 담는다.
- 두 파일의 경계가 흐려지면 README Draft의 신뢰도가 무너진다.

## 4. Reviewer 직접 수정 금지

- Reviewer는 파일을 직접 수정하지 않는다.
- 발견한 문제, 근거, 영향도, 수정 제안만 `review-findings-template.md`로 남긴다.
- 실제 수정은 Writer 또는 Implementer가 별도의 승인 흐름에서 진행한다.

## 5. 로그로 재현성 확보

- 모든 작업은 `prompt-log`와 `work-log`에 기록된다.
- 요청 → 계획 → 승인 → 결과물까지의 흐름을 누락 없이 남긴다.
- 이 기록이 있어야 같은 작업을 재현하거나 디버깅할 수 있다.
- 로그가 없는 작업은 재현 불가로 간주한다.
