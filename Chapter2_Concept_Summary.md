# Chapter 2: Application Layer - 시험 대비 핵심 개념 정리

## 1. 네트워크 애플리케이션 기본 개념

### 네트워크 애플리케이션 작성 방법

1. **프로그램 작성**: End system에서 실행
2. **네트워크를 통해 통신**: 다른 장치들과 데이터 주고받기
3. **브라우저 소프트웨어와 통신**: 웹 브라우저를 통한 상호작용

### 핵심 특징

- **네트워크 코어 장치용 소프트웨어 불필요**: 라우터, 스위치는 데이터 전달만 담당
- **빠른 앱 개발/전파**: End system에서만 실행되므로 전체 네트워크에 영향 없음

---

## 2. 네트워크 애플리케이션 아키텍처

### Client-Server Paradigm (클라이언트-서버 모델)

#### Server (서버)

- **상시 호스트**: 항상 네트워크에 연결
- **영구 주소**: 고정된 IP 주소 보유
- **확장 가능성**: 데이터 센터에서 서버 성능 확장
- **예시**: HTTP(웹), IMAP(이메일), FTP(파일 전송)

#### Client (클라이언트)

- **서버와 접속/통신**: 서버에 요청하고 응답 받기
- **간헐적 연결**: 필요할 때만 연결
- **동적 IP 주소**: ISP로부터 변경 가능한 IP 주소
- **직접 통신 불가**: 모든 통신은 서버를 통해

### Peer-to-Peer (P2P) Architecture

#### 특징

- **상시 가동 서버 없음**: 중앙 서버 불필요
- **직접 통신**: Peer 간 직접 데이터 교환
- **자체 확장성**: 새로운 peer = 새로운 용량 + 수요
- **간헐적 연결**: IP 주소 변경 가능
- **복잡한 관리**: 상태 관리의 어려움

#### 예시

- **P2P 파일 공유**: BitTorrent
- **스트리밍**: 칸칸
- **VoIP**: Skype
- **블록체인**

---

## 3. 프로세스 간 통신

### Process (프로세스)

- **정의**: 호스트 내에서 실행되는 프로그램
- **Client Process**: 통신을 시작하는 프로세스 (브라우저)
- **Server Process**: 연락을 기다리는 프로세스 (웹서버)

### 통신 방식

- **같은 호스트**: IPC (Inter-Process Communication)
- **다른 호스트**: TCP/IP 프로토콜을 통한 메시지 교환

### Socket (소켓)

- **정의**: 네트워크 데이터 송수신을 위한 프로그래밍 인터페이스
- **문과 유사**: 송신 프로세스가 메시지를 문 밖으로 밀어냄
- **양쪽에 필요**: 통신에는 양쪽에 소켓이 하나씩 필요

### Addressing Processes (프로세스 주소 지정)

- **식별자**: IP 주소 + 포트 번호
- **포트 번호 예시**:
  - HTTP server: 80
  - Mail server: 25

---

## 4. 애플리케이션 계층 프로토콜

### 정의하는 내용

1. **교환되는 메시지 유형**: Request, Response
2. **메시지 구문**: 필드 구성 방식
3. **메시지 의미**: 각 필드의 의미
4. **프로토콜 유형**:
   - **오픈 프로토콜**: RFC에 정의 (HTTP, SMTP)
   - **독점 프로토콜**: 특정 회사 소유 (Skype)

---

## 5. 전송 서비스 요구사항

### 주요 요구사항

#### 1. Data Integrity (데이터 무결성)

- **100% 안정적 전송 필요**: 이미지 파일
- **일부 손실 허용**: Zoom 오디오

#### 2. Timing (타이밍)

- **짧은 지연 필요**: 화상 통화
- **지연 허용**: 이메일

#### 3. Throughput (처리량)

- **최소 처리량 필요**: 대용량 파일 전송
- **처리량 무관**: 텍스트 기반 애플리케이션

#### 4. Security (보안)

- **암호화, 데이터 무결성**

### 애플리케이션별 요구사항

| 애플리케이션          | 데이터 무결성 | 타이밍 | 처리량 |
| --------------------- | ------------- | ------ | ------ |
| 파일 전송             | 필요          | 불필요 | 높음   |
| 이메일                | 필요          | 불필요 | 낮음   |
| 웹 문서               | 필요          | 불필요 | 중간   |
| 인터랙티브 텍스트     | 필요          | 필요   | 낮음   |
| 인터랙티브 멀티미디어 | 불필요        | 필요   | 중간   |
| 비디오 스트리밍       | 불필요        | 필요   | 높음   |

---

## 6. 인터넷 전송 프로토콜

### TCP Service

- **안정적 전송**: 데이터 손실 없이 전송 보장
- **흐름 제어**: 송신자가 수신자를 압도하지 않음
- **혼잡 제어**: 네트워크 과부하 시 속도 조절
- **연결 지향**: 클라이언트-서버 간 연결 설정 필요
- **제공하지 않음**: 타이밍, 최소 처리량, 보안

### UDP Service

- **빠른 전송**: 신뢰성 없이 빠른 전송
- **제공하지 않음**: 안정성, 흐름제어, 혼잡제어, 타이밍, 처리량 보장, 보안, 연결 설정
- **사용 예**: 실시간 애플리케이션 (스트리밍, 게임)

### TCP vs UDP 비교

| 구분      | TCP        | UDP            |
| --------- | ---------- | -------------- |
| 신뢰성    | 높음       | 낮음           |
| 속도      | 느림       | 빠름           |
| 연결 설정 | 필요       | 불필요         |
| 흐름 제어 | 있음       | 없음           |
| 혼잡 제어 | 있음       | 없음           |
| 사용 예   | 웹, 이메일 | 스트리밍, 게임 |

---

## 7. Web and HTTP

### HTTP (HyperText Transfer Protocol)

- **웹의 애플리케이션 계층 프로토콜**
- **클라이언트-서버 모델**
- **TCP 사용**: 포트 80에서 연결
- **Stateless**: 과거 클라이언트 요청 정보 유지하지 않음

### HTTP 연결 방식

#### Non-persistent HTTP (비영구 HTTP)

- **특징**: 하나의 객체마다 새로운 TCP 연결
- **응답 시간**: 2RTT + 파일 전송 시간
- **단점**: 여러 객체 시 여러 연결 필요

#### Persistent HTTP (영구 HTTP)

- **특징**: 하나의 TCP 연결로 여러 객체 전송
- **장점**: 네트워크 부하 감소, 성능 향상
- **응답 시간**: RTT 감소

### HTTP 메시지

#### Request Message

- **구조**:

  - Request Line: Method + URL + Version
  - Header Lines: 추가 정보
  - Body: 전송 데이터

- **주요 Methods**:
  - **GET**: 리소스 검색
  - **POST**: 폼 데이터 전송
  - **PUT**: 파일 업로드/대체
  - **HEAD**: 헤더 정보만 요청

#### Response Message

- **구조**:

  - Status Line: 프로토콜 + 상태 코드 + 상태 문구
  - Header Lines: 서버 정보
  - Body: 요청된 리소스

- **주요 Status Codes**:
  - **200 OK**: 요청 성공
  - **301 Moved Permanently**: 객체 위치 이동
  - **400 Bad Request**: 요청 메시지 이해 불가
  - **404 Not Found**: 문서 없음
  - **505 HTTP Version Not Supported**: 지원되지 않는 버전

### HTTP/2

- **목표**: 다중 객체 요청 지연 감소
- **개선사항**:
  - 객체 우선순위 지정 가능
  - 요청되지 않은 객체도 푸시 가능
  - 프레임으로 분할하여 HOL 차단 완화
  - 멀티플렉싱 지원

### HTTP/3

- **UDP 기반**: QUIC (Quick UDP Internet Connection)
- **보안 강화**: 암호화 포함
- **성능 향상**: 객체별 오류 및 혼잡 제어

---

## 8. Cookies (쿠키)

### 목적

- **상태 유지**: HTTP의 stateless 특성 보완
- **인증**: 로그인 상태 유지
- **쇼핑 카트**: 장바구니 상태 유지
- **추천**: 사용자 활동 기반 추천
- **세션 관리**: 웹 메일 등

### 구성 요소

1. **HTTP 응답 메시지의 쿠키 헤더 라인**
2. **HTTP 요청 메시지의 쿠키 헤더 라인**
3. **사용자 호스트의 쿠키 파일**
4. **웹사이트 백엔드 데이터베이스**

### 개인정보 보호 이슈

- **추적 가능**: 사이트에서 사용자 정보 수집
- **타사 쿠키**: 여러 사이트에서 공용 ID 추적

---

## 9. Web Caching (웹 캐싱)

### 목적

- **응답 시간 단축**: 클라이언트에 더 가까운 위치
- **트래픽 감소**: 접속 링크 트래픽 감소
- **효율적 콘텐츠 제공**: 네트워크 효율성 향상

### 동작 방식

1. **캐시에 객체 있음**: 캐시에서 클라이언트로 반환
2. **캐시에 객체 없음**: 원본 서버에서 요청 후 캐시 저장 후 반환

### 캐시 특징

- **클라이언트와 서버 역할 모두 수행**
- **ISP에서 설치**: 대학, 회사, 주거용
- **CDN과 유사**: Content Delivery Network

### 성능 계산 예시

- **캐시 없음**: Access link utilization = 0.97 (97%)
- **캐시 있음 (히트율 40%)**: Access link utilization = 0.58 (58%)

### Conditional GET

- **목표**: 최신 버전 확인 후 필요시에만 전송
- **방법**: If-Modified-Since 헤더 사용
- **응답**:
  - **304 Not Modified**: 최신 버전
  - **200 OK**: 새로운 버전 전송

---

## 10. E-mail

### 구성 요소

1. **User Agent**: 메일 리더 (Outlook, iPhone 메일)
2. **Mail Server**: 수신/발신 메일 관리
3. **SMTP**: 메일 간 전송 프로토콜

### SMTP (Simple Mail Transfer Protocol)

- **특징**:
  - TCP 사용 (포트 25)
  - 직접 전송
  - 3단계: 핸드셰이킹, 메시지 전송, 연결 종료
  - 명령/응답 상호작용
  - 7비트 ASCII
  - 영구 연결 사용

### SMTP vs HTTP 비교

| 구분        | SMTP                        | HTTP                    |
| ----------- | --------------------------- | ----------------------- |
| 전송 방식   | Push                        | Pull                    |
| 연결        | 영구 연결                   | 비영구 연결 가능        |
| 메시지      | 7비트 ASCII                 | 바이너리 가능           |
| 메시지 구조 | 여러 객체를 하나의 메시지로 | 각 객체마다 별도 메시지 |

### Mail Access Protocols

#### POP3 (Post Office Protocol - Version 3)

- **특징**: 간단한 다운로드 중심
- **제한적**: 서버 기반 관리 기능 부족

#### IMAP (Internet Mail Access Protocol)

- **특징**: 서버 기반 관리 기능
- **기능**: 검색, 삭제, 폴더 관리

#### HTTP

- **사용**: Gmail, Hotmail, Yahoo! Mail
- **특징**: 웹 기반 인터페이스

---

## 11. DNS (Domain Name System)

### 정의

- **분산된 계층적 데이터베이스**
- **도메인 이름을 IP 주소로 변환**

### DNS 구조

#### 계층 구조

1. **Root Servers**: DNS 쿼리의 출발점
2. **Top-Level Domain (TLD)**: .com, .org, .net, .edu
3. **Authoritative Servers**: 특정 도메인의 최종 DNS 정보

#### 서버 유형

- **Root Name Servers**: ICANN이 관리, 전 세계 분산
- **TLD Servers**: .com, .org, .net, .edu, 국가 도메인
- **Authoritative DNS Servers**: 조직의 DNS 서버
- **Local DNS Servers**: ISP의 기본 네임 서버

### DNS Resolution (이름 해석)

#### Iterated Query (반복 쿼리)

- **특징**: 서버가 "다음 서버에 물어보세요" 응답
- **클라이언트**: 여러 서버를 순차적으로 쿼리

#### Recursive Query (재귀 쿼리)

- **특징**: 서버가 클라이언트를 대신하여 쿼리
- **장점**: 클라이언트 부담 감소

### DNS Records

| Type  | Name       | Value                     | 설명                  |
| ----- | ---------- | ------------------------- | --------------------- |
| A     | hostname   | IP address                | 도메인 이름 → IP 주소 |
| NS    | domain     | authoritative name server | 도메인 → 권한 서버    |
| CNAME | alias name | canonical name            | 별칭 → 정식 이름      |
| MX    | domain     | mail server name          | 도메인 → 메일 서버    |

### DNS Caching

- **목적**: RTT 감소
- **TTL**: Time To Live (캐시 만료 시간)
- **문제**: 오래된 정보 가능성

---

## 12. P2P Applications

### P2P 파일 배포

#### Client-Server vs P2P 비교

**Client-Server 배포 시간**:

```
Dc-s = max{NF/us, F/dmin}
```

- N: 클라이언트 수
- F: 파일 크기
- us: 서버 업로드 속도
- dmin: 최소 클라이언트 다운로드 속도

**P2P 배포 시간**:

```
Dp2p = max{F/us, F/dmin, NF/(us + Σui)}
```

- ui: 클라이언트 i의 업로드 속도

#### P2P의 장점

- **확장성**: 클라이언트 수 증가해도 성능 유지
- **자원 공유**: 각 피어가 업로드에도 참여

### BitTorrent

#### 구성 요소

- **File**: 256KB 청크로 분할
- **Tracker**: 참여 피어 추적
- **Torrent**: 청크를 교환하는 피어 그룹

#### 동작 방식

1. **새 피어 합류**: Tracker에서 피어 목록 받기
2. **청크 요청**: 가장 희귀한 청크부터 요청
3. **Tit-for-tat**: 가장 빠른 4명에게만 청크 전송
4. **Optimistic Unchoke**: 30초마다 무작위 피어 선택

#### 특징

- **공정성**: 빠른 업로드에 보상
- **확장성**: 새 피어에게 기회 제공
- **Churn**: 피어의 유동적 참여

### Blockchain

- **정의**: 암호화로 연결된 블록들의 목록
- **특징**: 탈중앙화된 P2P 네트워크
- **Blockchain Trilemma**: 보안, 탈중앙화, 확장성 중 2가지만 최적화
- **Gossip Protocol**: 전염병 확산 방식 기반 데이터 전파

---

## 13. Video Streaming and CDNs

### Video Streaming

#### 비디오 특성

- **이미지 시퀀스**: 일정 속도로 표시 (24 images/sec)
- **픽셀 배열**: 각 픽셀은 비트로 표현
- **코딩**:
  - **Spatial Coding**: 이미지 내 중복 제거
  - **Temporal Coding**: 이미지 간 중복 제거

#### CBR vs VBR

- **CBR (Consistent Bit Rate)**: 일정한 인코딩 속도
- **VBR (Variable Bit Rate)**: 코딩 양에 따라 속도 변경

#### 스트리밍 방식

- **스트리밍**: 초반 재생 + 후반 전송 동시 진행
- **연속 재생 제약**: 원본 타이밍과 일치해야 함
- **버퍼링**: 네트워크 지연 보정

### DASH (Dynamic Adaptive Streaming over HTTP)

#### 구성 요소

- **Server**: 비디오를 다양한 속도로 인코딩된 청크로 저장
- **Manifest File**: 청크 URL 제공
- **Client**: 대역폭 측정하여 적절한 청크 요청

#### 클라이언트 인텔리전스

- **언제 요청할지**: 버퍼 고갈/오버플로우 방지
- **어떤 속도로**: 사용 가능한 대역폭에 따라
- **어디서**: 클라이언트와 가까운 서버에서

### CDN (Content Distribution Networks)

#### 문제점 해결

- **단일 메가 서버의 한계**:
  - 단일 장애 지점
  - 네트워크 혼잡
  - 긴 경로
  - 비효율적 복사본 전송

#### CDN 전략

- **Enter Deep**: 접속 네트워크 깊숙이 배치 (Akamai)
- **Bring Home**: 접속 네트워크 근처에 대규모 클러스터 (Limelight)

#### CDN 동작

1. **콘텐츠 요청**: 클라이언트가 비디오 URL 요청
2. **DNS 해석**: CNAME을 통해 CDN URL 반환
3. **최적 서버 선택**: 가장 가까운 CDN 서버에서 스트리밍

---

## 14. 시험 출제 포인트

### 핵심 개념

1. **애플리케이션 아키텍처**: Client-Server vs P2P
2. **전송 프로토콜**: TCP vs UDP 특성과 사용 사례
3. **HTTP**: 메시지 구조, 연결 방식, 상태 코드
4. **DNS**: 계층 구조, 레코드 타입, 해석 과정
5. **P2P**: 파일 배포 시간 계산, BitTorrent 동작
6. **스트리밍**: DASH, CDN의 역할

### 계산 문제

- **HTTP 응답 시간**: Non-persistent vs Persistent
- **캐시 성능**: 히트율에 따른 지연 시간 계산
- **P2P 배포 시간**: Client-Server vs P2P 비교
- **DNS 응답 시간**: 캐시 유무에 따른 차이

### 비교 분석

- **SMTP vs HTTP**
- **POP3 vs IMAP**
- **Iterated vs Recursive Query**
- **Enter Deep vs Bring Home**

### 암기 사항

- **포트 번호**: HTTP(80), SMTP(25), POP3(110), IMAP(143)
- **HTTP 메서드**: GET, POST, PUT, HEAD
- **HTTP 상태 코드**: 200, 301, 400, 404, 505
- **DNS 레코드 타입**: A, NS, CNAME, MX
- **비디오 코딩**: MPEG 1(1.5Mbps), MPEG 2(3-6Mbps), MPEG 4(64Kbps-12Mbps)

---

## 15. 주요 공식 정리

### HTTP 응답 시간

- **Non-persistent**: 2RTT + 파일 전송 시간
- **Persistent**: RTT + 파일 전송 시간

### 파일 배포 시간

- **Client-Server**: Dc-s = max{NF/us, F/dmin}
- **P2P**: Dp2p = max{F/us, F/dmin, NF/(us + Σui)}

### DNS 응답 시간

- **캐시 없음**: RTT_l + 3×RTT_r
- **캐시 있음**: RTT_l

### 캐시 성능

- **Access Link Utilization**: 트래픽 / 링크 용량
- **평균 지연**: 캐시 히트율 × 캐시 지연 + 캐시 미스율 × 원본 지연
