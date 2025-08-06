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
###[로그인/로그아웃]
- 서비스 최초 화면으로 로그인을 해야 해당 ERP를 이용가능합니다.
  - LoginId와 Authority 정보를 이용하여 JWT토큰 생성 및 만료시간 설정
  - 로그인 시 사요자 정보와 함께 JWT 토큰과 만료시간 반환
  - 존재하는 Login Id인지 비밀번호가 일치하는지 확인하는 유효성 검사 진행
  - 직원의 회원 가입 승인이 보류 혹은 거절되었을 때 로그인 실
- 회원가입이 되어있는 경우 아이디/비밀번호를 입력 후 로그인/ 되어있지 않은 경우 회원가입 진행
###[회원가입/회원가입 승인]
- 비밀번호와 아이디에 대한 유효성 검사를 진행하고 회원가입을 진행합니다.
- 회원 가입 시 정규식과 중복체크 메서드를 통해 이미 가입된 아이디, 이메일, 연락처를 확인하여 중복 가입을 방지
- 회원 가입 완료 후 로그인 페이지 이동
###[아이디/비밀번호 찾기 및 이메일 인증]
- 아이디 찾기
  - 직원이 가입시 작성했던 이메일과 전화번호를 입력하면 해당 이메일로 토큰이 담긴 URL이 이메일을 통해 보내짐.
  - 인증 링크 URL은 email, phoneNumber 과 employeeRepository로 찾은 loginId이 포함된 Token이 포함되어 있음
  - Front에서 이 Token을 Param으로 받아 loginId를 받아옴.
- 비밀번호 찾기
  - 아이디 찾기와는 다르게 이메일, 전화번화와 직원의 아이디까지 받아옴
  - 해당 인증 링크 URL은 Long userId까지 포함된 Token이 포함되어 있음.
  - 비밀번호는 bCryptpasswordEncoder로 처리되어 있기 때문에 비밀번호를  재설정하는것으로 유도하도록 함.
  - 재설정이 끝나면 버튼을 클릭하여 로그인 페이지로 이동
###[로그인 승인]
- 회원 가입 시 로그인 승인 필요
- 관리자가 해당 직원의 정보를 확인 후 회원가입 승인 또는 거절
- 거절 시 거절 사유를 선택 후 확인 버튼을 통해 승인 결과를 해당 직원에게 이메일로 전달
- 거절 사유가 정보 불일치일 경우 이메일 인증을 통한 정보 수정 후 다시 승인 절차를 기다림
- 승인 시 완료와 함께 직원에게 승인 결과를 이메일을 통해 전송










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
