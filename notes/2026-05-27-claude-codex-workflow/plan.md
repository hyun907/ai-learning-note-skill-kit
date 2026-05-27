# Plan

> Writer는 작업을 시작하기 전 이 plan을 먼저 작성하고, 사용자의 명시적 승인 이후에만 다음 단계로 진행한다.

## 요청 요약
현재 레포의 Claude Writer 워크플로우를 실제로 한 번 돌려, "Claude Code와 Codex Skills를 활용한 AI 학습 기록 워크플로우"라는 짧은 학습 자료를 학습 기록으로 정리하는 테스트를 진행한다.

## 작업 목적
- `.claude/skills/ai-learning-note` Writer 흐름이 8단계 순서대로 실제 산출물을 만들어내는지 확인한다.
- plan-first approval, Summary/My Note 분리, AI 해석 금지, 로그 기록 4가지 가드레일이 실 작업에서 지켜지는지 검증한다.
- 첫 실제 산출물을 `notes/` 아래에 남겨, 이후 Reviewer(Codex) 흐름의 입력 데이터로도 쓸 수 있게 한다.

## 생성할 파일
**1차 승인 범위(본 plan):**
- `notes/2026-05-27-claude-codex-workflow/input-learning-material.md` — 입력 학습 자료 박제.
- `notes/2026-05-27-claude-codex-workflow/plan.md` — 본 plan 저장.
- `notes/2026-05-27-claude-codex-workflow/learning-summary.md` — 입력 자료의 확인 가능한 사실만 정리.
- `notes/2026-05-27-claude-codex-workflow/my-note.md` — 빈 템플릿 (사용자 작성용).
- `notes/2026-05-27-claude-codex-workflow/prompt-log.md` — 요청·프롬프트 흐름 기록.
- `notes/2026-05-27-claude-codex-workflow/work-log.md` — 생성·수정 파일 기록.

**2차 승인 범위(My Note 작성 완료 후 별도 승인):**
- `notes/2026-05-27-claude-codex-workflow/readme-draft.md` — Summary + 사용자가 채운 My Note 기반.

## 수정할 파일
- 1차 승인 후 단계 진행에 따라 `prompt-log.md`, `work-log.md`를 점진적으로 갱신.
- 그 외 레포 내 기존 파일(`README.md`, `CLAUDE.md`, `AGENTS.md`, `docs/*`, 템플릿 등)은 수정하지 않는다.

## 작업 범위
1차 승인 직후:
1. `notes/2026-05-27-claude-codex-workflow/` 디렉터리 생성.
2. `input-learning-material.md` 작성 — 레포 실제 문서에서 확인 가능한 사실만 박제.
3. `plan.md` 작성 — 본 plan 저장.
4. `learning-summary.md` 작성 — 입력 자료의 사실만 정리.
5. `my-note.md` 빈 템플릿 생성 (`my-note-template.md` 원문 그대로).
6. `prompt-log.md`, `work-log.md` 초기 버전 작성.
7. 사용자에게 My Note 작성 안내.

My Note 작성 후:
8. 사용자가 `my-note.md`를 채워 알려준다.
9. Writer는 README Draft 작성을 위한 별도 plan/승인을 요청한다.
10. 2차 승인 후 `readme-draft.md` 작성 (Summary + My Note 기반만).
11. `prompt-log.md`, `work-log.md` 최종 갱신.
12. Reviewer(Codex) 흐름 안내로 마무리.

## 제외 범위
- README Draft 작성은 본 plan의 승인 범위가 아니다. 별도 plan/승인 이후 진행.
- 레포의 기존 문서(`README.md`, `CLAUDE.md`, `AGENTS.md`, `docs/*`, 템플릿) 수정.
- 외부 자료 크롤링·API 연동·CI 통합.
- `my-note.md`에 AI가 답변·예시·placeholder 텍스트를 미리 채우는 행위.

## 필요한 사용자 입력
- 1차 승인 (본 plan).
- `my-note.md`의 5개 항목을 사용자가 직접 작성 (이번 1차 테스트에서는 기존 템플릿 5개 항목을 그대로 사용).
  1. 이 자료를 읽은 이유
  2. 내가 이해한 핵심
  3. 내 학습이나 프로젝트에 연결할 점
  4. 아직 헷갈리는 점
  5. 다음 액션
- My Note 작성 완료 후 README Draft 진행을 위한 2차 승인.

## 리스크
| 리스크 | 영향 | 완화 |
|---|---|---|
| `input-learning-material.md`가 AI 추측 기반이 되어 Summary가 오염될 수 있음 | Summary가 "자료의 사실"이 아니라 "AI의 일반 지식"이 됨 | 입력 자료는 레포의 실제 문서에서 확인 가능한 사실만으로 구성. 외부 지식·추론은 넣지 않음. |
| README Draft가 승인 전에 작성되는 사고 | My Note 없이 AI 해석이 들어감 | 1차/2차 승인을 명확히 분리. 2차 승인 전에는 `readme-draft.md` 생성·수정 금지. |
| 빈 `my-note.md`에 AI가 예시·placeholder 텍스트로 미리 채움 | 가드레일 위반 (My Note 임의 작성) | `my-note.md`는 `my-note-template.md` 원문 그대로 복사. 답변 칸은 빈 줄로 둠. |
| 단계 진행 중 prompt/work log 누락 | 기록 일관성 깨짐 | 파일 생성 직후 `work-log.md`에 항목 추가, 요청·승인 시점은 `prompt-log.md`에 기입. |
| 1회 승인이 전체 단계 승인으로 오해됨 | 가드레일 우회 | 1차 승인 범위 = 위 6개 파일(README Draft 제외)임을 plan에 명시. |

## 승인 요청
- **1차 승인 (이번):** 위 "생성할 파일 — 1차 승인 범위"의 6개 파일을 생성한다.
- **2차 승인 (나중):** 사용자가 `my-note.md`를 채운 뒤 별도 plan으로 다시 요청. 그때 `readme-draft.md`를 생성한다.

추가 확인 사항(이미 사용자가 확정):
- 디렉터리 경로: `notes/2026-05-27-claude-codex-workflow/`.
- `input-learning-material.md` 소스: 이 레포의 실제 문서들로 한정 (외부 지식·추측 배제).
- `my-note.md`: 기존 `my-note-template.md` 구조 그대로, 5개 항목 고정.

---

**승인 전에는 파일을 생성하거나 수정하지 않는다.**
