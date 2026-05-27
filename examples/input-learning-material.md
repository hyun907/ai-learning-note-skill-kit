# 학습 자료 (가상): Claude Skills와 Codex Skills를 활용한 AI 학습 기록 워크플로우

> 본 자료는 본 프로젝트의 예시 흐름을 보여주기 위한 **가상 학습 자료**다. 외부에 실재하는 글이 아니다.

## 글의 목적
이 글은 AI 학습 자료를 단순 요약하는 데서 벗어나, Claude Skills와 Codex Skills를 결합해 "사실 정리 / 사용자 해석 / 리뷰"를 분리하는 워크플로우를 제안한다.

## 핵심 주장
1. AI가 사용자의 해석을 임의로 만들어내면 학습 기록의 신뢰도가 떨어진다.
2. 학습 자료 정리는 "확인 가능한 사실(Summary)"과 "사용자의 해석(My Note)"으로 분리되어야 한다.
3. Skill 도구를 둘로 나누면 책임을 분리할 수 있다. Claude는 Writer, Codex는 Reviewer.
4. 모든 작업은 plan과 사용자 승인 이후에 진행된다.

## 이전과의 변화
- 전통적인 AI 요약: 한 번에 자료를 받아 요약본을 출력. 사용자의 해석이 AI 출력에 섞임.
- 제안하는 방식: Summary와 My Note가 파일 단위로 분리. README Draft는 두 산출물을 결합해 만든다.

## 주요 개념
- **plan-first approval gate**: 모든 파일 생성·수정 전 plan을 작성하고 사용자 승인을 받는 단계.
- **Summary와 My Note 분리**: AI가 작성하는 영역과 사용자가 작성하는 영역을 파일 단위로 분리하는 원칙.
- **Reviewer 직접 수정 금지**: 리뷰어 역할의 도구는 문제만 기록하고 수정은 다른 도구가 한다.
- **Prompt/Work Log**: AI 작업을 블랙박스로 두지 않기 위한 기록.

## 자료가 제시한 적용 예시
- 학습한 블로그 글을 정리할 때 Claude Skill로 Summary 생성, My Note는 직접 작성.
- 작성한 README Draft를 Codex Skill로 검토. 직접 수정 대신 review-findings로 받기.
- 모든 작업을 prompt-log와 work-log로 기록.

## 자료가 던지는 질문
- AI가 "이해한 것처럼" 보이는 문장은 어디까지가 사실이고 어디부터가 해석인가
- Writer와 Reviewer의 역할 분리를 어떻게 도구 단위로 강제할 수 있는가
- 학습 기록의 가치는 무엇이 만드는가
