# Plan

> Writer는 작업을 시작하기 전 이 plan을 먼저 작성하고, 사용자의 명시적 승인 이후에만 다음 단계로 진행한다.

## 요청 요약

`claude-master-guide (1).pdf`의 첫 번째 chunk (p.1–p.30, 도입 + 1장)를 AI Learning Note Skill Kit 워크플로로 처리한다.

## 작업 목적

전체 16개 chunk로 나뉜 PDF의 첫 분할본에 대해 Learning Summary를 작성하고, My Note 템플릿을 제공하며, 이후 README Draft 생성과 Review 단계로 이어질 기반을 만든다.

## 생성할 파일

```
notes/2026-05-30-claude-master-guide-ch01/
├── plan.md
├── learning-summary.md
├── my-note.md            (빈 템플릿만 제공, 사용자 작성)
├── prompt-log.md
└── work-log.md
```

(README Draft는 My Note 수령 후 별도 단계에서 생성)

## 수정할 파일

없음 (신규 폴더)

## 작업 범위

- 이 chunk(p.1–p.30)에 한정한 Learning Summary 작성
- Summary 상단에 chunk 위치 표기 (01/16, p.1–p.30)
- My Note 빈 템플릿 제공
- 자료에서 확인 가능한 내용만 작성

## 제외 범위

- My Note 내용 직접 작성 금지
- README Draft는 My Note 수령 전까지 작성 안 함
- 이 chunk 범위를 벗어난 내용 추측·확장 금지
- 이미지/도표의 시각 정보(원본 PDF에서만 확인 가능한 부분) 임의 서술 금지

## 필요한 사용자 입력

- 이 plan에 대한 명시적 승인
- Learning Summary 확인 후 My Note 직접 작성

## 리스크

| 리스크 | 영향 | 완화 |
|---|---|---|
| 이미지·도표 미반영 | 시각 정보 누락 | Summary에 "이미지 참고 필요" 표기 |
| chunk 경계가 절 중간에 끊김 | 내용 불완전 | chunk 범위를 명시하고 미완 절은 표기 |

## 승인 요청

- 위 계획을 검토해주세요.
- 다음 단계로 진행해도 되는지 명시적으로 승인해주세요.

---

**승인 전에는 파일을 생성하거나 수정하지 않는다.**

## 승인 기록

- 사용자 승인: 예
- 승인 일시: 2026-05-30
