# Claude Code 강의 커리큘럼

> 상위 과정: 바이브 코딩 & Agentic AI 실전 (`1. Agentic Coding`)
> 이 모듈의 목표: "AI에게 시켜서 대충 완성"이 아니라, **에이전트에게 안전하게 위임하고, 결과를 검증하고, 팀 워크플로우에 통합**할 수 있는 실무 감각을 기르는 것.

전체 12차시(0~11), 차시당 2~3시간, 총 약 30시간 분량. 주 2회 진행 시 약 6주 과정.

> [!NOTE]
> 이 문서는 2026-09-01 기준 공식 Anthropic 문서를 바탕으로 구성했다. Claude Code·Claude Cowork의 모델, 요금제, 명령, 제공 기능은 바뀔 수 있으므로 수업 직전 [Claude Code 공식 문서](https://code.claude.com/docs/en)와 [Claude Cowork 공식 문서](https://claude.com/docs/cowork/overview)를 다시 확인한다.

---

## 학습 목표 (수료 시 학생이 할 수 있어야 하는 것)

1. Claude Code를 설치하고 자신의 프로젝트에서 자율적으로 작업을 위임할 수 있다
2. Chat·Claude Cowork·Claude Code의 역할을 구분하고, 작업 성격에 따라 적절한 환경을 선택할 수 있다
3. `CLAUDE.md`로 프로젝트 컨텍스트를 설계해 AI 출력 품질을 통제할 수 있다
4. Plan Mode·diff 리뷰·커밋 전 확인 등 **위험을 관리하는 승인 습관**을 체화한다
5. Git/GitHub 워크플로우(브랜치, 커밋, PR) 전체를 에이전트와 함께 수행할 수 있다
6. "AI가 됐다고 말한 것"을 그대로 믿지 않고 **직접 검증**하는 태도를 가진다
7. Custom Skill, Hook, Subagent, MCP로 반복 작업을 자동화할 수 있다 — 이 확장 기능들이 Claude Cowork와도 공유된다는 점을 이해한다
8. Headless 모드/CI 연동으로 대화형을 넘어선 자동화 파이프라인을 구상할 수 있다
9. 비용·모델 선택 기준을 이해하고, 팀 단위로 안전하게 확산시킬 규칙을 제안할 수 있다

## 사전 준비물

- Anthropic 계정 (Claude Code 로그인용) / 팀 사용 시 Console 계정
- Node.js 18+ 설치 가능한 PC
- GitHub 계정, `gh` CLI 설치 가능 환경
- VS Code (선택: Claude Code용 IDE 확장 설치)
- Claude Cowork 체험용 유료 플랜(Pro/Max/Team/Enterprise) 및 Claude Desktop 앱 — 0차시 비교 실습에 필요 (선택, 미보유 시 강사 데모로 대체)

---

## 0차시. 오리엔테이션 — Chat·Cowork·Claude Code와 Agentic Coding

- **목표**: Chat, Claude Cowork, Claude Code의 역할과 "코드 자동완성 도구"·"에이전트"의 차이를 구분한다
- **내용**
  - [Claude 제품 지도](https://claude.com/docs/cowork/overview)
    - **Chat**: 질문, 설명, 브레인스토밍, 짧은 초안처럼 대화 자체가 중심인 작업
    - **Claude Cowork**: Claude Code와 **동일한 에이전트 아키텍처**를 쓰지만 터미널 없이 Claude Desktop에서 실행되는 크로스앱 지식노동 에이전트. 로컬 파일을 직접 읽고 쓰며, Slack·Google Drive 등 커넥터와 Claude in Chrome으로 웹 작업까지 자동화하고, 복잡한 작업은 서브에이전트로 나눠 병렬 처리한 뒤 문서·스프레드시트·발표자료 같은 **완성된 결과물**을 만든다
    - **Claude Code**: 코드베이스를 이해하고, 코드를 수정하고, 명령과 테스트를 실행하며, diff와 PR로 변경을 전달하는 소프트웨어 개발 전용 에이전트
  - Cowork와 Claude Code는 같은 엔진 위에 있지만 완전히 같은 설정을 공유하지는 않는다 — 예: Cowork는 세션 시작 시 claude.ai 계정에 연결된 Skill·커넥터·플러그인만 불러오며, 로컬 Claude Code CLI의 `~/.claude` 디렉터리는 자동으로 읽지 않는다 (Cowork에서 쓰려면 **Customize**에서 별도로 추가해야 함)
  - 자동완성 도구와 에이전트의 차이: 답변 생성 vs 파일 읽기 → 계획 → 수정 → 명령 실행 → 결과 관찰 → 재시도
  - Claude Code가 잘하는 일 vs Cowork가 잘하는 일: 코드베이스 작업·테스트·PR(Claude Code) vs 문서/보고서 종합, 반복 업무, 여러 앱을 넘나드는 지식노동(Cowork)
  - 하나의 프로젝트 안에서도 Cowork로 요구사항 조사·보고서를 만들고, Claude Code로 구현·테스트·PR을 진행한 뒤, 다시 Cowork로 발표자료나 운영 문서를 만드는 연결 흐름
  - 왜 "바이브 코딩"이 위험할 수도, 강력할 수도 있는가 — 통제권을 어디에 둘 것인가
  - 이 과정의 지향점: "빨리 만들기"가 아니라 "믿고 맡기되 검증하는 법". 이 원칙은 Claude Code뿐 아니라 Cowork에도 동일하게 적용된다
- **실습**: 하나의 요청(예: "이 프로젝트 현황을 정리해줘")을 Chat·Cowork·Claude Code에 각각 맡겨보고, 대화형 답변·완성된 문서·검증된 코드 변경의 차이를 비교하는 선택표 작성

## 1차시. 설치와 첫 실행

- **목표**: 터미널 공포감을 없애고 안전 모드부터 익힌다
- **내용**
  - 터미널 기초 (경로, cd, ls/dir), Node.js/npm 설치
  - `npm install -g @anthropic-ai/claude-code` 설치, 로그인
  - **Permission Mode 4종**: 기본(매번 승인) / Accept Edits(수정 자동승인) / Plan Mode(읽기 전용, 계획만) / Bypass(전체 자동, 위험) — 언제 무엇을 쓰는지
  - `/help`, `/init`, 세션 재개(`--continue`, `--resume`) 등 기본 슬래시 명령
- **실습**: 빈 폴더에서 Plan Mode로 "간단한 계산기 웹페이지" 계획만 세워보고, 승인 후 실행까지 진행

## 2차시. 에이전트에게 일을 시키는 법 (프롬프트가 아니라 "브리핑")

- **목표**: 모호한 지시와 좋은 지시의 차이를 체감한다
- **내용**
  - 나쁜 지시("로그인 기능 만들어줘") vs 좋은 지시(맥락, 제약조건, 완료 기준 명시)
  - Explore 기반 탐색 시키기: "이 프로젝트 구조부터 파악해줘" → 이해도 확인 후 작업 지시
  - 큰 작업을 작은 단위로 쪼개서 위임하는 법 (한 번에 다 시키지 않기)
  - 진행 중 방향 수정하는 법 — 끝까지 기다리지 않고 중간 개입하기
- **실습**: 기존 오픈소스 미니 프로젝트를 던져주고 "이 코드가 뭘 하는지 설명해줘" → 기능 하나 추가 요청까지

## 3차시. CLAUDE.md — 프로젝트의 두뇌 설계하기

- **목표**: 매번 같은 설명을 반복하지 않도록 프로젝트 컨텍스트를 파일로 고정한다
- **내용**
  - `CLAUDE.md`의 역할: 코딩 컨벤션, 금지 사항, 아키텍처 원칙, 자주 쓰는 명령어 명시
  - 좋은 `CLAUDE.md` vs 나쁜 `CLAUDE.md` (너무 길어서 안 읽히는 경우 포함)
  - `/init`으로 초안 생성 → 다듬는 실습
  - 프로젝트 규모가 커질 때 하위 폴더별 `CLAUDE.md` 분리 전략
- **실습**: 2차시 프로젝트에 `CLAUDE.md`를 작성하고, 같은 요청을 다시 시켜 결과 품질 변화 비교

## 4차시. Plan Mode와 승인 워크플로우 — 안전하게 맡기기

- **목표**: "일단 승인 → 결과 확인" 습관 대신 "계획 확인 → 승인 → 결과 확인"을 체화한다
- **내용**
  - Plan Mode로 실행 전 계획서 받아보기, 계획이 마음에 안 들면 반려하고 다시 계획시키기
  - diff를 실제로 읽는 법 — 변경된 줄만 보지 말고 "이게 왜 필요한가" 질문하기
  - 위험한 명령(강제 push, 파일 삭제, DB 마이그레이션) 앞에서 반드시 멈추는 습관
  - 되돌리기: git으로 안전망 만들기 (커밋 전 상태로 되돌아갈 수 있게 하기), 체크포인트 개념
- **실습**: 일부러 모호하거나 위험할 수 있는 요청("이 폴더 정리해줘")을 시켜보고, Plan Mode로 의도 파악 후 반려/재요청하는 롤플레이

## 5차시. Context 관리 — 세션 위생

- **목표**: 대화가 길어질수록 품질이 떨어지는 이유를 이해하고 관리한다
- **내용**
  - 컨텍스트 윈도우 개념, 대화가 길어지면 생기는 문제 (이전 지시 망각, 엉뚱한 파일 수정)
  - `/clear`(완전 초기화) vs `/compact`(요약 압축) 언제 쓸지
  - 작업 단위별로 세션을 나누는 전략 — "이 기능 하나 끝나면 새 세션"
  - Subagent 맛보기: 탐색/조사를 별도 에이전트에 맡겨 메인 컨텍스트를 보호하는 개념
- **실습**: 일부러 긴 대화를 이어가며 성능 저하를 관찰 → `/compact` 전후 비교

## 6차시. Git/GitHub 완전 연동

- **목표**: 실제 협업 환경의 커밋~PR 흐름을 에이전트와 함께 수행한다
- **내용**
  - git status/diff/log를 에이전트가 확인하고 커밋 메시지를 작성하게 하는 법
  - 브랜치 전략, `gh` CLI로 PR 생성까지 자동화
  - 커밋은 작게, 의미 단위로 — "한 번에 다 커밋"의 위험성
  - 시크릿/민감정보가 실수로 커밋되는 것을 막는 습관 (커밋 전 git status/diff 재확인)
- **실습**: 브랜치 생성 → 기능 구현 → 커밋 → PR 생성 → (동료와) 리뷰 코멘트 반영까지 전체 사이클

## 7차시. 검증과 디버깅 — AI를 의심하는 기술

- **목표**: 이 커리큘럼에서 가장 중요한 차시. "됐다"는 말을 믿지 않는 습관
- **내용**
  - "테스트 통과했습니다"라는 말 대신 실제 실행 로그를 직접 확인하는 법
  - 에이전트가 스스로 만든 테스트가 진짜 검증인지, 형식적인지 구분하기
  - 버그 재현 정보(에러 로그, 재현 단계)를 정확히 제공하는 법 — 모호한 "안 돼요"의 위험성
  - 보안 관점 리뷰: 시크릿 하드코딩, 입력값 검증 누락, 권한 체크 누락 등 흔한 AI 생성 코드의 함정
  - 프롬프트 인젝션 개념: 외부 콘텐츠(웹페이지, 문서, 이메일)에 숨겨진 악성 지시가 에이전트를 조종하는 위험 — Claude Cowork처럼 브라우저·연동 앱까지 다루는 에이전트일수록 더 커지는 위험이므로 "검증 없이 실행 결과를 믿지 않는다"는 원칙은 코딩 에이전트에 국한되지 않는다는 것을 강조
  - 에이전트가 루프에 빠지거나 엉뚱한 방향으로 갈 때 개입하는 타이밍
- **실습**: 의도적으로 버그가 있는 프로젝트를 주고 고치게 한 뒤, "정말 고쳐졌는지" 학생이 직접 검증하는 미션

## 8차시. 확장 생태계 — Skills, Hooks, MCP

- **목표**: 반복 작업을 자동화하고 도구를 확장한다
- **내용**
  - Custom Skill(슬래시 커맨드)로 자주 쓰는 워크플로우 저장하기
  - Hooks로 규칙 강제하기 (예: 커밋 전 자동 테스트/린트 실행)
  - MCP(Model Context Protocol)로 외부 데이터/도구 연결 — 왜 이게 "USB-C for AI"로 불리는지
  - Subagent 심화: 역할을 분리해 병렬로 조사·구현 시키기
  - Skill·Connector·Plugin은 Claude Code와 Claude Cowork가 공유하는 확장 방식이다 — 단, Cowork는 `~/.claude`를 자동으로 읽지 않으므로 조직에서 두 환경 모두에 배포하려면 **Customize**에 별도 등록이 필요하다는 점을 팀 규칙에 반영
- **실습**: 팀에서 반복적으로 쓸 나만의 Skill 하나, Hook 하나 직접 제작

## 9차시. 자동화와 확장 — Headless 모드, CI 연동

- **목표**: 대화형을 넘어 파이프라인 안에 에이전트를 심는다
- **내용**
  - `claude -p` 헤드리스 모드로 스크립트/파이프라인에서 비대화형 실행
  - GitHub Actions 등 CI에서 PR 자동 리뷰/이슈 트리아지에 활용하는 사례
  - Claude Agent SDK 맛보기 — 나만의 도구를 가진 커스텀 에이전트로 확장하는 다음 단계 (다음 모듈인 Workflow Automation과 연결)
- **실습**: 간단한 헤드리스 스크립트 작성 (예: 커밋 메시지 자동 생성 CLI, 텍스트 파일 일괄 리팩터링)

## 10차시. 비용 전략과 팀 협업 규칙

- **목표**: 혼자 쓰는 도구에서 팀/조직 차원의 도구로 시야를 넓힌다
- **내용**
  - 모델 선택 기준 (가볍고 반복적인 작업 vs 복잡한 설계 작업) 및 `/cost`로 사용량 확인
  - 팀 단위 `CLAUDE.md` 컨벤션 통일, 코드 리뷰 문화(AI가 짠 코드도 사람이 리뷰) 유지하기
  - 과의존 경계하기 — 학습을 대체하지 않고 증폭시키는 도구로 쓰는 법
  - 라이선스/저작권 이슈 — 생성된 코드의 출처 확인 습관
- **실습**: 조별로 "우리 팀의 Claude Code 사용 가이드라인" 문서 작성

## 11차시. 캡스톤 — 실전 미니 프로젝트

- **목표**: 배운 모든 것(브리핑, CLAUDE.md, Plan Mode, Git 워크플로우, 검증, 자동화)을 통합
- **진행**
  - 개인/팀별 프로젝트 기획 (예: 개인 웹사이트, 자동화 CLI 도구, 간단한 API 서버)
  - `CLAUDE.md` 작성 → Plan Mode로 설계 → 구현 → 셀프 검증 → PR 히스토리로 정리
  - 5분 발표 + 동료 코드 리뷰
- **평가 기준**
  - 지시(브리핑)의 명확성
  - Plan Mode/diff 리뷰 등 승인 습관 준수 여부
  - Git 워크플로우(커밋 단위, PR 품질)
  - 결과물에 대한 자체 검증 여부 (테스트, 실제 실행 확인)

---

## 부록 A. 자주 쓰는 슬래시 명령 치트시트

| 명령 | 용도 |
|---|---|
| `/init` | 프로젝트 스캔 후 `CLAUDE.md` 초안 생성 |
| `/clear` | 대화 컨텍스트 완전 초기화 |
| `/compact` | 컨텍스트 요약 압축 (긴 세션 정리) |
| `/cost` | 현재 세션 토큰/비용 확인 |
| `/agents` | Subagent 목록/관리 |
| `/permissions` | 권한 모드 및 허용 목록 설정 |
| `/resume`, `--continue` | 이전 세션 이어가기 |

## 부록 B. Chat·Cowork·Claude Code 선택 기준

| 필요한 결과 | 먼저 선택할 환경 | 예시 |
|---|---|---|
| 답이나 아이디어 | Chat | 개념 설명, 아이디어 발산, 짧은 문장 다듬기 |
| 여러 앱을 넘나드는 완성된 업무 결과물 | Claude Cowork | 보고서 종합, 회의 준비, 반복 리포트, 파일 정리, 스프레드시트/발표자료 |
| 실행·테스트된 코드 변경 | Claude Code | 기능 구현, 버그 수정, 리팩터링, 코드 리뷰, PR |
| 업무 결과물과 코드가 모두 필요 | Cowork와 Claude Code 연결 | Cowork로 요구사항·자료 조사 → Claude Code로 구현·검증 → Cowork로 보고서·발표자료 작성 |

선택 기준은 도구 이름이 아니라 최종 산출물이다. 코드가 조금 섞여 있다는 이유만으로 Cowork에 개발을 맡기거나, 개발 프로젝트라는 이유만으로 모든 조사·문서 작업을 Claude Code에 맡기지 않는다.

**승인 모드 비교** (같은 원칙, 다른 표현)

| 구분 | Claude Code | Claude Cowork |
|---|---|---|
| 기본 | 매 변경마다 승인 | 자동 승인(위험 행동 사전 차단) |
| 자동화 | Accept Edits / Bypass | 모든 승인 건너뛰기 |
| 계획 우선 | Plan Mode | 작업 시작 시 계획 검토 후 실행 |
| 공통 안전장치 | 위험한 명령 앞에서 항상 확인 | 파일 삭제는 모든 모드에서 명시적 허락 필요 |

## 부록 C. 다른 도구와 비교 (선택 세션 또는 과제용)

- Claude Code vs Codex(`1. Agentic Coding/1. Codex`) — CLI 에이전트 간 비교, 도구 선택 안목
- Claude Code vs Cursor/Copilot — "채팅 보조" vs "자율 에이전트"의 실무 체감 차이
- 이후 모듈(Workflow Automation, Personal AI Agent)로 이어지는 다리: 헤드리스 모드 → n8n/Dify 연동, SDK → 커스텀 에이전트 개발

## 부록 D. 참고 영상 (보충 자료, 선택 시청)

- [2026년 클로드, 1시간 올인원 강의](https://www.youtube.com/watch?v=If_U_zmXWYo)
- [The Ultimate Beginner's Guide to Claude AI](https://www.youtube.com/watch?v=9oJySubZRSA)
- [Full Claude Code Tutorial for Non-Technical Beginners](https://www.youtube.com/watch?v=bqJzIWAEn40)
- [(1시간 모음집) 클로드 기초·코워크·디자인](https://www.youtube.com/watch?v=fFMnrauHlA4)

## 부록 E. 공식 참고 문서

- [Claude Code 공식 문서](https://code.claude.com/docs/en)
- [Claude Cowork 개요](https://claude.com/docs/cowork/overview)
- [Claude Cowork 시작하기](https://support.claude.com/en/articles/13345190-get-started-with-claude-cowork)
- [Claude Cowork 안전하게 사용하기](https://support.claude.com/en/articles/13364135-use-claude-cowork-safely)
- [Claude Cowork 제품 가이드](https://claude.com/blog/the-claude-cowork-product-guide)
- [Claude Cowork 웹/데스크톱/모바일 사용](https://support.claude.com/en/articles/15520349-use-claude-cowork-on-web-desktop-and-mobile)

## 강사용 참고

- 이 커리큘럼의 무게중심은 "만들기"보다 "안전하게 위임하고 검증하기"에 있다. 특히 4차시(Plan Mode)와 7차시(검증)는 시간을 줄이지 말 것.
- 비개발자 대상이라도 git/PR 흐름(6차시)을 생략하지 말 것 — 실무 도구로 자리잡으려면 협업 워크플로우 경험이 필수.
- 9~10차시는 조직 규모·수강생 배경에 따라 선택 심화 세션으로 조정 가능.
- Claude Cowork는 유료 플랜(Pro/Max/Team/Enterprise) 전용이자 베타로 계속 변하는 기능이 많다. 0차시 실습 시 계정이 없는 학생은 강사 데모 시청으로 대체하고, 세부 기능은 수업 직전 공식 문서로 재확인한다.
