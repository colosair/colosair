# 이정헌 (Lee Jeongheon)

Web Platforms · AI Applications · Developer Tools

팀 프로젝트에서 웹 플랫폼 통합, AI 서버, 인증과 배포를 맡았고 AI 코딩 에이전트용 개발 도구 두 개를 npm에 배포했습니다. 프로젝트별 담당 범위와 근거 코드는 각 개인 기여 기록에 정리했습니다.

[Projects](#selected-projects) · [Engineering](#engineering) · [Developer Tools](#published-developer-tools) · [Background](#earlier-work--background)

## Selected Projects

<table>
<tr>
<td width="50%" valign="top">
<a href="projects/ssafesta.md"><img src="assets/featured/ssafesta-tile.webp" width="100%" alt="SSAFESTA 로그인 화면 — 개인 기여 기록으로 이동"></a><br>
<b><a href="projects/ssafesta.md">SSAFESTA</a></b> · <sub>Frontend Main · 6인</sub><br>
React·Unity 통합, 통합 검증과 Production 승격
</td>
<td width="50%" valign="top">
<a href="projects/pinlog.md"><img src="assets/featured/pinlog-tile.webp" width="100%" alt="PinLog 자연어 검색 화면 — 개인 기여 기록으로 이동"></a><br>
<b><a href="projects/pinlog.md">PinLog</a></b> · <sub>AI 파트 · 6인</sub><br>
FastAPI AI 파이프라인과 자연어 검색 품질 개선
</td>
</tr>
</table>

<table>
<tr>
<td width="50%" valign="top">
<a href="projects/nohome.md"><img src="assets/featured/nohome-tile.webp" width="100%" alt="NoHome 실거래가 검색과 AI 도우미 화면 — 개인 기여 기록으로 이동"></a><br>
<b><a href="projects/nohome.md">NoHome</a></b> · <sub>팀장 · 3인 · 최우수상(팀)</sub><br>
Tool Calling 기반 AI 어시스턴트와 개인 배포
</td>
<td width="50%" valign="top">
<a href="projects/linkle.md"><img src="assets/featured/linkle-tile.webp" width="100%" alt="LINKLE 지도와 장소 정보 화면 — 개인 기여 기록으로 이동"></a><br>
<b><a href="projects/linkle.md">LINKLE</a></b> · <sub>팀장 · 5인</sub><br>
FE·BE 인증 구조와 Docker·Nginx 배포
</td>
</tr>
</table>

원본 저장소: [SSAFESTA](https://github.com/mingleland/ssafesta) · [PinLog](https://github.com/Team-PinLog/PinLog) · [NoHome](https://github.com/repechage-team/no-home-backend) · [LINKLE](https://github.com/LINKLE-2025/LINKLE_Frontend)

## Engineering

**Strengths**

- **웹 클라이언트 기반 계층** <sub>React · TypeScript</sub><br>
  Unity WebGL 위 React 공통 구조, 환경을 감추는 Host Gateway, 실시간 통신 계층, 오류 처리 3계층 설계·구현(SSAFESTA). 인증 연동(LINKLE), 개인 도구 런타임(ASC·JAM)도 TypeScript로 작성·배포
- **시스템 경계 통합과 원인 진단** <sub>계약 · 종단 검증</sub><br>
  FE·BE·Unity·AI 사이 계약을 맞추고, 장애가 나면 담당 파트 코드(Unity C#·Spring·FastAPI·Jenkins·nginx)까지 읽어 원인 특정(SSAFESTA). 백엔드 AI 연동 직접 구현(PinLog)
- **AI 백엔드와 측정 기반 판단** <sub>Python · FastAPI · PostgreSQL · pgvector</sub><br>
  AI 처리 파이프라인과 자연어 검색 구현, 측정 도구로 임베딩·임계값·프롬프트 변경의 채택과 기각 판단(PinLog)
- **배포·릴리스 경로** <sub>Docker · Nginx · CI · npm</sub><br>
  Docker·Nginx 배포(LINKLE), OCI ARM 배포(NoHome), Production 승격 경로와 CI 정리(SSAFESTA), npm 릴리스(ASC·JAM)

**Key Problems Solved**

1. **장애 뒤 Production 승격 경로 신설** · SSAFESTA · [기록](projects/ssafesta.md#4-engineering-decisions) · [#1217](https://github.com/mingleland/ssafesta/pull/1217) [#1230](https://github.com/mingleland/ssafesta/pull/1230)
   - 문제: Demo 장애가 하루 5건 났고, Production 환경과 승격 절차가 없었음
   - 해결: Demo에서 검증한 산출물을 재빌드 없이 그대로 올리는 승격 경로와 rollback 상태 전이 구성
   - 결과: main 승격 11건 수행. Production에서만 생긴 AI NPC 중복은 배포 산출물을 직접 확인해 원인을 잡고 재승격
2. **BE·AI 계약 불일치로 멈춘 문서 처리** · SSAFESTA · [#1293](https://github.com/mingleland/ssafesta/pull/1293) [#1294](https://github.com/mingleland/ssafesta/pull/1294)
   - 문제: Demo·Production 문서 처리가 전부 실패, 로그에는 오류 코드만 남음
   - 해결: AI는 계약대로 보내고 Spring은 그 필드를 거절하던 것을 직접 호출로 재현, BE는 계약대로 받게 하고 AI는 거절 사유를 기록하게 수정
   - 결과: Demo 문서 처리 E2E 확인 후 main 승격
3. **React·Unity 입력 소유권 재설계** · SSAFESTA · [기록](projects/ssafesta.md#4-engineering-decisions) · [#572](https://github.com/mingleland/ssafesta/pull/572) [#580](https://github.com/mingleland/ssafesta/pull/580)
   - 문제: ESC가 두 번 먹고, 오버레이를 닫아도 Unity 카메라 초점이 남아 이동 불가
   - 해결: Unity가 UI 상태 snapshot을 보내고 React가 명시 명령을 보내는 채널로 상태 소유 분리, Unity 입력 코드는 건드리지 않음
   - 결과: 결함 해소, 관련 단위 테스트 22건 추가
4. **짧은 질의 검색 실패** · PinLog · [기록](projects/pinlog.md#4-engineering-decisions) · [ai#118](https://github.com/Team-PinLog/ai/pull/118) [ai#119](https://github.com/Team-PinLog/ai/pull/119) [back#206](https://github.com/Team-PinLog/back/pull/206)
   - 문제: 「부캠」 같은 짧은 고유명사가 검색 컷을 풀어도 8위
   - 해결: 임베딩 모델 교체는 측정으로 기각(1위 정답 수 동일, 저장 2배), 질의 재작성·키워드 재정렬·문자열 병합·LLM 재판정 4신호를 기본 꺼짐으로 추가
   - 결과: 신호마다 검증 게이트 통과 후 운영 활성화
5. **AI 어시스턴트 오동작을 구조로 수정** · NoHome · [기록](projects/nohome.md#4-engineering-decisions) · [PoC](https://github.com/repechage-team/no-home-backend/commit/26054ad) [통합](https://github.com/repechage-team/no-home-backend/commit/a487fc6)
   - 문제: 모호하거나 불만을 말한 발화도 억지로 화면 조작 명령이 됨
   - 해결: 조회 tool은 답변, 조작 tool은 명령을 그대로 반환하는 Tool Calling 단일 엔드포인트로 재설계, 분기 동작을 PoC로 먼저 검증
   - 결과: 챗봇·에이전트 두 엔드포인트 통합, 레거시 경로 제거

## Published Developer Tools

- **[ASC](https://github.com/colosair/asc)** · Agent Session Control · `v0.10.2` · [npm](https://www.npmjs.com/package/@asc-agent/runtime)<br>
  AI 코딩 에이전트 세션의 목표·쓰기 경계·승인 조건을 계약으로 관리하는 로컬 제어 계층
- **[JAM](https://github.com/colosair/jam)** · Jira Agent MCP · `v1.8.0` · [npm](https://www.npmjs.com/package/@jam-mcp/server)<br>
  Jira 읽기 결과에 조회 범위를 표시하고, 쓰기는 Plan → Apply → Verify로만 실행하는 MCP 서버

## Earlier Work & Background

<details>
<summary>이전 작업 — CardGarden · teacafe_POS · DB/Spring Quiz · SQLP Tuning Mock</summary>

- **[CardGarden](https://github.com/colosair/cardgarden)** · 2025 · 팀장<br>
  Spring·MyBatis 기반 카드 추천 웹 서비스. 이메일 인증·3사 OAuth2, 초기 구조·배포
- **[teacafe_POS](https://github.com/colosair/teacafe_POS)** · 2025 · 개인<br>
  Java·JDBC로 만든 찻집 콘솔 POS 학습 프로젝트
- **[DB Quiz](https://github.com/colosair/db-quiz) · [Spring Quiz](https://github.com/colosair/spring-quiz)** · 2026 · 개인<br>
  과목평가 대비 모의고사 웹앱, 각 150문항
- **[SQLP Tuning Mock](https://github.com/colosair/sqlp-tuning-mock)** · 2026 · 개인<br>
  SQL 튜닝 창작 모의문제 240문항, CC BY 4.0

</details>

**Education**

- SSAFY 15기 — 교육 중 · 2026.01.07 ~ 현재
- 신한DS 금융SW 아카데미 5기 — 수료 · 976시간 · 2025.04.01 ~ 2025.10.01

**Awards**

- SSAFY 1학기 프로젝트 최우수상 — 팀, NoHome · 2026.06
- SSAFY 1학기 성적우수상 — 개인, 종합성적 반 3등 · 2026.06

**Certifications**

- 정보처리기사 · SQLD · ADsP
