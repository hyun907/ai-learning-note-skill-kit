# Plan (example)

> Writer는 작업을 시작하기 전 이 plan을 먼저 작성하고, 사용자의 명시적 승인 이후에만 다음 단계로 진행한다.

## 요청 요약
사용자는 `examples/input-learning-material.md` 자료를 바탕으로 학습 기록을 정리하고, GitHub README에 붙일 수 있는 Draft를 만들고 싶어한다.

## 작업 목적
- 자료의 사실을 Learning Summary로 정리한다.
- 사용자가 My Note를 직접 작성할 수 있게 안내한다.
- Summary와 My Note를 결합한 README Draft 초안을 만든다.
- 전체 흐름을 prompt-log와 work-log로 남긴다.

## 생성할 파일
- `notes/2026-05-27-claude-codex-workflow/learning-summary.md`
- `notes/2026-05-27-claude-codex-workflow/my-note.md` (사용자가 직접 작성)
- `notes/2026-05-27-claude-codex-workflow/readme-draft.md`
- `notes/2026-05-27-claude-codex-workflow/prompt-log.md`
- `notes/2026-05-27-claude-codex-workflow/work-log.md`

## 수정할 파일
- 없음

## 작업 범위
- 자료에서 확인 가능한 내용만 Summary로 정리한다.
- My Note 작성 안내. 직접 작성은 사용자 영역.
- README Draft의 "내가 이해한 점"은 사용자 My Note 완료 이후에 채운다.

## 제외 범위
- AI가 My Note를 채우지 않는다.
- 외부에서 새로운 자료를 수집하지 않는다.
- 루트 `README.md` 수정은 이번 작업에 포함되지 않는다.
- Reviewer 단계(Codex)는 본 plan의 범위가 아니다.

## 필요한 사용자 입력
- My Note 직접 작성
- README Draft 초안 검토 및 수정 의견

## 리스크
| 리스크 | 영향 | 완화 |
|---|---|---|
| Summary에 AI 해석이 섞일 위험 | Draft 신뢰도 저하 | 자료 원문 인용 위주로 작성, 해석성 문장 검수 |
| My Note가 빈 상태에서 Draft로 진행할 위험 | Draft 품질 저하 | My Note 작성 완료 전까지 Draft 단계로 넘어가지 않는다 |
| 가상 자료라는 점이 Draft에서 약하게 드러날 위험 | 외부 공유 시 오해 | "정리한 자료"에 "가상 자료" 표기 명시 |

## 승인 요청
- 위 계획을 검토해주세요.
- 다음 단계로 진행해도 되는지 명시적으로 승인해주세요.

---

**승인 전에는 파일을 생성하거나 수정하지 않는다.**
