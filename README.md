## Introduce
![rect](https://capsule-render.vercel.app/api?type=rect&color=gradient&text=Hello,World🐶&fontAlign=30&fontSize=30&textBg=true&desc=I'M%20HyunSeok%20Seo&descAlign=60&descAlignY=50)

<h3 align="center">🛠️ Tech Stack 🛠️</h3>
<p align="center">languages and tools</p>

<p align="center">
  <img src="https://img.shields.io/badge/HTML-E34F26?style=flat-square&logo=HTML5&logoColor=white"/>&nbsp
  <img src="https://img.shields.io/badge/CSS-1572B6?style=flat-square&logo=CSS3&logoColor=white"/>&nbsp
  <img src="https://img.shields.io/badge/JavaScript-F7DF1E?style=flat-square&logo=JavaScript&logoColor=black"/>&nbsp
  <img src="https://img.shields.io/badge/React-61DAFB?style=flat-square&logo=react&logoColor=black"/>&nbsp
  <br>
  <img src="https://img.shields.io/badge/Java-006D5C?style=flat-square&logo=java&logoColor=white"/>&nbsp
  <img src="https://img.shields.io/badge/Spring-6DB33F?style=flat-square&logo=spring&logoColor=white"/>&nbsp
  <br>
  <img src="https://img.shields.io/badge/MySQL-4479A1?style=flat-square&logo=mysql&logoColor=white"/>&nbsp
  <img src="https://img.shields.io/badge/Oracle-F80000?style=flat-square&logo=oracle&logoColor=white"/>&nbsp
</p>

![Top Langs](https://github-readme-stats.vercel.app/api/top-langs/?username=aodhzld45&layout=compact&theme=dark&hide_border=true&cache_seconds=21600)
<!-- GitHub Streak -->
![GitHub Streak](https://github-readme-streak-stats-eight.vercel.app?user=aodhzld45&theme=dark&hide_border=true)

[![Naver Badge](https://img.shields.io/badge/Naver-03C75A?style=flat-square&logo=Naver&logoColor=white)](mailto:prking94@naver.com)

<!-- hsbs 소개 -->
# HSBS 🧪 — 포트폴리오 & AI 서비스 플레이그라운드

> 제 개인 **포트폴리오 + 자기소개 + 실험용 SaaS 플랫폼**입니다.  
> 프론트는 **React**, 백엔드는 **Spring Boot + MySQL**, 인프라는 **OCI Ubuntu + Nginx/Apache + GitHub Actions CI/CD**로 구성했습니다.

- 🌐 Live: https://www.hsbs.kr  
- 🔧 Backend: `hsb-bo` (Spring Boot)  
- 🎨 Frontend: `hsb-fe` (React SPA)  

---

## 🤖 HSBS SaaS Chatbot (멀티 테넌트 챗봇 위젯)

사내/외부 사이트에 임베드 가능한 **멀티 테넌트 챗봇**입니다.  
각 위젯은 `siteKey`로 식별되며, **위젯 설정 · 프롬프트 · 쿼터 · 사용량 로깅**까지 포함한 상용화 구조를 목표로 합니다.

### 핵심 흐름

1. **SiteKey 발급**
   - 도메인 화이트리스트
   - 플랜/상태 관리: `ACTIVE / SUSPENDED / REVOKED`
2. **Widget 설정**
   - 테마/버블/컬러/위치/환영 문구 등 **브랜딩 옵션** 저장
3. **Prompt Profile**
   - 시스템/가드레일 프롬프트
   - `temperature`, `maxTokens` 등 모델 파라미터
   - 테넌트 ID(tenantId)로 멀티 테넌트 구분
4. **JS SDK 임베드**
   - `hsbs-chat.js` 스니펫 한 줄로 위젯 로드
5. **요청 처리**
   - `/api/ai/complete` 엔드포인트
   - 요청/응답 및 메타데이터 저장 · 로깅
6. **쿼터/요금 관리**
   - 일일/월간 호출 수, 사용 토큰량 추적
   - 토큰 비용을 KRW 기준으로 환산해 집계

### 관리자 기능 (요약)

- **SiteKey 관리**
  - 목록/검색, 상태 변경(토글), 논리 삭제(soft delete)
- **WidgetConfig**
  - 생성/수정 (파일/이미지 포함)
  - 미리보기(Preview) 패널로 즉시 확인
- **PromptProfile**
  - 등록/수정 및 버전 관리
  - 시스템/가드레일 프롬프트 분리 관리

---

## 📈 KRX/KIS 증권 데이터 모듈 (포트폴리오 연동)

HSBS 내에서 **국내 주식 마스터 + 시세/캔들 차트**를 제공하는 모듈입니다.  
향후 “사내용 금융 포털” 혹은 “투자 대시보드”로 확장 가능한 형태를 목표로 설계했습니다.

### 데이터 파이프라인

1. **KRX 마스터**
   - KRX CSV/XLS 배치로 종목코드/시장/상장상태 주기적 갱신
2. **KIS OpenAPI**
   - 실시간/근실시간 가격 수집
   - 일/주/월 캔들 데이터 적재
3. **저장 스키마(요약)**
   - `stock_master`, `stock_market_price` 등
   - 인덱스 설계 & Unique Key로 **중복 삽입 방지**
4. **스케줄러**
   - 장중/장마감 동기화 스케줄링
   - 장애 시 재시도/보정 로직 포함

### 프론트 기능

- **심볼/한글명 자동완성**  
  - 검색어 디바운스 + 캐시 활용
- **캔들 차트 (일/주/월)**
  - 차트 라이브러리로 OHLC/Volume 시각화
- **호가/체결 간단 패널** (옵션)
  - 선택 종목의 현재가/등락률/체결 정보 표시

### 성능/안정화 포인트

- API 호출 캐시(TTL) 및 백오프/리트라이
- 일중/일봉 **중복 삽입 방지** (Unique 제약)
- 장애 발생 시 최근 N일 데이터 재빌드 배치

### 예시 컴포넌트 / DTO

- 컴포넌트: `KisPanel`, `CandleChart`, `StockSearchBox`
- DTO: `KisPrice`, `KisDailyItem`, `CandleDto`

---

## 📰 CMS / 포털 기능 (게시판 · 콘텐츠 · 팝업 · 문의)

HSBS는 단순 소개 페이지가 아니라, **실제 회사 인트라넷에 가까운 CMS 구조**를 갖고 있습니다.

### 게시판 관리

- 공지/이벤트/Q&A 등 **카테고리별 게시판**
- 검색/페이징/첨부파일 지원
- 이벤트 게시판은 **응모 폼 + 참여자 관리 + 엑셀 내보내기 + 추첨 기능**까지 포함

### 콘텐츠 관리

- **영상/문서/이미지/뉴스** 등 멀티미디어 콘텐츠 관리
- 파일 업로드, 썸네일, 태그/카테고리로 분류
- 프론트에서 카드 리스트 + 상세 보기 + 동영상 플레이어 제공

### 팝업 / 배너 관리

- 메인 페이지용 **팝업/배너 등록**
- 노출 기간(시작/종료일), 위치, 사용 여부(use_tf) 설정
- 포트폴리오 메인에서 실제로 랜더링되어 노출

### 문의 관리

- 사이트 내 문의/견적/문의 폼 수집
- 관리자가 목록/상세/상태(접수/처리완료 등) 관리
- 이메일 알림/답변 템플릿(Thymeleaf 기반 메일 템플릿) 연동

---

## 🛠 운영 & 배포 체크리스트 (요약)

- **BE 로그 확인**
  - `sudo journalctl -u hsb-bo.service -f -n 100`
- **FE 빌드/배포**
  - GitHub Actions → 서버 `/var/www/html` 동기화
- **환경 변수 관리**
  - 백엔드: `application-prod.yml`
  - 프론트엔드: `.env.production`

> HSBS는 “단순 포트폴리오”를 넘어,  
> **실제 운영 가능한 SaaS/데이터/CMS 서비스 구조**를 반영한 개인 플레이그라운드입니다.




