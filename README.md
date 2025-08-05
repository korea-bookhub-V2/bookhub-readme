# 📖 서점 ERP 서비스 BookHub README

- 배포 URL : 
- Test ID : 
- Test PW : 

<br>

## 프로젝트 소개

- **BookHub**는 오프라인 서점 및 프랜차이즈 도서 유통업체를 위한 통합 ERP 시스템입니다.
- 전국 지점의 도서 전시, 재고, 주문, 발주 흐름부터 직원 인사 및 권한 관리, 할인 정책 적용, 알림 및 로그 관리까지
- 도서 유통의 모든 과정을 하나의 시스템에서 통합적으로 관리할 수 있도록 설계되었습니다.

<br>

## 팀원 구성

<div align="center">

| **고혁재** | **최서윤** | **성재원** |
| :------: |  :------: | :------: |
| [<img src="https://avatars.githubusercontent.com/u/106502312?v=4" height=150 width=150> <br/> @khj](https://github.com/yeon1615) | [<img src="https://avatars.githubusercontent.com/u/106502312?v=4" height=150 width=150> <br/> @csw](https://github.com/yeon1615) | [<img src="https://avatars.githubusercontent.com/u/106502312?v=4" height=150 width=150> <br/> @sjw](https://github.com/yeon1615) |



</div>

<br>

## 1. 개발 환경

- Front : React, TypeScript, HTML5, CSS3
- Back-end : Spring Boot, JPA, Spring Security, Spring Boot Validation, Spring Boot Mail, JWT, MyBatis, Lombok
- 형상 관리 : Git
- 데이터베이스: MySQL
- 테스트 도구: Postman
- 프로젝트 일정 정리 도구 : Notion
- 서비스 배포 환경 : 
- 디자인 : [Figma](https://www.figma.com/design/EWdZT1aa3Rf980aMJYeq56/%EC%8A%AC%EB%A6%BD%ED%85%8C%ED%81%AC-%EB%B6%81%ED%97%88%EB%B8%8C?node-id=0-1&p=f&t=BpCnYMWC3D2dlzC5-0)
<br>

## 2. 채택한 개발 기술과 브랜치 전략

### Front-end

- **React + TypeScript**: SPQ 기반 화면 구성 및 안정적인 타입 관리
- **HTML5 / CSS3**: 웹 표준 기반 마크업 및 스타일링
- **Tailwind CSS**: 빠른 UI 프로토타이핑 및 반응형 스타일링
- **Zustand**: 전역 상태 관리 라이브러리
    
### Back-end

- **Spring Boot (Java)**: RESTful API 서버 개발
- **Spring Security + JWT**: 로그인, 권한 부여 및 인증 처리
- **Spring Validation / Mail**: 유효성 검사 및 이메일 인증 처리
- **JPA + MyBatis**: ORM 기반의 CRUD + 복잡한 쿼리 병행 지원
- **Lombok**: 보일러플레이트 코드 제거

### 기타

- **MySQL**: 관계형 데이터베이스
- **Postman**: API 테스트 및 협업
- **Figma**: UI/UX 시안 디자인
- **GitHub**: 형상 관리
- **Notion**: 업무 및 일정 관리
- **교보문고 크롤링 자동화**: 300권 이상의 실데이터 수집 및 초기 데이터베이스 구축
- **Recharts**: 판매 통계 시각화 차트 구현

### 브랜치 전략

- Git-flow 전략을 기반으로 브랜치를 관리했습니다.
- 브랜치 구성:
  - main: 실제 배포 및 최종 제품 브랜치
  - develop: 모든 기능 브랜치가 병합되는 통합 개발 브랜치
  - feat/기능명-이름명: 기능 단위 브랜치로 작업 후 develop에 merge 및 삭제
- 커밋 컨벤션:
  - feat: 새로운 기능
  - refactor: 코드 리팩토링

<br>

## 3. 프로젝트 구조

-**Backend (Spring Boot)**

```
bookhub-back/
├── build.gradle
├── settings.gradle
├── README.md
│
├── src
│   ├── main
│   │   ├── java
│   │   │   └── com.bookhub
│   │   │       ├── common              # 공통 상수, 응답 메시지 등
│   │   │       ├── controller          # REST API Controller
│   │   │       ├── dto                 # 요청 및 응답 DTO
│   │   │       ├── entity              # JPA Entity 클래스
│   │   │       ├── repository          # DB 접근 레이어 (JPA, MyBatis)
│   │   │       ├── security            # Spring Security 설정
│   │   │       └── service             # 비즈니스 로직
│   │   └── resources
│   │       ├── application.yml        # 환경 설정
│   │       ├── mapper                 # MyBatis XML 매퍼
│   │       └── static/templates       # 정적 리소스 및 템플릿 (필요 시)
│   └── test                           # 테스트 코드
```

-**Frontend (React + TypeScript)**

```
bookhub-front/
├── package.json
├── tsconfig.json
├── tailwind.config.js
├── .eslintrc.js
├── .prettierrc
│
├── public
│   └── index.html
│
└── src
    ├── main.tsx                      # 앱 진입점
    ├── App.tsx                       # 라우터 및 레이아웃 설정
    │
    ├── apis/                         # API 통신 함수
    ├── components/                   # 공통 UI 컴포넌트 (헤더, 버튼 등)
    ├── dtos/                         # DTO 타입 정의
    ├── pages/                        # 주요 페이지 컴포넌트
    │   ├── Book/
    │   ├── Category/
    │   ├── Employee/
    │   ├── Login/
    │   ├── Reception/
    │   ├── Statistics/
    │   └── ...
    ├── stores/                       # Zustand 기반 전역 상태 관리
    ├── styles/                       # Tailwind 및 전역 스타일
    └── utils/                        # 유틸 함수, 형식 처리 등
```

<br>

## 4. 역할 분담

### 고혁재

- **기능**
    - 회원 가입/로그인
    - 아이디 찾기 및 이메일 인증
    - 비밀번호 변경 및 이메일 인증
    - 회원가입 승인 기능 및 로그
    - 직원 정보 수정 기능 및 로그
    - 재고 통계 기능
    - 지점 CRUD
    - 저자 CRUD
    - 발주 승인 로그

<br>
    
### 최서윤

- **기능**
    - 책 위치 기능 구현
    - 재고 업데이트 및 로그
    - 할인정책 기능구현
    - 출판사 CRUD
    - 매출 통계기능 구현
    - Sidebar/header 구현
    - 발주 요청서 CRUD
    - 발주 승인 기능 구현

<br>

### 성재원

- **기능**
    - 알림 기능 구현
    - 책 CRUD
    - 수령 확인 CRUD
    - 카테고리 CRUD
    - 베스트셀러
    - 판매 수량 통계 차트
    - 메인 화면 통합 검색

<br>

## 5. 개발 기간 및 작업 관리

### 개발 기간

- 전체 개발 기간 : 2025.04.01 ~ 2025.06.30
- UI 구현 : 2025.04.01 ~ 2025.05.24
- 기능 구현 : 2025.05.25 ~ 2025.06.30

<br>

### 작업 관리

- **Notion**을 중심으로 전체 작업 흐름을 관리했습니다.
  - 역할 분담, API 명세, 일정표, 기능별 구현 체크리스트 등을 정리
  - 각자의 진행 상황을 실시간으로 공유하며 기능별 완료 여부를 체크
- 주간 회의를 통해 각자 진행 상황을 공유하고, 기능 병합 및 코드 리뷰를 진행했습니다.

<br>

## 6. 페이지별 기능

<br>

## 7. 프로젝트 후기

### 고혁재

..

<br>

### 최서윤

...

<br>

### 성재원

....

<br>
