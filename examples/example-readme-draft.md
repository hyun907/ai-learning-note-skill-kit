# README Draft (example)

> Summary와 My Note를 결합한 README 초안 예시. 완성본이 아니다.
> 본 예시 자료는 가상 자료다.

## 학습 주제
Claude Skills와 Codex Skills를 결합한 AI 학습 기록 워크플로우

## 정리한 자료
- 제목: Claude Skills와 Codex Skills를 활용한 AI 학습 기록 워크플로우 (가상 자료)
- 출처: `examples/input-learning-material.md`
- 검토 시점: 2026-05-27

## 핵심 내용
- AI가 사용자의 해석을 임의로 만들면 학습 기록의 신뢰도가 떨어진다.
- 학습 정리는 Summary(사실)와 My Note(해석)로 파일 단위 분리.
- Claude는 Writer, Codex는 Reviewer로 책임 분리.
- 모든 작업은 plan과 사용자 승인 이후 진행.
- 자료는 작업 흐름을 prompt-log와 work-log로 기록할 것을 제안한다.

## 내가 이해한 점
- AI 출력 그대로를 내 생각으로 받아들이면 안 된다는 점이 가장 핵심이다.
- Summary와 My Note를 파일부터 분리하는 것이 가드레일에 가장 가깝다.
- Reviewer 직접 수정 금지가 도구 책임 분리에 효과적이다.

## 내 학습이나 프로젝트에 연결할 점
- 학습 노트 레포에 이 구조를 도입한다.
- README의 "내가 이해한 점"은 직접 작성한 텍스트만 들어가도록 규칙을 정한다.

## 아직 더 공부할 점
- Codex Skill의 인식 경로가 환경마다 다를 수 있는 문제.
- review-findings 이후 Writer가 어디까지 자율로 고치고 어디부터 사용자 승인을 받아야 하는지 경계.

## 다음 액션
- 이번 주 안에 학습 노트 레포에 본 Kit을 적용한다.
- 작은 글 하나로 시범 운영한다.
- prompt-log/work-log의 재현성을 평가한다.

## 한 줄 기록
학습 기록은 AI가 만드는 것이 아니라, AI가 정리한 사실 위에 내가 직접 해석을 쌓는 것이다.
