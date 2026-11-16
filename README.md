# ❄️ AS-FAST · 냉난방 A/S 실시간 예약 서비스

**원하는 날짜와 시간을 바로 골라 냉난방 A/S를 예약하는 웹 서비스**  
*Java · JavaScript*

![Spring Boot 4.0](https://img.shields.io/badge/Spring_Boot-4.0-6db33f) ![MyBatis 4.0](https://img.shields.io/badge/MyBatis-4.0-b32424) ![View Thymeleaf](https://img.shields.io/badge/View-Thymeleaf-005f0f) ![DB MariaDB](https://img.shields.io/badge/DB-MariaDB-003545)

| 항목 | 내용 |
|------|------|
| 기간   | 2026.09.08 ~ 2026.09.17 (약 2주)                                                              |
| 팀     | COMMIT (3명) · 그린AI캠퍼스 평생교육원 「공공데이터를 활용한 AI 풀스택 웹 개발」 1차 프로젝트 |
| 대주제 | 웹 서비스 기능 구현                                                                           |

------------------------------------------------------------------------

## 📌 프로젝트 개요

여름·겨울 성수기에는 냉난방 A/S 예약이 몰려 전화 연결부터 어렵습니다. 고객이 직접 **남은 시간대를 확인하고 바로 예약**할 수 있도록, 예약 접수부터 확인·후기 작성까지 이어지는 흐름을 웹으로 구현했습니다.

- 🙍 **고객** — 로그인, A/S 예약 신청, 예약 시간 선택, 예약 내역 확인, 후기 작성
- 🛠️ **관리자** — 예약 현황 대시보드

## 🙋 내가 담당한 부분 — 로그인 · 예약 신청 폼

> - `회원` 로그인 기능 구현 (DTO · Mapper · Service · Controller 계층 구성)
> - `예약 폼` 로그인한 회원의 주소를 자동으로 불러오고, 필요하면 바꿀 수 있게 구현
> - `DB` A/S 카테고리(제품 종류 등)를 DB에서 조회해 예약 폼에 표시
> - `협업` `feature` / `hotfix` 브랜치로 나눠 작업하고 dev 병합 시 충돌 해결

## 🌿 주요 기능

- ✅ **로그인** — 회원 정보로 로그인, 로그인 상태에 따라 메뉴 변경
- ✅ **예약 신청** — 카테고리 선택, 회원 주소 자동 입력
- ✅ **실시간 시간 선택** — 이미 예약된 시간을 제외하고 가능한 시간만 선택
- ✅ **예약 내역** — 목록 · 상세 · 완료 화면
- ✅ **후기 작성** — A/S 완료 후 후기 등록
- ✅ **관리자 대시보드** — 예약 현황 확인

## 🧩 시스템 구성

```
[ 브라우저 ]  Thymeleaf (Layout Dialect) · CSS · JavaScript
      │
      ▼
[ Spring Boot ]  Controller → Service → Mapper   (member / reserve / review / admin)
      │
      ▼
[ MariaDB ]  회원 · 예약 · 카테고리 · 후기
```

## 🛠️ 사용 기술

| 분야     | 기술                            |
|----------|---------------------------------|
| Backend  | Java 17, Spring Boot, MyBatis   |
| Frontend | Thymeleaf, HTML/CSS, JavaScript |
| Database | MariaDB                         |
| 협업     | Git, GitHub, Notion             |

## 🔍 프로젝트 특징

- **기능별 패키지 구조**
  - `member` · `reserve` · `review` · `admin`을 각각 controller / service / mapper / dto로 나눠 담당자별로 겹치지 않게 작업
- **공통 레이아웃**
  - Thymeleaf Layout Dialect로 사용자 / 관리자 레이아웃을 분리하고 헤더·사이드 메뉴를 재사용
- **브랜치 전략**
  - 기능은 `feature/*`, 병합 후 수정은 `hotfix/*`로 나눠 dev에 합침

## 💡 느낀 점

처음으로 팀원과 협업해 서비스를 구현해 본 경험이었습니다. 로그인 기능을 DTO, Mapper, Service, Controller 순서로 직접 만들고, 팀원들이 만든 기능과 하나로 합쳐 보았습니다. 함께 만든 서비스가 실제로 작동하는 것을 보며 뿌듯함을 느꼈습니다.

특히 예약 폼의 카테고리를 처음에는 화면에 직접 적어 두었다가, 회의에서 놓친 부분을 알게 되어 DB에서 불러오도록 바꾸었습니다. 이 일을 겪으면서 처음 설계할 때부터 이런 경우까지 생각해 두는 것이 중요하다는 것을 깨달았습니다.

혼자 개발할 때는 보이지 않던 부분을 팀과 함께 발견하고 보완하면서, 개발은 기능만 만드는 것이 아니라 함께 생각하고 고쳐 가는 과정이라는 것을 배웠습니다.
