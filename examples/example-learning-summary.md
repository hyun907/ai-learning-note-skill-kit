# Learning Summary (example)

> 학습 자료에서 확인 가능한 내용만 정리한 예시.

## 자료 정보
- 제목: Claude Skills와 Codex Skills를 활용한 AI 학습 기록 워크플로우 (가상 자료)
- 출처: `examples/input-learning-material.md`
- 작성일/수정일: 가상 자료 (시점 없음)
- 검토 시점: 2026-05-27

## 1. 핵심 주장
- 자료는 AI가 사용자의 해석을 임의로 만들어내면 학습 기록의 신뢰도가 떨어진다고 주장한다.
- 학습 자료 정리는 "확인 가능한 사실(Summary)"과 "사용자의 해석(My Note)"으로 분리되어야 한다고 말한다.
- Skill 도구를 Writer(Claude)와 Reviewer(Codex)로 나누어 책임을 분리하자고 제안한다.
- 모든 작업은 plan과 사용자 승인 이후에 진행되어야 한다는 원칙을 제시한다.

## 2. 중요한 변화
- 전통적인 AI 요약은 한 번에 요약본을 출력하며 사용자의 해석이 출력에 섞인다고 자료는 말한다.
- 제안 방식은 Summary와 My Note를 파일 단위로 분리하고, README Draft를 두 산출물의 결합으로 만든다고 자료에 명시되어 있다.

## 3. 주요 개념
- plan-first approval gate: 파일 생성·수정 전 plan과 사용자 승인을 받는 단계라고 자료가 정의한다.
- Summary와 My Note 분리: AI 작성 영역과 사용자 작성 영역을 파일 단위로 분리하는 원칙이라고 자료는 설명한다.
- Reviewer 직접 수정 금지: 리뷰어 도구가 문제만 기록하고 수정은 다른 도구가 한다는 원칙.
- Prompt/Work Log: AI 작업을 블랙박스로 두지 않기 위한 기록.

## 4. 적용 아이디어 후보
- 자료는 블로그 글 정리에 Claude Skill로 Summary 생성을 제안한다.
- 자료는 Codex Skill로 README Draft를 검토하고 review-findings를 받는 활용을 제시한다.
- 자료는 모든 작업을 prompt-log와 work-log로 기록하는 활용을 제시한다.

## 5. 생각해볼 질문
- AI가 "이해한 것처럼" 보이는 문장은 어디까지가 사실이고 어디부터가 해석인가
- Writer와 Reviewer의 역할 분리를 도구 단위로 어떻게 강제할 수 있는가
- 학습 기록의 가치는 무엇이 만드는가
