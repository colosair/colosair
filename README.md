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
  React·Unity 공통 구조, Host Gateway, 실시간 통신 계층 (SSAFESTA)
- **시스템 경계 통합·진단** <sub>계약 · 종단 검증</sub><br>
  FE·BE·Unity·AI 계약 정리, 담당 파트 코드까지 읽어 원인 특정
- **AI 백엔드·측정 기반 판단** <sub>Python · FastAPI · pgvector</sub><br>
  처리 파이프라인·자연어 검색 구현, 변경 채택·기각을 측정으로 결정 (PinLog)
- **배포·릴리스** <sub>Docker · Nginx · CI · npm</sub><br>
  OCI ARM 배포, Production 승격 경로, npm 패키지 릴리스

**Key Problems Solved**

1. **Production 승격 경로 신설** · [SSAFESTA](projects/ssafesta.md#4-engineering-decisions)<br>
   장애 뒤 Demo 검증 산출물을 재빌드 없이 승격하는 경로 구성, main 승격 11건
2. **BE·AI 계약 불일치** · [SSAFESTA](projects/ssafesta.md)<br>
   문서 처리 전면 실패를 재현으로 규명, BE·AI 양쪽 수정
3. **React·Unity 입력 소유권** · [SSAFESTA](projects/ssafesta.md#4-engineering-decisions)<br>
   ESC 이중 입력을 Unity 상태 snapshot과 명시 명령 채널로 해결
4. **짧은 질의 검색 실패** · [PinLog](projects/pinlog.md#4-engineering-decisions)<br>
   임베딩 교체는 측정으로 기각, 4신호 검색을 검증 게이트 통과 후 운영 적용
5. **AI 어시스턴트 오동작** · [NoHome](projects/nohome.md#4-engineering-decisions)<br>
   Tool Calling 단일 엔드포인트로 조회 답변과 화면 조작 분리

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
