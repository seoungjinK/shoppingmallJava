# 🛍️ Spring Boot + React 쇼핑몰 프로젝트 (MyShop)

<div align="center">

![Java](https://img.shields.io/badge/Java-17-ED8B00?style=flat&logo=openjdk&logoColor=white)
![Spring Boot](https://img.shields.io/badge/Spring%20Boot-3.2-6DB33F?style=flat&logo=springboot&logoColor=white)
![Spring Security](https://img.shields.io/badge/Spring%20Security-6DB33F?style=flat&logo=springsecurity&logoColor=white)
![JPA](https://img.shields.io/badge/JPA-Hibernate-59666C?style=flat&logo=hibernate&logoColor=white)
![MySQL](https://img.shields.io/badge/MySQL-4479A1?style=flat&logo=mysql&logoColor=white)

![React](https://img.shields.io/badge/React-20232A?style=flat&logo=react&logoColor=61DAFB)
![Vite](https://img.shields.io/badge/Vite-646CFF?style=flat&logo=vite&logoColor=white)
![Recoil](https://img.shields.io/badge/Recoil-3578E5?style=flat&logo=recoil&logoColor=white)
![TailwindCSS](https://img.shields.io/badge/Tailwind_CSS-38B2AC?style=flat&logo=tailwind-css&logoColor=white)

</div>

<br>

## 📖 프로젝트 소개 (Introduction)
**MyShop**은 사용자에게는 직관적인 쇼핑 경험을, 관리자에게는 효율적인 상품 관리 기능을 제공하는 **풀스택 쇼핑몰 서비스**입니다.

단순한 기능 구현을 넘어 **트랜잭션 처리, N+1 문제 해결, JWT 기반 보안 시스템** 등 백엔드의 핵심 기술적 챌린지를 해결하여 서비스의 안정성과 확장성을 확보하는 데 집중했습니다.

<br>

## 🛠️ 기술 스택 (Tech Stack)

| 구분 | 상세 기술 |
| :--- | :--- |
| **Backend** | **Java 17**, **Spring Boot 3.2**, Spring Security, JPA, QueryDSL, MySQL |
| **Frontend** | **React**, Vite, Recoil, Axios, Tailwind CSS, MUI |
| **Payment** | PortOne (KakaoPay) |
| **Tools** | IntelliJ, VS Code, Git, Postman |

<br>

## 📂 프로젝트 구조 (Project Structure)

핵심 비즈니스 로직을 도메인별로 분리하고, QueryDSL과 Security 설정을 모듈화하여 유지보수성을 높였습니다.

### 1. Backend (Spring Boot)
<details>
<summary><b>☕ 백엔드 패키지 구조 (클릭하여 펼치기)</b></summary>
<div markdown="1">

```text
src/main/java/com/example/shoppingmall
├── config             # 설정 파일 (Security, CORS, QueryDSL, JWT)
│   ├── JwtAuthenticationFilter.java
│   ├── SecurityConfig.java
│   └── WebConfig.java
├── controller         # API 엔드포인트 (요청/응답 처리)
├── domain             # JPA Entity (DB 테이블 매핑)
│   ├── product
│   ├── user
│   └── ...
├── dto                # Data Transfer Object (데이터 전송 객체)
├── repository         # DAO 계층 (Spring Data JPA + QueryDSL)
│   ├── ProductRepositoryImpl.java (QueryDSL 구현)
│   └── ...
└── service            # 비즈니스 로직 & 트랜잭션 처리
