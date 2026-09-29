# Codex 실습 문서

이번 과정은 기존 상품 조회 프로젝트에 **근거를 검색하고 출처를 표시하는 RAG 상담 첫 버전**을 추가합니다. 2장에서 규칙·설정, 3장에서 요구사항, 4장에서 구현 계획을 정리하고 5장에서 구현·검증·커밋·PR까지 완료합니다.

## 읽는 순서

| 문서 | 읽을 부분 | 역할 |
| --- | --- | --- |
| [요구사항정의서.xlsx](요구사항정의서.xlsx) | `Codex_실습범위` | 이번 과정의 범위와 원문 요구사항 연결 |
| [데이터 정의서.xlsx](<데이터 정의서.xlsx>) | 기존 CSV 시트, `RAG_문서`, `RAG_API` | 시작 데이터와 추가할 문서·API 계약 |
| [실습 보완 명세](<실습 보완 명세.md>) | 전체 | 공통 구현·검증 계약 |
| [RAG 상담 요구사항 초안](<RAG 상담 요구사항 초안.md>) | 결정할 질문 | grill-me 인터뷰의 출발점 |
| [강사 진행 가이드](<강사 진행 가이드.md>) | 사전 준비·장별 산출물 | 저장소·문서·계정 준비와 검수 |
| [합성 테스트 자료](fixtures/README.md) | RAG 자료 | API 키 없이 검색·실패 경로 재현 |

기존 Excel 시트의 서비스 요구사항과 CSV 정의는 유지했습니다. `tmp_` 파일은 수정 전 원본입니다. 원문의 수용 O가 곧 이번 강의의 필수 구현을 뜻하지 않습니다. 이번 범위는 `Codex_실습범위`와 실습 보완 명세로 확인합니다.

## 학생이 만드는 문서

템플릿을 읽고 학생의 `project/docs/`에 실제 결정과 결과를 작성합니다. 대괄호는 실제 값으로 바꾸며, 비어 있는 기록을 완료 증거로 제출하지 않습니다.

- [요구사항 템플릿](templates/rag-requirements.md) → `project/docs/requirements/rag-chatbot.md`
- [계획 템플릿](templates/rag-plan.md) → `project/docs/plans/rag-chatbot.md`
- [PR 본문 템플릿](templates/pr-body.md) → `project/docs/pr/rag-chatbot.md`
- [검증·리뷰 기록 템플릿](templates/change-review.md) → `project/docs/reports/rag-review.md`
- [변경 검증 템플릿](templates/change-validation.md) → `project/docs/reports/`의 단위별 기록·`rag-validation.md`

## 5장에서 사용할 제공 Skill

구현은 계획에 맞춘 일반 프롬프트로 요청하고, 반복 절차는 아래 Skill로 진행합니다. 5장 시작에 `project/.agents/skills/`로 세 폴더를 복사합니다. 3장의 외부 Skill은 그대로 유지합니다.

| 제공 Skill | 역할 |
| --- | --- |
| [verify-changes](skills/verify-changes/SKILL.md) | 요구사항·계획 대조, 테스트·품질 검사, 현재 코드에 해당하는 검증 기록 |
| [commit-changes](skills/commit-changes/SKILL.md) | 검증 근거와 staged diff 확인, 단위별 커밋 |
| [create-pr](skills/create-pr/SKILL.md) | 본문 준비, 요청 범위의 push·Draft PR·CI 확인 |

`docs/skills/`는 배포 원본이고 `project/.agents/skills/`는 Codex가 발견하는 설치 위치입니다. 원본을 수정했다면 설치본도 비교·갱신합니다. 실제 동작 조건은 요구사항·계획·실습 명세에서 읽도록 구성했습니다.

MCP·Skill 제작·예약 작업의 일반 설명은 [Work 강의](<../../1. Work/README.md>)를 참고합니다. Codex 3장에서는 기존 find-skills와 grill-me를 요구사항 작업에, 5장에서는 제공 Skill을 검증·커밋·PR 작업에 사용합니다.
