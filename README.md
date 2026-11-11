# CALENDAR BOT 문서

[CALENDAR BOT](https://github.com/ho8566z/calendar-bot) 프로젝트의 명세서와 발표 자료를 모아 둔 문서 저장소입니다. (1차 개인 프로젝트, 2026.11.07 ~ 11.12)

코드는 [calendar-bot](https://github.com/ho8566z/calendar-bot) 저장소에 있고, 이 저장소에는 코드를 만들기 전에 정한 기획·설계 문서와 발표 자료만 둡니다.

## 프로젝트 요약

월간 달력에서 일정을 관리·검색하고, 다음 주 일정을 매주 일요일 21:00에 텔레그램으로 보내 주며, 휴대폰 화면에서도 쓸 수 있는 개인 일정 관리 웹 서비스입니다.

- **해결하려는 문제**: 일정을 등록해 두고도 다시 열어 보지 않으면 놓친다.
- **핵심 기능**: 주간 브리핑(텔레그램), 모바일 반응형 화면
- **기술 스택**: Java 17, Spring Boot, Spring Security, JPA(쓰기)·MyBatis(동적 조회), MySQL, Thymeleaf
- **목적**: 취업용 포트폴리오. 단순 CRUD에서 멈추지 않고 기획·보안·완성도로 차별화

## 폴더 구성

```
서류/
  calendar_bot 명세서 모음.xlsx     명세서 전체(시트 13개)
ppt/
  calendar_bot_new.pptx            발표 자료(23장)
  calendar_bot_new/                슬라이드 이미지(슬라이드1~23.PNG)
  calendar_bot.pdf                 발표 자료 PDF
  캡처/                            실제 화면 캡처(홈, 달력, 통계)
```

## 명세서 (서류/calendar_bot 명세서 모음.xlsx)

| 시트 | 내용 |
| --- | --- |
| 프로젝트 산출물 가이드 | 제출해야 할 산출물 항목과 작성 상태 |
| 프로젝트 개요 | 서비스 목표, 권한 등급, 서비스 구성, 기술 스택, 실행 흐름, 구현 상태, 확정·미정 항목 |
| 결정 기록 | 방향·기술·설계 결정과 검토한 선택지, 이유(D-01~D-15) |
| 요구 명세서 | 구분별 요구사항(ID, 권한, 세부 기능 요구사항) |
| 기능 목록 | 기능 ID, 설명, 관련 요구사항, 액터, 우선순위, 개발 구분(기존·개선·신규) |
| 기능 명세서 | 핵심 기능의 사전 조건, 입력, 처리 순서, 업무 규칙, 예외 |
| API 명세서 | 구분, Method, URI, 권한, 구현·계획 상태 |
| 화면 기능 명세서 | 화면 ID별 영역·요소·사용자 동작·처리 규칙 |
| 테이블 명세서 | MySQL 테이블과 컬럼(`USER_MEMBER`, `PLAN`, `BRIEF_LOG`, `TELEGRAM_LINK`, `LOGIN_LOCK` 등) |
| WBS | 6일 일정(문서 → 개발 → 오류 수정 → 마무리)과 작업별 상태 |
| 트러블슈팅 | 점검에서 찾은 문제, 영향도, 재현 방법, 처리 상태 |
| 설정·규약 | 포트, 환경변수, 구현 순서 등 개발 공통 기준 |
| 2순위 기능 | 핵심 기능을 끝낸 뒤 구현할 기능과 2순위로 둔 이유 |

## 주요 결정

- Calendar 주제를 유지(D-01), 학원에서 배운 기술 범위 안에서만 사용(D-02)
- 쓰기·단순 조회는 JPA, 검색·통계 같은 동적 조회는 MyBatis로 역할 분리(D-03)
- 주간 브리핑은 텔레그램 전용, 연동은 1회용 코드 + 롱 폴링(D-04, D-05)
- 통계는 외부 차트 라이브러리 없이 표와 CSS 막대로 구현(D-07)
- 모바일은 반응형 웹으로만 진행, 경계 폭 768px(D-14)

## 발표 자료

`ppt/calendar_bot_new.pptx`(23장)에 프로젝트 소개, 기능, 구성, 구현 결과를 정리했습니다. PDF(`ppt/calendar_bot.pdf`)와 슬라이드 이미지는 같은 내용을 다른 형식으로 둔 것입니다.

<table>
<tr><td><img src="ppt/calendar_bot_new/슬라이드1.PNG" alt="슬라이드 1" width="100%"><br><sub>1</sub></td><td><img src="ppt/calendar_bot_new/슬라이드2.PNG" alt="슬라이드 2" width="100%"><br><sub>2</sub></td><td><img src="ppt/calendar_bot_new/슬라이드3.PNG" alt="슬라이드 3" width="100%"><br><sub>3</sub></td></tr>
<tr><td><img src="ppt/calendar_bot_new/슬라이드4.PNG" alt="슬라이드 4" width="100%"><br><sub>4</sub></td><td><img src="ppt/calendar_bot_new/슬라이드5.PNG" alt="슬라이드 5" width="100%"><br><sub>5</sub></td><td><img src="ppt/calendar_bot_new/슬라이드6.PNG" alt="슬라이드 6" width="100%"><br><sub>6</sub></td></tr>
<tr><td><img src="ppt/calendar_bot_new/슬라이드7.PNG" alt="슬라이드 7" width="100%"><br><sub>7</sub></td><td><img src="ppt/calendar_bot_new/슬라이드8.PNG" alt="슬라이드 8" width="100%"><br><sub>8</sub></td><td><img src="ppt/calendar_bot_new/슬라이드9.PNG" alt="슬라이드 9" width="100%"><br><sub>9</sub></td></tr>
<tr><td><img src="ppt/calendar_bot_new/슬라이드10.PNG" alt="슬라이드 10" width="100%"><br><sub>10</sub></td><td><img src="ppt/calendar_bot_new/슬라이드11.PNG" alt="슬라이드 11" width="100%"><br><sub>11</sub></td><td><img src="ppt/calendar_bot_new/슬라이드12.PNG" alt="슬라이드 12" width="100%"><br><sub>12</sub></td></tr>
<tr><td><img src="ppt/calendar_bot_new/슬라이드13.PNG" alt="슬라이드 13" width="100%"><br><sub>13</sub></td><td><img src="ppt/calendar_bot_new/슬라이드14.PNG" alt="슬라이드 14" width="100%"><br><sub>14</sub></td><td><img src="ppt/calendar_bot_new/슬라이드15.PNG" alt="슬라이드 15" width="100%"><br><sub>15</sub></td></tr>
<tr><td><img src="ppt/calendar_bot_new/슬라이드16.PNG" alt="슬라이드 16" width="100%"><br><sub>16</sub></td><td><img src="ppt/calendar_bot_new/슬라이드17.PNG" alt="슬라이드 17" width="100%"><br><sub>17</sub></td><td><img src="ppt/calendar_bot_new/슬라이드18.PNG" alt="슬라이드 18" width="100%"><br><sub>18</sub></td></tr>
<tr><td><img src="ppt/calendar_bot_new/슬라이드19.PNG" alt="슬라이드 19" width="100%"><br><sub>19</sub></td><td><img src="ppt/calendar_bot_new/슬라이드20.PNG" alt="슬라이드 20" width="100%"><br><sub>20</sub></td><td><img src="ppt/calendar_bot_new/슬라이드21.PNG" alt="슬라이드 21" width="100%"><br><sub>21</sub></td></tr>
<tr><td><img src="ppt/calendar_bot_new/슬라이드22.PNG" alt="슬라이드 22" width="100%"><br><sub>22</sub></td><td><img src="ppt/calendar_bot_new/슬라이드23.PNG" alt="슬라이드 23" width="100%"><br><sub>23</sub></td></tr>
</table>

## 작성자

이윤호 (개인 프로젝트)
