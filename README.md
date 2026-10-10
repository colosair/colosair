# 이정헌 (Lee Jeongheon)

**Web Platforms · AI Applications · Developer Tools**

완료한 팀 프로젝트와 실제로 배포한 개발자 도구를 정리했습니다. **담당 영역·기술적 판단·검증 결과**는 각 개인 기여 문서에서 공개 코드와 PR로 확인할 수 있습니다.

[팀 프로젝트](#selected-team-projects) · [배포한 도구](#published-developer-tools) · [이전 작업 및 이력](#earlier-work--background)

---

## Selected Team Projects

<table>
  <tr>
    <td width="50%" valign="top">
      <strong><a href="projects/ssafesta.md">SSAFESTA</a></strong><br>
      <em>2026.08–09 · Frontend Main · 6인 팀</em>
      <p>Unity WebGL 기반 메타버스 부스·전시 서비스.</p>
      <p><strong>주요 기여</strong><br>React·Unity Host/Bridge 설계, 이벤트 계약·통합 검증, Demo 검증 산출물의 Production 승격.</p>
      <a href="projects/ssafesta.md">개인 기여</a> · <a href="https://github.com/mingleland/ssafesta">원본 코드</a>
    </td>
    <td width="50%" valign="top">
      <strong><a href="projects/pinlog.md">PinLog</a></strong><br>
      <em>2026.07–08 · AI 담당 · 6인 팀</em>
      <p>경험·방문 이유를 기록하고 자연어로 검색하는 장소 아카이빙 서비스.</p>
      <p><strong>주요 기여</strong><br>FastAPI 비동기 처리·상태 전이, 4신호 검색 고도화, 품질 측정과 백엔드 AI 연동.</p>
      <a href="projects/pinlog.md">개인 기여</a> · <a href="https://github.com/Team-PinLog/PinLog">원본 코드</a>
    </td>
  </tr>
  <tr>
    <td width="50%" valign="top">
      <strong><a href="projects/nohome.md">NoHome</a></strong><br>
      <em>2026.06–07 · 팀장 / AI · 팀 3인 + 개인 고도화</em>
      <p>서울 아파트 실거래가 조회와 AI 어시스턴트. <strong>SSAFY 1학기 프로젝트 최우수상(팀)</strong>.</p>
      <p><strong>주요 기여</strong><br>Tool Calling 기반 조회·화면 조작 분리, 테스트 동기화. 팀 종료 후 OCI ARM·Docker·HTTPS 배포.</p>
      <a href="projects/nohome.md">개인 기여</a> · <a href="https://github.com/repechage-team/no-home-backend">팀 코드</a>
    </td>
    <td width="50%" valign="top">
      <strong><a href="projects/linkle.md">LINKLE</a></strong><br>
      <em>2025.08–09 · 팀장 / 인증·배포 · 5인으로 시작</em>
      <p>지도 기반 장소 기록·지역 SNS 서비스.</p>
      <p><strong>주요 기여</strong><br>Spring Boot·React 양단 인증(JWT·Redis·HttpOnly 쿠키), Focus-Refresh, HTTPS·Docker·Nginx 배포.</p>
      <a href="projects/linkle.md">개인 기여</a> · <a href="https://github.com/LINKLE-2025/LINKLE_Frontend">FE 코드</a> · <a href="https://github.com/LINKLE-2025/LINKLE_Backend">BE 코드</a>
    </td>
  </tr>
</table>

## Published Developer Tools

직접 설계·구현하고 npm에 배포한 개인 개발 도구입니다.

<table>
  <tr>
    <td width="50%" valign="top">
      <strong><a href="https://github.com/colosair/asc">ASC</a> — Agent Session Control</strong><br>
      <em>확인된 릴리스 · v0.10.2</em>
      <p>AI 코딩 에이전트의 작업 목표·쓰기 경계·승인 조건을 세션 계약으로 관리하는 로컬 제어 계층.</p>
      <a href="https://github.com/colosair/asc">소스·문서</a> · <a href="https://www.npmjs.com/package/@asc-agent/runtime">npm</a>
    </td>
    <td width="50%" valign="top">
      <strong><a href="https://github.com/colosair/jam">JAM</a> — Jira Agent MCP</strong><br>
      <em>확인된 릴리스 · v1.8.0</em>
      <p>Jira 읽기의 근거 범위를 표시하고 Plan → Apply → Verify 절차로 쓰기 작업을 제어하는 MCP 서버.</p>
      <a href="https://github.com/colosair/jam">소스·문서</a> · <a href="https://www.npmjs.com/package/@jam-mcp/server">npm</a>
    </td>
  </tr>
</table>

## Earlier Work & Background

<details>
<summary><strong>이전 작업 보기 — CardGarden · teacafe_POS · 학습 도구</strong></summary>

| 작업 | 확인된 결과 |
|---|---|
| [CardGarden](https://github.com/colosair/cardgarden) · 2025 | Spring·MyBatis 기반 카드 추천 서비스. 팀장, 이메일 인증·3사 OAuth2, 초기 구조·배포 |
| [teacafe_POS](https://github.com/colosair/teacafe_POS) · 2025 | Java·JDBC 기반 찻집 콘솔 POS 개인 학습 프로젝트 |
| [DB Quiz](https://github.com/colosair/db-quiz) / [Spring Quiz](https://github.com/colosair/spring-quiz) · 2026 | 과목 평가 대비 모의고사 웹앱(각 150문항) |
| [SQLP Tuning Mock](https://github.com/colosair/sqlp-tuning-mock) · 2026 | SQL 튜닝 창작 모의문제 240문항(CC BY 4.0) |

</details>

| Education | Awards · Certifications |
|---|---|
| **SSAFY 15기** — 1학기 과정 이수(2026.01–06, 925시간)<br><br>**신한DS 금융SW 아카데미 5기** — 976시간 수료(2025.04–10) | **SSAFY** — 1학기 프로젝트 최우수상(팀, NoHome), 1학기 성적우수상(개인·반 3등, 2026.06)<br><br>**정보처리기사** · **SQLD** · **ADsP** |

> 프로젝트에서 실제 수행한 내용과 팀 전체 결과는 구분하여 기록했습니다. 세부 구현·트러블슈팅·한계는 [프로젝트별 개인 기여 문서](projects/)에 남겼습니다.
