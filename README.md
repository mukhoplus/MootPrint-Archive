# MootPrint 🐾

> **발자취를 기록하는 위치 기반 모바일 서비스**

- 본 프로젝트는 `Microsoft Copilot Pro`를 이용한 `Vibe Coding`을 통해 제작되었습니다.

MootPrint는 사용자의 위치 정보를 기록하고 관리할 수 있는 위치 기반 서비스입니다. Android 앱, 백엔드 서버, 그리고 관리자 웹 페이지로 구성된 완전한 생태계를 제공합니다.

## 📱 프로젝트 구조

```
MootPrint-archive/
├── MootPrint/                    # Android 앱
│   ├── app/
│   │   ├── src/main/java/        # Kotlin 소스 코드
│   │   ├── src/main/res/         # Android 리소스
│   │   └── build.gradle.kts      # 앱 모듈 빌드 설정
│   ├── local.properties          # 환경 변수
│   └── build.gradle.kts          # 프로젝트 빌드 설정
│
├── MootPrint-Server/             # 백엔드 서버 (Spring Boot)
│   ├── src/main/kotlin/          # Kotlin 소스 코드
│   │   └── com/mukho/mootprint/
│   │       ├── location/         # 위치 관련 기능
│   │       ├── user/             # 사용자 관련 기능
│   │       └── config/           # 설정 파일
│   ├── src/main/resources/       # 설정 파일 디렉토리
│   └── build.gradle              # Gradle 빌드 설정
│
├── MootPrint-Admin/              # 관리자 웹 앱 (Next.js)
│   ├── src/
│   │   ├── app/                  # Next.js 13+ App Router
│   │   ├── components/           # React 컴포넌트
│   │   ├── services/             # API 서비스
│   │   └── types/                # TypeScript 타입 정의
│   ├── public/                   # 정적 파일
│   ├── package.json              # Node.js 의존성
│   └── .env.local                # 환경 변수 예제
│
└── README.md                     # 이 파일
```

## 🚀 주요 기능

### 📱 MootPrint (Android App)

- **위치 추적**: GPS를 통한 실시간 위치 기록
- **Google Maps 연동**: 지도 기반 위치 시각화
- **사용자 인증**: Google OAuth 로그인
- **로컬 저장**: Room Database를 통한 오프라인 데이터 관리
- **백그라운드 동작**: Work Manager를 통한 백그라운드 위치 수집

### 🔧 MootPrint-Server (Backend API)

- **RESTful API**: 위치 데이터 CRUD 작업
- **사용자 관리**: OAuth 기반 사용자 인증 및 관리
- **데이터베이스**: MySQL/MariaDB 연동
- **Spring Boot**: 안정적이고 확장 가능한 백엔드 아키텍처

### 🌐 MootPrint-Admin (Web Admin)

- **위치 데이터 관리**: 사용자별 위치 정보 조회 및 관리
- **지도 시각화**: 네이버 지도, OpenStreetMap 지원
- **데이터 분석**: 날짜별 위치 데이터 필터링 및 분석
- **반응형 UI**: Tailwind CSS 기반 모던 인터페이스

## 🛠 기술 스택

| 구분            | 기술 스택                                                          |
| --------------- | ------------------------------------------------------------------ |
| **Android**     | Kotlin, Android SDK, Retrofit, Room, Google Maps API, Work Manager |
| **Web Admin**   | Next.js, TypeScript, Tailwind CSS, Leaflet, Naver Maps API         |
| **Backend**     | Spring Boot, Kotlin, MySQL, JPA/Hibernate                          |
| **Build Tools** | Gradle (Android/Server), npm (Web)                                 |

## 🔧 개발 환경 설정

### 필수 요구사항

- **Android**: Android Studio, JDK 17+
- **Web**: Node.js 18+, npm
- **Server**: JDK 17+, MySQL 8.0+

### 환경 변수 설정

각 프로젝트는 민감한 정보를 환경 변수로 관리합니다:

#### 🔐 Android (`local.properties`)

#### 🔐 Admin (`.env.local`)

#### 🔐 Server (`application.properties`)

### 📊 성능 최적화

#### Android 앱

- **위치 수집 간격 조정**: `LocationService`에서 간격 설정
- **배터리 최적화**: 도즈 모드 및 배터리 최적화 예외 설정
- **Room 쿼리 최적화**: 인덱스 추가 및 쿼리 최적화

#### 백엔드 서버

- **데이터베이스 인덱싱**: 위치 및 시간 기반 인덱스 생성
- **API 응답 캐싱**: Redis 또는 메모리 캐시 활용
- **쿼리 최적화**: N+1 문제 해결

#### 웹 관리자

- **이미지 최적화**: Next.js Image 컴포넌트 사용
- **API 응답 캐싱**: SWR 또는 React Query 활용
- **번들 크기 최적화**: Dynamic Import 사용
