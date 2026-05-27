# Roles

AI Learning Note Skill Kit의 역할 구분. 한 사람·한 도구가 여러 역할을 겸할 수 있으나, 각 역할의 책임과 금지 사항은 분리해서 지킨다.

## Researcher

- **책임**
  - 학습 자료를 수집하고 정리한다.
  - 자료의 출처, 작성일, 신뢰도를 기록한다.
- **금지**
  - 자료에 없는 내용을 만들어 넣지 않는다.
  - 자료의 해석을 단정하지 않는다.

## Planner

- **책임**
  - 작업 시작 전 plan을 작성한다.
  - 생성·수정 예정 파일, 작업 범위, 제외 범위, 리스크, 필요한 사용자 입력을 명시한다.
- **금지**
  - 사용자 승인 전 파일을 생성·수정하지 않는다.
  - 계획 없이 임의로 작업을 확장하지 않는다.

## Writer

- **책임**
  - 승인된 plan에 따라 `learning-summary`, `readme-draft`, `prompt-log`, `work-log`를 작성한다.
  - 사용한 자료를 출처로 명시한다.
- **금지**
  - 사용자의 해석을 임의로 작성하지 않는다.
  - `my-note`는 채우지 않는다(사용자 전용 영역).
  - Reviewer의 산출물(`review-findings`)을 대신 만들지 않는다.

## Reviewer

- **책임**
  - 결과물의 사실성, 템플릿 준수, 구조 일관성을 검토한다.
  - 문제점, 근거, 영향도(High/Medium/Low), 수정 제안을 `review-findings-template.md`로 남긴다.
- **금지 (강화)**
  - **Reviewer는 직접 파일을 고치지 않는다.**
  - **수정·추가·삭제가 아닌 문제 보고만 한다.**
  - **수정 제안이 아무리 명확하더라도 직접 적용하지 않는다.**
  - **Writer의 작업을 대신 수행하지 않는다.**
  - **실제 수정은 Writer 또는 Implementer가 별도의 승인 흐름에서 진행한다.**

## 역할 경계 요약

| 산출물 | 작성 주체 |
|---|---|
| plan | Planner (또는 Writer가 겸임) |
| learning-summary | Writer |
| my-note | 사용자 |
| readme-draft | Writer (My Note 기반) |
| prompt-log / work-log | Writer |
| review-findings | Reviewer |
