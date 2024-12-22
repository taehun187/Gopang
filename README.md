# GOPANG Microservice Project
**GOPANG-microservice**는 마이크로서비스 아키텍처를 기반으로 설계된 프로젝트로, 쇼핑 또는 결제 플랫폼과 같은 복잡한 시스템을 여러 독립적인 서비스로 나누어 관리하며 유연성과 확장성을 제공합니다.
<br>
<br>

## 🛠️ 프로젝트 개요
본 프로젝트는 다음과 같은 주요 서비스를 포함합니다:
1. **Config Server**
    - 분산된 마이크로서비스 환경에서 공통 설정을 관리.
    - Spring Cloud Config 기반.

2. **Eureka Server**
    - 서비스 디스커버리 기능 제공.
    - 각 서비스는 Eureka 서버에 등록되어 동적으로 서로의 위치를 탐색 가능.

3. **API Gateway (Gateway Server)**
    - 클라이언트 요청을 라우팅하고, 인증, 로깅, 부하 분산 등을 처리.
    - Spring Cloud Gateway 또는 Zuul 기반.

4. **Payment Service**
    - 결제 및 결제 취소 로직 처리.
    - 카드 결제, 환불 관련 도메인 모델 포함 (`Card`, `Cancel` 등).

5. **OAuth2 Server**
    - 인증 및 권한 관리.
    - OAuth2 표준 기반으로 구현된 인증 제공.


<br>
<br>

## ⚙️ 설정 정보
### 1. **Docker Compose 설정**
- `docker-compose.yml`:
    - 각 마이크로서비스와 데이터베이스, Eureka 서버, Config 서버 등을 컨테이너로 구성.

### 2. **Spring Cloud 구성**
- **Config Server**:
    - `configserver/src/main/resources/bootstrap.yml`에서 외부 구성 경로 지정.

- **Eureka Server**:
    - `eurekaserver/src/main/resources/bootstrap.yml`에서 Eureka 서버 환경 정의.

<br>
<br>

## 📦 주요 디렉토리 구조
---
'''
GOPANG-microservice/
├── configserver/                # Config Server 소스코드
│   ├── src/main/java/com/gopang/configserver/
│   ├── resources/
├── eurekaserver/                # Eureka Server 소스코드
│   ├── src/main/resources/
│   ├── build.gradle
├── gatewayserver/               # API Gateway 소스코드
│   ├── src/main/java/com/gopang/gatewayserver/
│   │   ├── filters/            # JWT 인증 및 트래킹 필터
│   ├── src/main/resources/
├── paymentserver/               # 결제 서비스
│   ├── src/main/java/com/gopang/paymentserver/
│   │   ├── authentication/     # 토큰 인증
│   │   ├── controller/         # 결제 REST 컨트롤러
│   │   ├── domain/             # 결제/취소 도메인 클래스
│   ├── src/main/resources/
├── oauth2server/                # OAuth2 인증 서버
├── docker-compose/              # Docker Compose 파일

'''
---
<br>
<br>

## 🔗 주요 기술 스택
- **Backend**:
    - **Java**, Spring Boot
    - Spring Cloud (Config, Eureka, Gateway)
    - Spring Data JPA


- **DevOps**:
    - Docker
    - Gradle 빌드 시스템
<br>
<br>



