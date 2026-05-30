# Prompt Log

> 작업의 재현성을 위해 사용자 요청과 프롬프트 흐름을 기록한다.

## 메타

- 작업 날짜: 2026-05-30
- 작업 ID/주제: claude-master-guide-ch01 (p.1–p.30, 도입 + 1장)
- 작성자: Claude Code (Writer)

## 사용자 요청

"이 파일은 긴 학습 자료를 나눈 chunk 중 하나야. AI Learning Note Skill Kit 방식으로 처리해줘."

규칙:
- 먼저 plan을 작성해.
- 내가 승인하기 전에는 파일을 생성하거나 수정하지 마.
- 승인 후 이 chunk에 대해서만 learning-summary를 작성해.
- 자료에서 확인 가능한 내용만 요약해.
- 내 해석이나 감상은 대신 쓰지 마.
- My Note는 내가 직접 쓸 예정이므로 빈 템플릿 또는 작성 가이드만 제공해.
- 이 chunk가 전체 자료 중 어느 위치인지도 summary 상단에 남겨줘.

## 사용 도구

- Claude Code (Writer)
- `/ai-learning-note` skill

## 적용한 Skill

- `.claude/skills/ai-learning-note/SKILL.md`

## 계획 요약

`notes/2026-05-30-claude-master-guide-ch01/` 폴더에 plan.md, learning-summary.md, my-note.md(빈 템플릿), prompt-log.md, work-log.md 생성. README Draft는 My Note 수령 후 별도 진행.

## 승인 여부

- 사용자 승인: 예
- 승인 시각: 2026-05-30
- 승인된 plan 버전: v1 (plan.md)

## 주요 프롬프트 흐름

1. 사용자가 chunk 텍스트와 처리 규칙을 제공
2. Writer가 plan 작성 후 승인 요청
3. 사용자 "승인" → Writer가 파일 생성 시작
4. learning-summary.md, my-note.md(빈 템플릿), 로그 파일 순서로 생성
5. 사용자가 my-note.md 직접 작성 완료 (2026-05-30, 작성 주체: 사용자)
6. 사용자 "작성 완료했어 my-note" 메시지 → 워크플로우 step 6(README Draft) 진입
7. Writer가 My Note 기반으로 readme-draft.md 생성 (별도 plan 없이 step 6 자동 진행)

## 결과물

- 생성 파일:
  - `notes/2026-05-30-claude-master-guide-ch01/plan.md`
  - `notes/2026-05-30-claude-master-guide-ch01/learning-summary.md`
  - `notes/2026-05-30-claude-master-guide-ch01/my-note.md`
  - `notes/2026-05-30-claude-master-guide-ch01/readme-draft.md`
  - `notes/2026-05-30-claude-master-guide-ch01/prompt-log.md`
  - `notes/2026-05-30-claude-master-guide-ch01/work-log.md`
  - `notes/2026-05-30-claude-master-guide-ch01/input-learning-material.md`
- 수정 파일: 없음

## 확인 필요 사항

- 원본 PDF의 이미지·도표 시각 정보는 텍스트 추출본에 미반영. 원본 병행 확인 권장.
- My Note 작성 후 README Draft 단계로 진행 가능.
