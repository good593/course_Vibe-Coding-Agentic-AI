# ChatGPT Work·Codex 기능 실전 커리큘럼

> 기획자는 **ChatGPT Work의 기능을 폭넓게 실습**하고, 웹개발자는 **Codex의 기능을 개발 워크플로우에 통합**한다.

이 강의의 주제는 기획 방법론이나 웹개발 방법론 자체가 아니라 **ChatGPT Work와 Codex를 제대로 사용하는 방법**이다. 기획자와 웹개발자는 기능을 현실적인 맥락에서 연습하기 위한 대표 사용자다.

| 구분 | 트랙 A. 기획자를 위한 ChatGPT Work | 트랙 B. 웹개발자를 위한 Codex |
|---|---|---|
| 핵심 질문 | Work로 어떤 업무 결과물과 워크플로우를 만들 수 있는가? | Codex로 개발의 어느 단계까지 안전하게 위임할 수 있는가? |
| 기능·직무 비중 | Work 기능 70% + 기획 업무 시나리오 30% | Codex 기능 70% + 웹개발 시나리오 30% |
| 분량 | 12차시 × 2시간, 총 24시간 | 16차시 × 2~3시간, 총 약 40시간 |
| 최종 결과 | Work의 주요 기능을 연결한 제품 기획 워크스페이스 | Codex의 주요 기능을 연결한 검증 가능한 웹 기능과 PR |

## 기능 실습 등급

| 등급 | 의미 | 운영 방식 |
|---|---|---|
| **핵심** | 대부분의 수강생이 직접 사용해야 하는 기능 | 전원 실습 |
| **조건부** | 계정·운영체제·조직 정책·지역에 따라 제공 범위가 달라질 수 있는 기능 | 사용 가능하면 실습, 아니면 강사 데모 |
| **고급** | 확장·자동화·플랫폼 개발에 해당하는 기능 | 짧은 구현 또는 구조 이해 중심 |
| **통합** | 앞 차시에서 익힌 여러 기능을 하나의 작업 흐름으로 연결하는 단계 | 캡스톤 결과와 실행 증거로 평가 |

> [!NOTE]
> 이 문서는 2026-09-02 기준 공식 OpenAI 문서를 바탕으로 구성했다. 기능과 명령은 빠르게 바뀔 수 있으므로 수업 직전 [기능 목록](https://learn.chatgpt.com/docs/features), [Work 시작하기](https://learn.chatgpt.com/docs/get-started-with-work), [Codex 문서](https://learn.chatgpt.com/docs/codex/cli)를 다시 확인한다.

## 공통 실습 프로젝트

두 트랙은 `동네 클래스 예약 서비스`라는 가상 제품을 사용한다.

- 기획자: 고객 피드백, 설문, 회의록, 경쟁사 자료로 PRD·우선순위·발표자료·대시보드를 만든다.
- 웹개발자: 기획 산출물과 기존 저장소를 바탕으로 예약 기능을 구현·테스트·리뷰·자동화한다.
- 각 차시는 새로운 기능을 최소 하나 직접 조작하고, 결과와 한계를 기록한다.
- 모든 실습은 **기능 선택 → 권한 확인 → 실행 → 결과 검토 → 미검증 항목 기록**으로 끝낸다.
- 실제 개인정보, 운영 데이터, API 키, 회사 비밀자료는 사용하지 않는다.
- 조건부 기능을 사용할 수 없는 수강생에게는 강사 데모와 같은 목표의 대체 실습을 제공한다.

---

## 트랙 A. 기획자를 위한 ChatGPT Work 기능 실전

### 수료 기준

수료한 학습자는 다음 Work 기능을 목적에 맞게 연결해 사용할 수 있어야 한다.

- Chat과 Work, 웹과 데스크톱, 로컬과 클라우드 작업을 구분한다.
- Projects와 Chats로 자료와 작업을 지속적으로 관리한다.
- Goal과 Plan Mode로 장기 작업의 목표·단계·중단 지점을 통제한다.
- 파일·폴더·이미지·Appshot·음성·웹을 입력 컨텍스트로 제공한다.
- Documents·PDF·Spreadsheets·Presentations 기능으로 편집 가능한 파일을 만든다.
- Visualizations와 Sites로 분석 결과와 기획 내용을 상호작용 가능한 결과물로 표현한다.
- Plugins·Browser·Computer use로 연결된 자료와 앱을 사용하되 승인 범위를 판단한다.
- Skills·Record & Replay로 반복 절차를 재사용한다.
- Scheduled tasks·Notifications·Long-running work·Subagents로 반복·장기 업무를 운영한다.

### 사전 준비물

- ChatGPT Work를 사용할 수 있는 계정
- 웹 브라우저와 ChatGPT 데스크톱 앱을 사용할 수 있는 PC
- 문서·PDF·CSV·스프레드시트·발표자료를 열 수 있는 환경
- 강사가 제공하는 가상 제품 자료 묶음
- 선택: Google Drive, Gmail, 캘린더 등 조직에서 승인한 Plugin

### Work 기능 커버리지

| 기능 영역 | 실습 기능 | 차시 |
|---|---|---|
| 작업 공간 | Work mode, Projects, Chats, 검색, 고정, 작업 이력 | A0 |
| 실행 제어 | Goal, Plan Mode, 모델·추론 수준, 방향 수정, 승인 | A1 |
| 컨텍스트 | 파일·폴더, 이미지 입력, Appshots, 음성, 로컬 컨텍스트 | A2 |
| 조사 | Web search, Browser, 출처 확인, Long-running work, Subagents | A3 |
| 문서 | Documents, PDF 읽기·생성·편집·검증 | A4 |
| 데이터 | Spreadsheets, 수식·표·차트, Visualizations | A5 |
| 프레젠테이션 | Presentations, Template Creator, 이미지 생성 | A6 |
| 연결 | Plugins, 도구 선택, 인증, 권한, 외부 읽기·쓰기 | A7 |
| 컴퓨터 작업 | Desktop app, Browser extension, Computer use, 로컬 앱 | A8 |
| 인터랙티브 결과 | Sites, 대시보드, 프로토타입, 공유 전 검토 | A9 |
| 재사용·자동화 | Skills, Record & Replay, Scheduled tasks, Notifications | A10 |
| 통합 | 위 기능 중 7개 이상 연결 | A11 |

### 전체 과정

| 차시 | 등급 | 기능 중심 주제 | 직접 조작할 기능 | 기획자 실습과 산출물 |
|---:|---|---|---|---|
| A0 | 핵심 | Work 시작과 작업 공간 | Work mode, Projects, Chats, 웹·데스크톱 | 프로젝트 생성, 자료 배치, Chat과 Work 결과 비교 |
| A1 | 핵심 | 목표·계획·실행 제어 | Goal, Plan Mode, 모델·추론 수준, 승인 | 제품 조사 목표와 단계·중단 조건 설정 |
| A2 | 핵심·조건부 | 멀티모달 컨텍스트 | 파일·폴더, 이미지, Appshot, 음성 | 회의록·화면 캡처·설문 파일을 하나의 컨텍스트로 구성 |
| A3 | 핵심·조건부 | 조사와 장기 작업 | Web search, Browser, Long-running work, Subagents | 시장·경쟁사 조사와 근거표 생성 |
| A4 | 핵심 | 문서와 PDF | Documents, PDF Plugin | 조사 결과로 PRD 작성, PDF 내보내기·재검증 |
| A5 | 핵심 | 스프레드시트와 시각화 | Spreadsheets, Visualizations | 설문 분석, 우선순위 점수, 차트와 대시보드 작성 |
| A6 | 핵심 | 발표자료와 이미지 | Presentations, Template Creator, Image generation | 의사결정용 덱과 제품 콘셉트 이미지 생성 |
| A7 | 조건부 | Plugins와 연결 서비스 | Plugin 탐색·설치·호출, 읽기·쓰기 승인 | Drive·메일·일정에서 자료를 모아 실행 항목 생성 |
| A8 | 조건부 | 브라우저와 컴퓨터 사용 | Browser, Browser extension, Computer use, 로컬 앱 | 경쟁 서비스 흐름 관찰과 회의 후속 작업 처리 |
| A9 | 조건부 | Sites로 결과 공유 | Sites, 파일·데이터 연결, 미리보기 | 제품 현황 대시보드 또는 내부 기획 사이트 제작 |
| A10 | 조건부 | Skill과 예약 자동화 | Skills, Record & Replay, Scheduled tasks, Notifications | 주간 제품 업데이트를 Skill과 예약 작업으로 구성 |
| A11 | 통합 | Work 캡스톤 | 기능 7개 이상 통합 | 조사 → 분석 → PRD → 덱 → 사이트 → 정기 업데이트 완성 |

### 차시별 실습 포인트

#### A0. Work mode·Projects·Chats

- Chat에서 짧은 답을 받고 Work에서 검토 가능한 결과물을 만드는 차이를 직접 비교한다.
- 새 Project를 만들고 제품 설명서, 인터뷰, 설문을 추가한다.
- 하나의 Chat을 하나의 완료 목표에 연결하고 새 작업을 별도 Chat으로 분리한다.
- 웹과 데스크톱 앱에서 동일 프로젝트를 열어 사용 가능한 기능 차이를 기록한다.

#### A1. Goal·Plan Mode·모델·승인

- 장기 목표를 만들고 완료 조건과 계속 진행할 조건을 지정한다.
- Plan Mode에서 자료, 단계, 예상 산출물, 질문, 승인 지점을 먼저 검토한다.
- 작업 복잡도에 따라 모델과 추론 수준을 선택하고 비용·속도 차이를 기록한다.
- 계획을 승인한 뒤 중간 결과에서 방향을 수정하거나 작업을 중단한다.

#### A2. Files·Folders·Image inputs·Appshots·Voice

- 개별 파일과 폴더를 추가하고 Work가 실제로 읽은 자료를 확인한다.
- 화면 캡처와 Appshot을 제공해 UI 문제를 설명하게 한다.
- 음성으로 회의 메모를 입력한 뒤 구조화된 회의록으로 변환한다.
- 서로 충돌하는 자료를 넣고 출처별 차이와 미확인 사항을 표시하게 한다.

#### A3. Web search·Browser·Long-running work·Subagents

- 검색 범위, 기준일, 허용 출처, 인용 방식을 지정해 웹 조사를 실행한다.
- Browser로 원문을 열어 검색 결과와 실제 내용을 대조한다.
- 큰 조사를 경쟁사·사용자·시장 관점의 Subagent로 나누고 결과를 통합한다.
- Long-running work의 진행 상태를 확인하고 중간에 질문·수정 지시를 전달한다.

#### A4. Documents·PDF

- Documents 기능으로 제목·본문·표·결정 사항이 포함된 PRD를 만든다.
- 기존 문서를 열어 특정 절만 수정하고 변경된 내용을 검토한다.
- PDF 자료를 읽어 근거를 추출하고, 최종 문서를 PDF로 만든 뒤 다시 열어 누락·깨짐을 확인한다.

#### A5. Spreadsheets·Visualizations

- CSV와 스프레드시트를 불러와 정리·수식·분류 작업을 수행한다.
- 우선순위 계산식과 원본 데이터가 맞는지 표본 행으로 검산한다.
- 차트와 Visualization을 만들고 필터·범례·단위·정렬을 검토한다.
- 같은 데이터에서 의사결정에 유리한 표현과 왜곡될 수 있는 표현을 비교한다.

#### A6. Presentations·Template Creator·Image generation

- 기존 템플릿을 기반으로 발표자료를 만들고 레이아웃 일관성을 확인한다.
- PRD와 스프레드시트를 근거로 5장 의사결정 덱을 생성한다.
- 제품 콘셉트 이미지를 만들고 실제 제품 화면으로 오해되지 않도록 표시한다.
- 슬라이드의 수치와 주장이 원본 자료와 일치하는지 역검증한다.

#### A7. Plugins

- Plugin 목록에서 필요한 연결을 찾고 설명·권한·읽기·쓰기 범위를 확인한다.
- `@Plugin`으로 특정 데이터 소스를 명시해 호출한다.
- Drive·메일·캘린더 등 여러 소스의 정보를 하나의 결과물로 통합한다.
- 메시지 발송·일정 생성·파일 저장 같은 외부 쓰기는 초안 검토와 승인 후 실행한다.

#### A8. Browser·Computer use·Browser extension

- 웹페이지를 직접 열어 흐름을 관찰하고 화면별 메모를 작성한다.
- 브라우저 확장으로 현재 페이지를 Work의 컨텍스트에 연결한다.
- 데스크톱 앱에서 로컬 파일·앱·브라우저를 사용하는 작업을 수행한다.
- 로그인, 결제, 삭제, 게시처럼 되돌리기 어려운 행동은 실행 직전 멈추게 한다.

#### A9. Sites

- PRD·일정·지표를 사용하는 내부 제품 사이트 또는 대시보드를 만든다.
- 표·차트·문서와 상호작용 요소를 한 화면에 연결한다.
- 대상 독자, 데이터 최신성, 공유 범위, 모바일 화면을 확인한다.
- 배포나 공유 전 샘플 데이터와 실제 데이터를 구분한다.

#### A10. Skills·Record & Replay·Scheduled tasks·Notifications

- 반복한 제품 업데이트 절차를 Record & Replay 또는 Skill로 저장한다.
- Skill의 입력, 단계, 출력, 중단 조건, 사용하지 말아야 할 상황을 정의한다.
- 예약 작업을 만들고 실행 주기, 사용 자료, 연결 도구, 승인 정책을 설정한다.
- Scheduled 화면과 Notifications에서 성공·실패·미확인 실행을 검토한다.

### A11. Work 캡스톤

다음 기능 중 7개 이상을 사용해 하나의 제품 기획 워크스페이스를 완성한다.

- Projects·Chats
- Goal·Plan Mode
- Files·Folders·Image inputs·Appshots
- Web search·Browser
- Documents·PDF
- Spreadsheets·Visualizations
- Presentations·Image generation
- Plugins·Computer use
- Sites
- Skills·Scheduled tasks·Notifications
- Long-running work·Subagents

**필수 증거**

- 기능별 사용 목적과 선택 이유
- 입력 자료와 출처 목록
- 생성한 문서·표·덱·사이트
- Plugin 권한과 외부 쓰기 승인 기록
- Scheduled task 또는 Skill 실행 결과
- 오류, 미검증 항목, 사람이 수정한 내용

**평가 기준**: 기능 활용 35%, 결과물 품질 20%, 출처·검증 20%, 권한·안전 15%, 재사용·자동화 10%

---

## 트랙 B. 웹개발자를 위한 Codex 기능 실전

> 차시별 슬라이드와 실습 자료: [`2. codex/README.md`](2.%20codex/README.md)

### 수료 기준

수료한 학습자는 다음 Codex 기능을 개발 흐름에 맞게 사용할 수 있어야 한다.

- Desktop app·CLI·IDE extension·Cloud·Remote의 차이를 알고 전환한다.
- CLI 명령, Slash commands, 이미지 입력, 웹 검색, 세션 재개 기능을 사용한다.
- Local·Worktree·Cloud 모드에서 격리 수준과 적용 방식을 선택한다.
- Plan Mode·Goals·Context·Compaction·모델·추론 수준을 제어한다.
- `AGENTS.md`·`config.toml`·Profiles·Rules·Feature flags를 구성한다.
- Sandbox·Approvals·Internet access·Writable roots를 최소 권한으로 운영한다.
- 통합 터미널에서 구현·테스트·빌드·디버깅을 반복한다.
- Code review·Auto-review와 GitHub·GitLab·Slack·Linear 연동을 활용한다.
- Skills·Plugins·MCP·WebMCP·Hooks로 기능을 확장한다.
- Subagents·Custom agents·Worktrees로 병렬 작업을 설계한다.
- `codex exec`·GitHub Action·SDK·App Server·MCP Server의 역할을 구분한다.

### 사전 준비물

- HTML·CSS·JavaScript, HTTP, Git 기본 지식
- React·Vue·Svelte 또는 Node.js·Python·Java 웹 프로젝트 경험
- Codex CLI, Git, `gh`, 프로젝트 런타임을 설치할 수 있는 PC
- VS Code 또는 호환 IDE와 ChatGPT 데스크톱 앱
- GitHub 계정과 실습용 저장소
- Windows 수강생은 Windows sandbox 또는 WSL 환경을 사전 점검

### Codex 기능 커버리지

| 기능 영역 | 실습 기능 | 차시 |
|---|---|---|
| 실행 표면 | Desktop app, CLI, IDE extension, Cloud, Remote | B0~B4 |
| CLI | Slash commands, resume, image, search, completion, status | B1 |
| IDE | 열린 파일·선택 영역, 이미지, diff, 모델·권한, Cloud 위임 | B2 |
| 앱 | Projects, Chats, multi-repo, integrated terminal, local changes | B3 |
| 환경 | Local, Worktree, Cloud, handoff, remote control | B4 |
| 실행 제어 | Prompting, Plan Mode, Goals, models, reasoning, compact | B5 |
| 사용자화 | `AGENTS.md`, config, Profiles, Rules, feature flags | B6~B7 |
| 보안 | Sandbox, approvals, internet, writable roots, secrets | B8 |
| 개발 루프 | 편집, 명령, 이미지·웹 컨텍스트, 브라우저 검증, 테스트 | B9~B10 |
| 리뷰·협업 | Code review, Auto-review, GitHub·GitLab·Slack·Linear | B11 |
| 확장 | Skills, Plugins, MCP, WebMCP | B12 |
| 병렬화 | Subagents, Custom agents, Worktrees | B13 |
| 자동화 | Hooks, `codex exec`, JSONL, schema, GitHub Action | B14 |
| 플랫폼 | Codex SDK, App Server, MCP Server | B14 고급 데모 |
| 통합 | 위 기능 영역 중 10개 이상 연결 | B15 |

### 전체 과정

| 차시 | 등급 | 기능 중심 주제 | 직접 조작할 기능 | 웹개발자 실습과 산출물 |
|---:|---|---|---|---|
| B0 | 핵심 | Codex 제품 지도 | App, CLI, IDE, Cloud, Remote | 같은 작업을 표면별로 배치한 선택표 |
| B1 | 핵심 | CLI 완전 입문 | 설치, Slash commands, resume, image, search, completion | 저장소 설명·검색·이미지 기반 첫 수정 |
| B2 | 핵심 | IDE 확장 | 파일·선택 영역 컨텍스트, diff, 모델·권한, Cloud 위임 | 선택 코드 리팩터링과 변경 검토 |
| B3 | 핵심·조건부 | 데스크톱 앱 | Projects, Chats, multi-repo, integrated terminal | 프런트·백 저장소를 연결한 작업 |
| B4 | 조건부 | 실행 환경과 Worktree | Local, Worktree, Cloud, handoff, Remote | 병렬 기능·버그 작업과 결과 적용 |
| B5 | 핵심 | 프롬프트와 실행 제어 | Plan Mode, Goals, model, reasoning, compact | PRD를 계획하고 긴 작업을 안정적으로 수행 |
| B6 | 핵심 | `AGENTS.md` | 전역·저장소·하위 지침, override, review rules | 웹 저장소 작업 계약 작성·검증 |
| B7 | 핵심 | 설정·Profiles·Rules | `config.toml`, Profiles, Rules, feature flags | 개발·리뷰·자동화 프로필 구성 |
| B8 | 핵심 | 권한과 보안 | Sandbox, approvals, internet, writable roots | 의존성 설치·외부 접근·삭제 요청 통제 |
| B9 | 핵심·조건부 | 프런트엔드 에이전트 루프 | image, search, browser tools, terminal, visual checks | 반응형 UI 구현과 화면 검증 |
| B10 | 핵심 | 백엔드·테스트·디버깅 | terminal, logs, unit·integration·E2E | API 버그 재현·수정·회귀 테스트 |
| B11 | 핵심·조건부 | 리뷰와 협업 | `/review`, Auto-review, GitHub·GitLab·Slack·Linear | PR 생성·리뷰·코멘트 반영 |
| B12 | 핵심·고급 | Skills·Plugins·MCP | Skill, Plugin, MCP, WebMCP | PR 검증 Skill과 읽기 전용 도구 연결 |
| B13 | 핵심·조건부 | Subagents·Custom agents | 병렬 위임, agent config, Worktrees | 탐색·테스트·보안 리뷰 병렬 수행 |
| B14 | 고급 | Hooks와 자동화·플랫폼 | Hooks, `codex exec`, JSONL, schema, Action, SDK | 자동 검증 파이프라인과 플랫폼 데모 |
| B15 | 통합 | Codex 캡스톤 | 기능 영역 10개 이상 통합 | 검증된 수직 웹 기능과 PR |

### 차시별 실습 포인트

#### B0. Desktop app·CLI·IDE·Cloud·Remote

- 동일한 버그 수정 요청을 각 실행 표면에서 어떻게 처리하는지 비교한다.
- 로컬 도구가 필요한 작업, 편집기 중심 작업, 격리·장기 작업을 구분한다.
- 기능 가용성, 계정, 운영체제, 조직 정책 차이를 확인한다.

#### B1. Codex CLI

- CLI를 설치하고 로그인한 뒤 프로젝트 디렉터리에서 시작한다.
- App과 CLI에서 `/status`, `/model`, `/plan`, `/review`, `/compact`, `/mcp`, `/permissions`, `/agent` 중 현재 실행 화면에 제공되는 명령을 확인하고 사용한다.
- Slash command는 실행 화면과 접근 권한에 따라 다르므로, 명령 이름을 암기하기보다 `/` 목록과 공식 레퍼런스를 확인하는 습관을 익힌다.
- `codex resume`, `codex --image`, `codex --search`, `codex completion`을 실습한다.
- 작업 전후 Git 체크포인트와 diff를 확인한다.

#### B2. IDE extension

- 열린 파일과 선택 영역을 명시적 컨텍스트로 전달한다.
- 오류 화면이나 디자인 이미지를 입력하고 관련 코드만 수정한다.
- IDE에서 모델·추론 수준·권한을 확인하고 diff를 검토한다.
- 큰 작업은 Cloud로 위임하고 결과를 다시 에디터에서 확인한다.

#### B3. ChatGPT desktop app

- 웹 프로젝트를 Project로 열고 기능별 Chat을 분리한다.
- 프런트엔드와 백엔드 등 여러 저장소를 하나의 작업 맥락에서 다룬다.
- Integrated terminal로 개발 서버·테스트·lint를 실행한다.
- 파일 변경과 명령 기록, 최종 diff를 앱에서 검토한다.

#### B4. Local·Worktree·Cloud·Remote

- Local에서 현재 작업 트리를 사용하고 Worktree에서 독립 작업을 시작한다.
- 여러 Worktree Chat으로 기능 구현과 버그 조사를 분리한다.
- 긴 작업을 Cloud에 맡기고 결과를 검토한 뒤 로컬에 적용한다.
- Handoff와 Remote 사용 시 코드와 실행 위치가 어디에 남는지 확인한다.

#### B5. Plan Mode·Goals·Models·Context

- 목표·범위·제약·완료 기준·보고 형식이 포함된 개발 브리핑을 작성한다.
- Plan Mode에서 영향 파일, API 계약, 테스트, 데이터 변경, 롤백을 검토한다.
- Goal로 장기 리팩터링의 완료 조건과 계속 진행 기준을 설정한다.
- `/model`, 추론 수준, Fast mode를 비교하고 `/compact`와 새 Chat 분리 기준을 익힌다.

#### B6. `AGENTS.md`

- `/init`으로 초안을 만든 뒤 실제 명령과 규칙으로 수정한다.
- 전역, 저장소 루트, 하위 디렉터리, `AGENTS.override.md`의 적용 순서를 확인한다.
- 빌드·테스트 명령, 코드 스타일, 금지 사항, 완료 조건을 작성한다.
- `## Code Review Rules`에 웹 보안·접근성·회귀 기준을 추가한다.

#### B7. `config.toml`·Profiles·Rules·Feature flags

- 모델, 추론 수준, 샌드박스, 승인 정책, MCP 기본값을 구성한다.
- 개발·읽기 전용 리뷰·CI용 Profile을 나눈다.
- 허용·차단할 명령을 Rules로 정의하고 동작을 확인한다.
- 안정·베타·실험 기능의 maturity를 확인하고 feature flag를 안전하게 사용한다.

#### B8. Sandbox·Approvals·Internet access

- `read-only`, `workspace-write`, `danger-full-access`의 차이를 실습한다.
- writable roots와 작업 디렉터리를 확인한다.
- 패키지 설치·네트워크·외부 서비스 쓰기에서 승인 요청을 읽는다.
- 비밀값, 운영 DB, 강제 push, 재귀 삭제 요청을 안전한 계획으로 바꾼다.

#### B9. 프런트엔드 구현

- 스크린샷·디자인 이미지·웹 검색을 컨텍스트로 사용한다.
- 기존 컴포넌트와 디자인 토큰을 탐색해 재사용한다.
- 정상·로딩·빈 상태·오류·권한 상태와 반응형 UI를 구현한다.
- 브라우저와 스크린샷으로 시각·접근성·상호작용을 확인한다.

#### B10. 백엔드·테스트·디버깅

- API·서비스·DB 흐름과 인증·인가 경계를 추적한다.
- 통합 터미널에서 최소 재현, 로그, 단위·통합·E2E 테스트를 실행한다.
- 실패 원인 가설을 세우고 최소 수정과 회귀 테스트로 검증한다.
- 종료 코드, 전체 로그, diff, 미검증 항목을 최종 보고에 포함한다.

#### B11. Code review·Auto-review·통합

- `/review`로 미커밋 변경, 커밋, 기준 브랜치를 각각 리뷰한다.
- Auto-review와 `AGENTS.md`의 리뷰 규칙을 연결한다.
- GitHub 또는 GitLab에서 PR을 만들고 리뷰 결과를 반영한다.
- 사용 가능한 환경에서는 Slack·Linear 등과 개발 상태·이슈 흐름을 연결한다.

#### B12. Skills·Plugins·MCP·WebMCP

- 반복 검증 절차를 `SKILL.md`, `scripts/`, `references/`, `assets/`로 구성한다.
- `/skills`와 `$skill-name`으로 명시 호출하고 설명 기반 자동 선택을 확인한다.
- Plugin을 탐색·설치하고 Skill과 도구 의존성이 어떻게 함께 제공되는지 확인한다.
- `codex mcp add/list/login`과 `/mcp`로 읽기 전용 도구를 연결한다.
- WebMCP를 포함한 외부 도구의 출처·인증·쓰기 범위·프롬프트 인젝션 위험을 검토한다.

#### B13. Subagents·Custom agents·Worktrees

- 탐색·테스트 설계·보안·접근성 리뷰를 독립 Subagent에 맡긴다.
- `/agent`로 스레드 상태를 확인하고 결과를 메인 Chat에서 통합한다.
- `.codex/agents/`에 역할·모델·추론·샌드박스가 다른 Custom agent를 정의한다.
- 쓰기 작업은 Worktree로 격리하고 같은 파일을 동시에 수정하지 않는다.
- 단일 에이전트 대비 시간·토큰·조정 비용을 비교한다.

#### B14. Hooks·`codex exec`·GitHub Action·SDK

- `/hooks`로 Hook 출처와 신뢰 상태를 확인하고 `PreToolUse`, `PostToolUse`, `Stop` 흐름을 실습한다.
- `codex exec`의 읽기 전용 기본값과 `--json`, `--output-schema`를 사용한다.
- GitHub Action에서 저장소 코드와 장기 비밀값을 분리하고 실패 폐쇄로 설계한다.
- 고급 데모로 Codex SDK, App Server, MCP Server의 역할과 사용 시점을 비교한다.

### B15. Codex 캡스톤

다음 기능 영역 중 10개 이상을 사용해 작은 수직 웹 기능을 완성한다.

- CLI·IDE·Desktop app·Cloud 중 2개 이상
- Local·Worktree·Cloud 중 2개 이상
- Plan Mode 또는 Goal
- `AGENTS.md`와 설정·Profile·Rule 중 하나 이상
- Sandbox와 승인 판단
- 이미지 또는 웹 검색 컨텍스트
- 통합 터미널과 테스트
- Code review와 GitHub PR
- Skill·Plugin·MCP 중 하나 이상
- Subagent 또는 Custom agent
- Hook 또는 `codex exec`·GitHub Action

**필수 증거**

- 기능별 사용 목적과 선택 이유
- 기술 브리핑, 계획, `AGENTS.md`
- 의미 단위 커밋과 PR
- 테스트·브라우저·로그·diff 결과
- Subagent·Skill·MCP·Hook·자동화 실행 기록
- 권한·보안·비용·미검증 항목
- Codex의 잘못된 가정과 사람이 개입한 근거

**평가 기준**: 기능 활용 30%, 구현 품질 20%, 검증 품질 25%, 권한·보안 10%, Git·리뷰 10%, 회고 5%

---

## 두 트랙의 연결

| 기획자 Work 산출물 | 웹개발자 Codex 작업 |
|---|---|
| 사용자 조사 문서·PDF | 구현 범위와 위험 탐색 |
| 우선순위 Spreadsheet·Visualization | 기술 작업 분해와 의존성 분석 |
| PRD와 화면 Appshot | UI·API·데이터 구현과 테스트 |
| Sites 대시보드 | 분석 이벤트와 운영 화면 구현 |
| Scheduled 제품 업데이트 | `codex exec`·GitHub Action 자동 검증 |
| Work의 Subagent 조사 결과 | Codex Subagent의 기술 교차 검증 |

공동 프로젝트의 목적은 두 제품을 억지로 하나로 합치는 것이 아니라, **Work가 만든 검토 가능한 업무 결과물이 Codex의 검증 가능한 코드 변경으로 이어지는 흐름**을 경험하는 것이다.

## 강사용 기능 운영 체크리스트

- 각 차시 시작 시 계정에서 기능이 보이는지와 maturity를 확인한다.
- 조건부 기능은 대체 과제와 화면 녹화를 준비한다.
- 기능 설명보다 학생이 직접 만든 Project·Chat·파일·diff·실행 기록을 평가한다.
- 외부 쓰기, 결제, 게시, 삭제, 배포는 시뮬레이션 또는 별도 승인 단계로 운영한다.
- 모델명·요금·정확한 명령은 고정 암기시키지 않고 현재 UI와 공식 문서에서 찾게 한다.
- 캡스톤은 기능 개수만 세지 않고 기능을 선택한 이유와 검증 근거를 함께 본다.

## 공식 참고 문서

### ChatGPT Work

- [ChatGPT 기능 목록](https://learn.chatgpt.com/docs/features)
- [ChatGPT Work 시작하기](https://learn.chatgpt.com/docs/get-started-with-work)
- [Projects와 Chats](https://learn.chatgpt.com/docs/projects)
- [Sites](https://learn.chatgpt.com/docs/sites)
- [Visualizations](https://learn.chatgpt.com/docs/visualizations)
- [Scheduled tasks](https://learn.chatgpt.com/docs/automations)
- [Long-running work](https://learn.chatgpt.com/docs/long-running-work)
- [Notifications](https://learn.chatgpt.com/docs/notifications)
- [ChatGPT 데스크톱 앱](https://learn.chatgpt.com/docs/app)

### Codex

- [Codex CLI](https://learn.chatgpt.com/docs/codex/cli)
- [Slash commands](https://learn.chatgpt.com/docs/reference/slash-commands)
- [Codex IDE 확장](https://learn.chatgpt.com/docs/codex/ide)
- [Codex 클라우드](https://learn.chatgpt.com/docs/cloud)
- [Codex 실행 모드](https://learn.chatgpt.com/docs/environments/modes)
- [Git Worktrees](https://learn.chatgpt.com/docs/environments/git-worktrees)
- [`AGENTS.md`](https://learn.chatgpt.com/docs/agent-configuration/agents-md)
- [설정 기초](https://learn.chatgpt.com/docs/config-file/config-basic)
- [샌드박스](https://learn.chatgpt.com/docs/sandboxing)
- [승인과 보안](https://learn.chatgpt.com/docs/agent-approvals-security)
- [Code review](https://learn.chatgpt.com/docs/code-review)
- [Skills](https://learn.chatgpt.com/docs/build-skills)
- [MCP](https://learn.chatgpt.com/docs/extend/mcp)
- [Hooks](https://learn.chatgpt.com/docs/hooks)
- [Subagents](https://learn.chatgpt.com/docs/agent-configuration/subagents)
- [`codex exec`](https://learn.chatgpt.com/docs/non-interactive-mode)
- [Codex GitHub Action](https://learn.chatgpt.com/docs/github-action)
