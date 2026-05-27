# Prompt Log (example)

## 메타
- 작업 날짜: 2026-05-27
- 작업 ID/주제: claude-codex-workflow 학습 정리
- 작성자: Claude Skill (Writer)

## 사용자 요청
"`examples/input-learning-material.md` 자료를 바탕으로 학습 기록을 정리하고, README에 붙일 수 있는 Draft를 만들어줘. plan-first 원칙을 지키고, My Note는 내가 직접 작성할게."

## 사용 도구
- Claude Code (Writer)
- Codex (Reviewer, 후속 단계)

## 적용한 Skill
- `.claude/skills/ai-learning-note/SKILL.md` (Writer)
- `.agents/skills/ai-learning-note/SKILL.md` (Reviewer, 후속 단계에서 적용 예정)

## 계획 요약
- Summary, My Note, README Draft, work-log를 `notes/2026-05-27-claude-codex-workflow/` 하위에 생성.
- My Note는 사용자가 직접 작성.
- Reviewer 단계는 본 흐름 종료 후 별도 진행.

## 승인 여부
- 사용자 승인: 예
- 승인 시각: 2026-05-27
- 승인된 plan 버전: `examples/example-plan.md`

## 주요 프롬프트 흐름
1. Writer가 `plan-template.md`로 plan을 작성하고 사용자에게 승인을 요청.
2. 사용자가 plan을 승인.
3. Writer가 `learning-summary-template.md`로 Summary 작성. 자료 인용 위주, 해석 금지.
4. Writer가 사용자에게 `my-note-template.md`를 안내. 사용자가 직접 작성.
5. Writer가 My Note 작성 완료 확인 후 `readme-draft-template.md`로 Draft 작성. "내가 이해한 점"은 My Note 텍스트를 그대로 반영.
6. Writer가 `work-log-template.md`와 본 prompt-log를 작성.
7. Writer는 사용자에게 Codex Reviewer 흐름으로 이동을 안내. Writer는 review-findings를 직접 작성하지 않는다.

## 결과물
- 생성 파일:
  - `notes/2026-05-27-claude-codex-workflow/learning-summary.md`
  - `notes/2026-05-27-claude-codex-workflow/my-note.md`
  - `notes/2026-05-27-claude-codex-workflow/readme-draft.md`
  - `notes/2026-05-27-claude-codex-workflow/work-log.md`
  - `notes/2026-05-27-claude-codex-workflow/prompt-log.md`
- 수정 파일: 없음

## 확인 필요 사항
- Codex Reviewer가 본 Draft를 검토해 review-findings를 남길 것.
- Reviewer 결과 반영은 Writer가 별도 plan을 다시 작성한 뒤 사용자 승인 후 진행.
