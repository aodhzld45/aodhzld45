## 👋 Introduce

![rect](https://capsule-render.vercel.app/api?type=rect&color=gradient&text=Hello,World🐶&fontAlign=30&fontSize=30&textBg=true&desc=I'M%20HyunSeok%20Seo&descAlign=60&descAlignY=50)

---

<h3 align="center">🛠️ Tech Stack 🛠️</h3>
<p align="center">Languages & Tools</p>

<p align="center">
  <img src="https://img.shields.io/badge/HTML-E34F26?style=flat-square&logo=HTML5&logoColor=white"/>&nbsp
  <img src="https://img.shields.io/badge/CSS-1572B6?style=flat-square&logo=CSS3&logoColor=white"/>&nbsp
  <img src="https://img.shields.io/badge/JavaScript-F7DF1E?style=flat-square&logo=JavaScript&logoColor=black"/>&nbsp
  <img src="https://img.shields.io/badge/React-61DAFB?style=flat-square&logo=react&logoColor=black"/>&nbsp
  <br>
  <img src="https://img.shields.io/badge/Java-006D5C?style=flat-square&logo=java&logoColor=white"/>&nbsp
  <img src="https://img.shields.io/badge/Spring Boot-6DB33F?style=flat-square&logo=spring&logoColor=white"/>&nbsp
  <br>
  <img src="https://img.shields.io/badge/Python-3776AB?style=flat-square&logo=python&logoColor=white"/>&nbsp
  <img src="https://img.shields.io/badge/FastAPI-009688?style=flat-square&logo=fastapi&logoColor=white"/>&nbsp
  <img src="https://img.shields.io/badge/OpenAI-412991?style=flat-square&logo=openai&logoColor=white"/>&nbsp
  <img src="https://img.shields.io/badge/Vector DB-000000?style=flat-square&logo=databricks&logoColor=white"/>&nbsp
  <br>
  <img src="https://img.shields.io/badge/MySQL-4479A1?style=flat-square&logo=mysql&logoColor=white"/>&nbsp
  <img src="https://img.shields.io/badge/Oracle-F80000?style=flat-square&logo=oracle&logoColor=white"/>&nbsp
</p>

---

![Top Langs](https://github-readme-stats.vercel.app/api/top-langs/?username=aodhzld45&layout=compact&theme=dark&hide_border=true&cache_seconds=21600)
![GitHub Streak](https://github-readme-streak-stats-eight.vercel.app?user=aodhzld45&theme=dark&hide_border=true)

[![Naver Badge](https://img.shields.io/badge/Naver-03C75A?style=flat-square&logo=Naver&logoColor=white)](mailto:prking94@naver.com)

---

# 🧪 HSBS — AI 기반 서비스 아키텍처 설계 플랫폼

> 단순 포트폴리오가 아닌,  
> **AI + SaaS + CMS 아키텍처를 직접 설계하고 운영하는 개인 서비스 플랫폼**

HSBS는 실제 운영을 고려한 구조로 설계된  
**멀티 테넌트 AI SaaS + CMS 통합 플랫폼**입니다.

- 🌐 Live: https://www.hsbs.kr  
- 🔧 Backend: `hsb-bo` (Spring Boot)  
- 🎨 Frontend: `hsb-fe` (React SPA)  
- 🧠 AI Server: `hsb-brain` (FastAPI - Python)

---

# 🏗 Architecture Overview

## 🔹 Frontend
- React SPA 구조
- 동적 Section 기반 메인 페이지
- 관리자(Admin) CMS UI
- 위젯 미리보기(Preview) 패널

## 🔹 Backend
- Spring Boot REST API
- JWT 기반 인증 설계
- AuditBase 공통 컬럼 설계
- Soft Delete 구조
- Job Queue 기반 비동기 처리

## 🔹 AI Server (분리 아키텍처)
- FastAPI 기반 독립 서버
- OpenAI API 연동
- RAG 기반 문서 질의응답
- Reverse Proxy (Apache) 구성

## 🔹 Database
- MySQL
- 멀티 테넌트 설계 (tenantId / siteKey 기반)
- PromptProfile / KB / UsageLog 구조

## 🔹 Infra & DevOps
- OCI Ubuntu
- Apache Reverse Proxy
- systemd 서비스 운영(uv, jar)
- GitHub Actions CI/CD 자동 배포

---

# 🤖 HSBS SaaS Chatbot (멀티 테넌트 AI 위젯)

사내/외부 사이트에 임베드 가능한  
**멀티 테넌트 AI 챗봇 플랫폼**

각 위젯은 `siteKey`로 식별되며,  
위젯 설정 · 프롬프트 · 사용량 · 쿼터 관리까지 포함한 SaaS 구조입니다.

---

## 🔑 핵심 설계 흐름

### 1️⃣ SiteKey 발급
- 도메인 화이트리스트
- 플랜/상태 관리 (`ACTIVE / SUSPENDED / REVOKED`)
- 호출 수 / 토큰 기반 쿼터 제어

### 2️⃣ Widget 설정
- 테마 / 버블 / 컬러 / 위치 / 환영 문구
- JSON 기반 옵션 저장
- 실시간 Preview UI

### 3️⃣ Prompt Profile
- 시스템 프롬프트 / 가드레일 분리
- temperature / maxTokens 설정
- 버전 관리 구조
- tenantId 기반 독립 운영

---

## 📰 CMS / 포털 기능 (게시판 · 콘텐츠 · 팝업 · 문의 · 관리자 시스템)

HSBS는 단순 소개 페이지가 아니라,  
**실제 회사 인트라넷 수준의 CMS + 관리자 권한 시스템**을 갖춘 구조입니다.

---

# 📌 게시판 관리

- 공지 / 이벤트 / Q&A 등 **카테고리별 게시판 분리**
- 검색 / 페이징 / 첨부파일 업로드
- 게시글 등록 / 수정 / 삭제 (Soft Delete)
- 이벤트 게시판 전용 기능:
  - 응모 폼 생성
  - 참여자 목록 관리
  - 엑셀 다운로드
  - 랜덤 추첨 기능
- 관리자 권한별 접근 제어 (읽기/쓰기 제한 가능)

---

# 🎬 콘텐츠 관리

- 영상 / 문서 / 이미지 / 뉴스 등 멀티미디어 콘텐츠 관리
- 파일 업로드 + 썸네일 자동 처리
- 태그 / 카테고리 기반 분류
- 프론트:
  - 카드 리스트 UI
  - 상세 페이지
  - 동영상 플레이어 제공
- 관리자:
  - 등록 / 수정 / 삭제
  - 노출 여부(use_tf) 제어

---

# 📢 팝업 / 배너 관리

- 메인 페이지용 팝업/배너 등록
- 노출 기간 설정 (시작일 / 종료일)
- 위치 설정
- 사용 여부(use_tf) 토글
- 포트폴리오 메인 페이지에 실시간 반영

---

# 📩 문의 관리

- 사이트 내 문의/견적/문의 폼 수집
- 관리자:
  - 목록 / 상세 조회
  - 상태 변경 (접수 / 처리중 / 완료)
- 이메일 알림 연동
- Thymeleaf 기반 메일 템플릿 발송

---

# 🔐 관리자(Admin) 시스템

HSBS는 단순 CMS가 아니라  
**역할 기반 권한 관리(RBAC) 구조**를 포함합니다.

---

## 👤 관리자 계정 관리

- 관리자 등록 / 수정 / 비활성화
- 비밀번호 암호화 (BCrypt)
- 로그인 세션 관리
- JWT 기반 인증 확장 설계

---

## 🏷 권한 그룹(Role) 관리

- 관리자 권한 그룹 생성
- 그룹별 접근 가능 메뉴 설정
- Soft Delete 구조 적용

---

## 🗂 메뉴 관리

- 관리자 메뉴 등록 / 수정 / 삭제
- 메뉴 계층 구조(depth / parent_id)
- 메뉴 노출 순서 정렬
- 메뉴 활성화(use_tf) 제어

---

## 🔒 역할-메뉴 매핑 (RBAC)

- 권한 그룹별 접근 가능 메뉴 설정
- 메뉴 단위 접근 제어
- 사용자-권한 그룹 매핑 구조
- 로그인 시 현재 사용자 권한 로딩 로직 구현

---

## 📊 통계 / 로그 관리

- 콘텐츠/게시판 등록 통계
- AI 호출 로그 조회
- 토큰 사용량 집계
- 사용자 활동 로그 기반 운영 데이터 확인

---

## ⚙️ 공통 설계 원칙

- 모든 테이블 공통 컬럼:
  - use_tf
  - del_tf
  - reg_adm
  - reg_date
  - up_adm
  - up_date
  - del_adm
  - del_date
- AuditBase 기반 공통 상속 구조
- Soft Delete 전략 일관 적용
- 관리자 UI는 React 기반 모달 + 페이징 + 검색 구조 통일

---

# 🧠 Engineering Philosophy

HSBS는 단순한 기능 구현 프로젝트가 아닙니다.

저는 다음과 같은 기준으로 서비스를 설계합니다.

- 기능이 아니라 **구조를 먼저 설계합니다**
- 단일 기능이 아닌 **확장 가능한 아키텍처**를 설계합니다
- AI는 부가 기능이 아니라 **서비스 레벨에서 통합**합니다
- 운영을 고려하지 않은 설계는 하지 않습니다
- 권한·로그·통계는 기본 구성요소로 포함합니다

> 저는 “기능을 구현하는 개발자”가 아니라  
> **확장 가능한 서비스 구조를 설계하는 개발자**를 지향합니다.
