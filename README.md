# Lee Jeongheon

`@colosair` · Web Platform · AI Application · Developer Tools

웹 플랫폼과 AI 응용 시스템, 개발자 도구를 구현해 왔습니다.
이곳에는 팀 프로젝트에서 담당한 개발 영역과 직접 배포한 소프트웨어의 설계·구현·검증 기록을 정리했습니다.

각 팀 프로젝트는 **개인 기여 기록**에서 팀 전체 결과와 본인 작업을 나누어 설명하고, 근거가 되는 PR·커밋·소스 파일로 연결합니다.

---

## Selected Team Projects

### SSAFESTA

`2026.08 – 2026.09` · 6인 팀 · SSAFY 15기 팀 프로젝트

Unity WebGL 월드 위에 React 오버레이를 얹은 메타버스 부스·전시 서비스입니다.

**역할** Frontend Main (Platform & Booth). 후반에는 통합 검증과 Production 승격 작업까지 직접 맡았습니다.

- React 프론트엔드 공통 구조와 Unity WebGL Host·Bridge 계층을 설계·구현
- FE·BE·Unity 사이 이벤트 계약을 맞추고, 로딩 병목·채팅 연결 끊김 같은 런타임 간 문제를 실측으로 진단
- 장애 대응 과정에서 Demo에서 검증한 산출물을 그대로 쓰는 Production 승격 경로를 만들고 main 승격 수행

[개인 기여 기록](projects/ssafesta.md) · [원본 저장소](https://github.com/mingleland/ssafesta)

### PinLog

`2026.07 – 2026.08` · 6인 팀 · SSAFY 15기 팀 프로젝트

장소를 방문 이유와 경험(Context)과 함께 기록하고, 자연어로 다시 찾는 장소 아카이빙 서비스입니다.

**역할** AI 파트 담당. 공용 API 명세 관리와 백엔드 AI 연동 구현을 함께 맡았습니다.

- FastAPI AI 서버의 비동기 처리 파이프라인·상태 전이, 임베딩·프리셋 키워드 판정 구현
- 개인 자연어 검색에 질의 재작성·키워드 재정렬·문자열 병합·LLM 관련도 재판정 신호를 단계적으로 추가
- 측정 도구로 임베딩·임계값·프롬프트 변경의 채택과 기각을 판단하고 결과를 PR로 기록

[개인 기여 기록](projects/pinlog.md) · [원본 저장소](https://github.com/Team-PinLog/PinLog)

### NoHome

`2026.06` · 3인 팀 · SSAFY 15기 1학기 관통 프로젝트 · 1학기 프로젝트 최우수상(팀)

서울 아파트 실거래가 조회 서비스에 AI 어시스턴트를 더한 웹 서비스입니다.

**역할** 팀장, AI 어시스턴트 담당. 팀 프로젝트 종료 후 개인 고도화로 서버 배포를 진행했습니다.

- AI 어시스턴트를 챗봇에서 Tool Calling 기반 단일 엔드포인트로 재설계해 조회 답변과 화면 조작을 분리
- 프론트엔드 필터 스키마와 AI가 쓸 수 있는 능력 목록을 테스트로 동기화
- (개인 고도화) 환경 설정을 분리하고 OCI ARM 서버에 Docker Compose·HTTPS로 배포

[개인 기여 기록](projects/nohome.md) · [팀 원본](https://github.com/repechage-team/no-home-backend) · [개인 고도화 저장소](https://github.com/no-home-project/no-home-docs)

### LINKLE

`2025.08 – 2025.09` · 5인 팀 · 신한DS 금융SW 아카데미 5기 팀 프로젝트

지도 위 장소에 사진과 메모를 남기고 같은 장소에 관심 있는 사람과 연결되는 지역 SNS입니다.

**역할** 팀장, 인증(FE·BE)·배포 담당.

- Spring Boot 인증: 이메일 인증 코드, BCrypt, JWT access·refresh, Redis 기반 refresh 검증, HttpOnly 쿠키
- React 인증 연동: 쿠키 기반 API 클라이언트, 탭 복귀 시 토큰 갱신(Focus-Refresh), 보호 라우트
- 로컬 HTTPS·CORS 환경 구성과 Docker 멀티스테이지·Nginx 배포

[개인 기여 기록](projects/linkle.md) · [Frontend](https://github.com/LINKLE-2025/LINKLE_Frontend) · [Backend](https://github.com/LINKLE-2025/LINKLE_Backend)

---

## Published Developer Tools

직접 설계·구현하고 npm에 배포한 도구입니다.

### ASC — Agent Session Control

여러 AI 코딩 에이전트 세션을 함께 운영할 때 세션마다 목표·완료 조건·쓰기 경계를 계약으로 주고, 소유권·공용 계약·비밀값·되돌릴 수 없는 작업에서만 사람의 승인을 거치게 하는 로컬 제어 계층입니다.

- 세션 계약과 작업 경계, 승인 경로, 발행과 실제 실행을 나눈 감사 기록
- `runtime`·`bootstrap` 두 패키지, 런타임 의존성 `zod` 하나, 계약 문서 C-01 ~ C-14
- 릴리스: **v0.10.2** (2026-09-14) · v0.1.0부터 태그 25개

[README](https://github.com/colosair/asc#readme) · [Releases](https://github.com/colosair/asc/releases) · [npm @asc-agent/runtime](https://www.npmjs.com/package/@asc-agent/runtime)

### JAM — Jira Agent MCP

Claude Code·Codex 같은 에이전트가 Jira를 읽고 쓰는 방식을 정책으로 고정한 MCP 서버입니다.

- 읽기 3단계(`jira_search` · `jira_context` · `jira_full`)와 결과마다 완전성·조회 범위를 알리는 `meta`
- 쓰기는 `jira_write_plan` → `jira_write_apply` → 재조회 확인 순서로만 실행
- 실제 사용 중 발견한 Windows 설치 결함(npx PATH 오염 등)을 v1.4.3에서 수정
- 릴리스: **v1.8.0** (2026-09-10) · v1.0.0부터 태그 17개

[README](https://github.com/colosair/jam#readme) · [Releases](https://github.com/colosair/jam/releases) · [npm @jam-mcp/server](https://www.npmjs.com/package/@jam-mcp/server)

---

## Earlier Work

| 프로젝트 | 기간 | 내용 | 역할 |
|---|---|---|---|
| [CardGarden](https://github.com/colosair/cardgarden) | 2025.06 – 2025.08 | 소비 패턴 기반 카드 추천 웹 서비스 (Spring·MyBatis·JSP) | 팀장, 회원 인증(이메일 인증·Kakao/Naver/Google OAuth2), 초기 구조, 배포 |
| [teacafe_POS](https://github.com/colosair/teacafe_POS) | 2025.05 | 프레임워크 없이 Java·JDBC로 만든 찻집 콘솔 POS | 개인 학습 프로젝트 |
| [DB Quiz](https://github.com/colosair/db-quiz) · [Spring Quiz](https://github.com/colosair/spring-quiz) | 2026.05 | SSAFY 과목평가 대비 모의고사 웹앱 (각 150문항, 즉시 채점·오답노트) | 개인 |
| [SQLP Tuning Mock](https://github.com/colosair/sqlp-tuning-mock) | 2026.07 – 2026.08 | SQLP 과목 III 대비 창작 모의문제 240문항 (CC BY 4.0) | 개인 |

---

## Background

**Education**

- SSAFY(삼성청년SW·AI아카데미) 15기 — 1학기 SW·AI 이론 및 실습 과정 이수 (2026.01 – 2026.06, 925시간)
- 신한DS 금융SW 아카데미 5기 (2025.04 – 2025.10)

**Awards**

- 1학기 프로젝트 최우수상 (팀, NoHome) — 삼성청년SW·AI아카데미, 2026.06
- 1학기 성적우수상 (개인, 종합성적 반 3등) — 삼성청년SW·AI아카데미, 2026.06

**Certifications**

- 정보처리기사 (2025.09)
- SQL 개발자 SQLD (2024.09)
- 데이터분석 준전문가 ADsP (2024.09)

---

## Index

| 구분 | 링크 |
|---|---|
| 개인 기여 기록 | [SSAFESTA](projects/ssafesta.md) · [PinLog](projects/pinlog.md) · [NoHome](projects/nohome.md) · [LINKLE](projects/linkle.md) |
| 팀 프로젝트 원본 | [mingleland/ssafesta](https://github.com/mingleland/ssafesta) · [Team-PinLog/PinLog](https://github.com/Team-PinLog/PinLog) · [repechage-team](https://github.com/repechage-team) · [LINKLE-2025](https://github.com/LINKLE-2025) |
| 개인 제품 | [colosair/asc](https://github.com/colosair/asc) · [colosair/jam](https://github.com/colosair/jam) |
| 개인 고도화 | [no-home-project](https://github.com/no-home-project) |
