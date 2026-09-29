# Codex로 RAG 상담 기능을 PR까지 완성하기

개발자가 기존 프로젝트를 인수하고 Codex로 규칙 적용·요구사항 구체화·구현 계획·구현·검증·커밋·PR을 수행하는 강의입니다. 건강한하루의 상품 조회 시작 코드를 공통 사례로 사용합니다.

## 강의 순서

| 번호 | 강의 | 시작과 산출물 |
| --- | --- | --- |
| 0 | [Codex의 Best Practices](<0. Codex의 Best Practices.md>) | 기존 개념 자료 유지 |
| 1 | [실습 환경과 기본 프로젝트](<1. 실습 환경과 기본 프로젝트.md>) | 기존 실행 실습 유지, 상품 조회·기본 테스트 |
| 2 | [AGENTS.md와 Codex 설정 적용하기](<2. AGENTS.md와 Codex 설정 적용하기.md>) | 프로젝트 규칙·설정·적용 확인 |
| 3 | [Skill로 RAG 요구사항 구체화하기](<3. Skill로 RAG 요구사항 구체화하기.md>) | find-skills·grill-me 활용, 요구사항 합의 |
| 4 | [Plan 모드로 구현 방법 검토하기](<4. Plan 모드로 구현 방법 검토하기.md>) | 변경·검증·커밋·PR 계획 |
| 5 | [계획에 따른 구현·검증·커밋·PR](<5. 계획에 따른 구현·검증·커밋·PR.md>) | 동작하는 RAG 첫 버전과 검토 가능한 PR |

0·1번의 Markdown과 기존 PDF는 유지했습니다. 2~5번은 Marp Markdown 강의자료입니다. VS Code의 Marp 미리보기로 발표하며 필요하면 PDF로 내보낼 수 있습니다. 이전 2~10번과 기존 목차는 같은 폴더의 `tmp_` 파일로 보관했습니다.

## 준비 자료와 진행 기준

[docs 안내](docs/README.md)와 [강사 진행 가이드](<docs/강사 진행 가이드.md>)부터 확인합니다. Excel의 기존 원문은 유지하고 이번 범위를 표시하는 시트를 추가했습니다. 원문 전체 서비스의 수용 O를 이번 과정의 필수 구현으로 해석하지 않습니다.

학생은 Python·VS Code·Git/GitHub·터미널을 사용할 수 있다고 가정합니다. 개발 도구는 VS Code Codex 확장, 서비스는 Python 3.13·uv·Streamlit·FastAPI·SQLite·Groq입니다. Skill 설치에는 Node.js·npm/npx, PR 명령에는 GitHub CLI를 사용합니다. GitHub 웹으로 PR을 생성하는 대안도 제공합니다.

일반적인 MCP·Skill 제작·예약 작업은 [Work 강의](<../1. Work/README.md>)를 참조합니다. 이 과정에서는 기존 Skill을 요구사항 작업에 활용합니다. 프로필·복용량 계산·PostgreSQL 전환·전체 서비스 구현은 이번 필수 범위에서 제외합니다.

## 작업 공간과 브랜치

강의 저장소 외부의 학생 폴더에 `docs`, `data`, `project`를 함께 준비합니다. 학생 Git 루트는 이 세 폴더를 포함해야 합니다. `project`만 Git 저장소로 만들면 테스트 자료와 CSV가 CI에 없을 수 있습니다. 상세 초기화는 강사 가이드를 따릅니다.

- 시작 코드: 학생 저장소의 main에 기준 커밋으로 보관
- 2~4장: chore/codex-setup에서 지침·Skill·요구사항·계획 준비
- 5장 시작: 준비 상태·CI를 main에 반영한 후 feat/rag-chatbot 생성
- 기능 변경: 작은 단위별 검증·리뷰·커밋, 하나의 RAG PR로 전달

PowerShell 명령은 별도 안내가 없으면 `project`에서 실행합니다. Codex 프롬프트는 입력창에 붙입니다. 강의에 등장하는 새 기능 파일과 명령은 학생이 구현한 뒤 실행합니다. `.env`, DB, 가상환경·캐시를 커밋하지 않습니다.

## 검증과 제출

1장에서는 기본 22개 테스트와 상품 44개 조회를 확인합니다. 5장에서는 기존 테스트에 신규 테스트가 추가되므로 총 개수는 학생 구현에 따라 달라집니다.

```powershell
# project에서 테스트·코드 규칙·서식을 검사합니다.
uv run --locked python -m pytest -q --basetemp=.pytest_cache/tmp
uv run --locked ruff check .
uv run --locked ruff format --check .
```

최종 제출은 합의한 요구사항·계획, 기능 커밋, 검증·리뷰 기록, PR URL, CI 결과와 리뷰 반영 근거입니다. 모의 테스트, 실제 Groq 호출, 공식 원문 대조를 구분합니다. 자료·계정·네트워크 때문에 실행하지 못한 항목은 이유와 다음 확인을 적습니다.

현재 배포물은 상품 조회 시작 코드와 학생 구현을 위한 강의입니다. 실제 RAG 완성 코드·학생 PR·CI·외부 Skill 설치를 이미 실행했다고 표시하지 않습니다. 공식·원본 안내 확인일: 2026-09-29.
