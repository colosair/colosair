# 이정헌 (Lee Jeongheon)

Web Platforms · AI Applications · Developer Tools

팀 프로젝트에서 웹 플랫폼 통합, AI 서버, 인증과 배포를 맡았고 AI 코딩 에이전트용 개발 도구 두 개를 npm에 배포했습니다. 프로젝트별 담당 범위와 근거 코드는 각 개인 기여 기록에 정리했습니다.

[Projects](#selected-projects) · [Engineering](#engineering) · [Developer Tools](#published-developer-tools) · [Background](#earlier-work--background)

## Selected Projects

<p align="center">
<a href="projects/ssafesta.md"><img src="assets/featured/ssafesta-tile.webp" width="350" alt="SSAFESTA 로그인 화면 — 개인 기여 기록으로 이동"></a>
<a href="projects/pinlog.md"><img src="assets/featured/pinlog-tile.webp" width="350" alt="PinLog 자연어 검색 화면 — 개인 기여 기록으로 이동"></a><br>
<a href="projects/nohome.md"><img src="assets/featured/nohome-tile.webp" width="350" alt="NoHome 실거래가 검색과 AI 도우미 화면 — 개인 기여 기록으로 이동"></a>
<a href="projects/linkle.md"><img src="assets/featured/linkle-tile.webp" width="350" alt="LINKLE 지도와 장소 정보 화면 — 개인 기여 기록으로 이동"></a>
</p>

1. **[SSAFESTA](projects/ssafesta.md)** — React·Unity 통합, 통합 검증과 Production 승격 · Frontend Main, 6인
2. **[PinLog](projects/pinlog.md)** — FastAPI AI 처리 파이프라인과 자연어 검색 품질 개선 · AI 파트, 6인
3. **[NoHome](projects/nohome.md)** — Tool Calling 기반 AI 어시스턴트와 개인 배포 · 팀장, 3인 · 최우수상(팀)
4. **[LINKLE](projects/linkle.md)** — FE·BE 인증 구조와 Docker·Nginx 배포 · 팀장, 5인

원본 저장소: [SSAFESTA](https://github.com/mingleland/ssafesta) · [PinLog](https://github.com/Team-PinLog/PinLog) · [NoHome](https://github.com/repechage-team/no-home-backend) · [LINKLE](https://github.com/LINKLE-2025/LINKLE_Frontend)

## Engineering

**Stack**

- **Web & Integration** <sub>SSAFESTA · LINKLE</sub><br>React · TypeScript · Unity WebGL 연동 · WebSocket(STOMP)
- **Backend & AI** <sub>PinLog · NoHome · LINKLE</sub><br>Java · Spring Boot · Python · FastAPI · PostgreSQL · pgvector · Redis
- **Delivery & Tools** <sub>SSAFESTA · NoHome · LINKLE · ASC · JAM</sub><br>Docker · Nginx · OCI ARM · MCP · npm

**Problem Solving**

1. **시스템 경계 문제** — SSAFESTA: React·Unity 사이 ESC 이중 입력을 Unity 상태 snapshot과 명시 명령으로 해결, Production에서만 생긴 AI NPC 중복은 배포 산출물로 원인 확정 [기록](projects/ssafesta.md#4-engineering-decisions)
2. **측정 기반 판단** — PinLog: 임베딩·프롬프트·다수결 변경을 측정해 근거 없는 변경은 기각, 짧은 질의 검색 실패는 문자열 병합 신호로 해결 [기록](projects/pinlog.md#4-engineering-decisions)
3. **구조 개선과 운영** — NoHome: 챗봇·에이전트 두 경로를 Tool Calling 단일 엔드포인트로 통합, LINKLE: 401 자동 갱신의 루프 위험을 탭 복귀 갱신으로 전환 [NoHome](projects/nohome.md#4-engineering-decisions) · [LINKLE](projects/linkle.md#4-engineering-decisions)

## Published Developer Tools

- **[ASC](https://github.com/colosair/asc)** — Agent Session Control. AI 코딩 에이전트 세션의 목표·쓰기 경계·승인 조건을 계약으로 관리하는 로컬 제어 계층. `v0.10.2` · [npm](https://www.npmjs.com/package/@asc-agent/runtime)
- **[JAM](https://github.com/colosair/jam)** — Jira Agent MCP. Jira 읽기 결과에 조회 범위를 표시하고 쓰기는 Plan → Apply → Verify로만 실행하는 MCP 서버. `v1.8.0` · [npm](https://www.npmjs.com/package/@jam-mcp/server)

## Earlier Work & Background

<details>
<summary>이전 작업 — CardGarden · teacafe_POS · DB/Spring Quiz · SQLP Tuning Mock</summary>

- [CardGarden](https://github.com/colosair/cardgarden) · 2025 — Spring·MyBatis 기반 카드 추천 웹 서비스. 팀장, 이메일 인증·3사 OAuth2, 초기 구조·배포
- [teacafe_POS](https://github.com/colosair/teacafe_POS) · 2025 — Java·JDBC로 만든 찻집 콘솔 POS, 개인 학습 프로젝트
- [DB Quiz](https://github.com/colosair/db-quiz) · [Spring Quiz](https://github.com/colosair/spring-quiz) · 2026 — 과목평가 대비 모의고사 웹앱, 각 150문항
- [SQLP Tuning Mock](https://github.com/colosair/sqlp-tuning-mock) · 2026 — SQL 튜닝 창작 모의문제 240문항, CC BY 4.0

</details>

- **Education** — SSAFY 15기 1학기 이수(925시간, 2026.01–06) · 신한DS 금융SW 아카데미 5기 수료(976시간, 2025.04–10)
- **Awards** — SSAFY 1학기 프로젝트 최우수상(팀, NoHome) · 1학기 성적우수상(개인, 종합성적 반 3등) · 2026.06
- **Certifications** — 정보처리기사 · SQLD · ADsP
