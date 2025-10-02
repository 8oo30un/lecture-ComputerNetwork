# Chapter 2: Application Layer

## 📁 파일 목록

### 📚 Chapter2_Concept_Summary.md

- **내용**: Chapter 2 애플리케이션 계층의 핵심 개념 정리
- **포함 내용**:
  - 네트워크 애플리케이션 기본 개념
  - Client-Server vs P2P 아키텍처 비교
  - 프로세스 간 통신 (소켓, 주소 지정)
  - 전송 서비스 요구사항 (무결성, 타이밍, 처리량, 보안)
  - TCP vs UDP 프로토콜 비교
  - HTTP (메시지 구조, 연결 방식, 상태 코드, HTTP/2, HTTP/3)
  - Cookies (상태 유지 메커니즘)
  - 웹 캐싱 (성능 향상, 조건부 GET)
  - E-mail (SMTP, POP3, IMAP)
  - DNS (계층 구조, 레코드 타입, 해석 과정)
  - P2P (파일 배포, BitTorrent, Blockchain)
  - 비디오 스트리밍 (DASH, CDN)
- **용도**: 시험 대비 핵심 개념 암기 및 이해

## 🎯 주요 학습 포인트

1. **애플리케이션 아키텍처**: Client-Server vs P2P 모델 이해
2. **전송 프로토콜**: TCP vs UDP 특성과 사용 사례
3. **HTTP**: 메시지 구조, 연결 방식, 상태 코드
4. **DNS**: 계층 구조, 레코드 타입, 해석 과정
5. **P2P**: 파일 배포 시간 계산, BitTorrent 동작 원리
6. **스트리밍**: DASH, CDN의 역할과 동작

## 📝 시험 출제 포인트

- **계산 문제**: HTTP 응답 시간, P2P 배포 시간, 캐시 성능
- **비교 분석**: TCP/UDP, SMTP/HTTP, POP3/IMAP, Client-Server/P2P
- **개념 이해**: DNS 구조, HTTP 메시지, P2P 동작 방식
- **암기 사항**: 포트 번호, 상태 코드, 레코드 타입

## 📊 주요 공식

### HTTP 응답 시간

- **Non-persistent**: 2RTT + 파일 전송 시간
- **Persistent**: RTT + 파일 전송 시간

### 파일 배포 시간

- **Client-Server**: Dc-s = max{NF/us, F/dmin}
- **P2P**: Dp2p = max{F/us, F/dmin, NF/(us + Σui)}

### DNS 응답 시간

- **캐시 없음**: RTT_l + 3×RTT_r
- **캐시 있음**: RTT_l
