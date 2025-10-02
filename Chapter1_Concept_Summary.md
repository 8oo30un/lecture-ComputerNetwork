# Chapter 1: Computer Networks and the Internet - 시험 대비 핵심 개념 정리

## 1. 인터넷의 정의와 관점

### "Nuts and Bolts" 관점 (기술적 관점)

- **수백만 개의 연결된 컴퓨팅 장치**: Host 또는 End System
- **통신 링크**: Fiber, copper, radio, satellite
- **전송 속도**: Bandwidth (bps 단위)
- **패킷 스위치**: Router와 Switch (Layer 3 장비)
- **"Network of Networks"**: ISP들이 상호 연결
- **프로토콜**: TCP, IP, HTTP, Skype, 802.11 등
- **표준 문서**: RFC (Request for Comments), IETF

### "Service View" 관점 (서비스 관점)

- **서비스 제공 기반 시스템**: Web, VoIP, email, games, e-commerce, social nets
- **Socket Interface**: 코딩 가능한 인터페이스
- **Distributed Application**: End-to-end 통신 지원

### 프로토콜 (Protocol)

**정의**: 네트워크 개체 간 메시지의 **형식, 순서, 행동**을 정의

- **형식**: 메시지 구조
- **순서**: 메시지 전송/수신 순서
- **행동**: 메시지 처리 시 취해야 할 동작

---

## 2. 네트워크 구조

### Network Edge (네트워크 가장자리)

- **Host**: Clients and Servers
- **Data Center**: 서버가 위치한 곳
- **Access Networks**: End system이 인터넷에 접근하는 네트워크
- **Physical Media**: Wired/Wireless 통신 링크

### Network Core (네트워크 핵심)

- **상호 연결된 Router들**
- **고속 라우터, 스위치**
- **주요 목적**: 데이터를 최적 경로로 빠르고 안정적으로 전달

---

## 3. Access Networks (접속 네트워크)

### Residential Access Networks (가정용)

#### DSL (Digital Subscriber Line)

- **기존 전화선** 활용
- **전화와 인터넷 동시 사용** 가능
- **비대칭 구조**: 업로드 < 다운로드
- **장점**: 케이블 설치 불필요

#### Cable-based Access

- **케이블 TV 네트워크** 활용
- **FDM (Frequency Division Multiplexing)**: 주파수 분할 다중화
- **HFC (Hybrid Fiber Coax)**: 광섬유 + 동축 케이블
- **비대칭 구조**: 업로드 < 다운로드
- **문제점**: 사용자 수 증가 시 속도 저하

#### FTTH (Fiber To The Home)

- **광섬유 직접 연결**
- **초당 기가바이트 범위** 전송 속도 가능
- **실제**: 수십~수백 Mbps

### Wireless Access Networks

- **WLANS**: WiFi (IEEE 802.11b/g/n/ac/ax)
- **Wide-area Cellular**: 3G/4G/5G
- **차이점**: Mobility (이동성)

### Enterprise Networks

- **회사, 대학** 등에서 사용
- **Ethernet**: Wired (100Mbps, 1Gbps, 10Gbps)
- **WiFi**: Wireless (11, 54, 450 Mbps)

---

## 4. Physical Media (물리적 매체)

### Guided Media (유도 매체)

- **Twisted Pair (TP)**: 두 개의 절연된 구리선
- **Coaxial Cable**: 두 개의 동심 구리 도체
- **Fiber Optic Cable**: 빛 펄스 전송, 고속, 낮은 오류율

### Unguided Media (비유도 매체)

- **Wireless Radio**: 전자기 스펙트럼
- **영향 요인**: 반사, 장애물, 간섭

---

## 5. Network Core (네트워크 핵심)

### Packet Switching

- **데이터를 패킷으로 분할**
- **독립적 라우팅**
- **Store-and-Forward**: 전체 패킷 수신 후 전송

#### Transmission Delay

- **공식**: L/R (패킷 길이 / 링크 전송 속도)
- **End-to-End Delay**: 2L/R (전파 지연 0 가정)

#### Packet Queueing and Loss

- **원인**: 도착 속도 > 전송 속도
- **결과**: Queueing delay, 패킷 손실

### Two Key Network-Core Functions

#### 1. Forwarding (전달)

- **Local Action**: 입력 링크 → 출력 링크
- **Forwarding Table**: Header value → Output link

#### 2. Routing (라우팅)

- **Global Action**: 출발지 → 목적지 경로 결정
- **Routing Algorithms**: 목적지 주소 기반

---

## 6. Circuit Switching vs Packet Switching

### Circuit Switching (회선 스위칭)

- **전용 자원 할당**
- **보장된 성능**
- **FDM**: 주파수 분할 (고유 대역 할당)
- **TDM**: 시간 분할 (시간 슬롯 할당)

### Packet Switching (패킷 스위칭)

- **자원 공유**
- **더 많은 사용자 지원**
- **효율적 자원 활용**
- **버스트성 데이터에 적합**

### 비교

| 구분      | Circuit Switching | Packet Switching |
| --------- | ----------------- | ---------------- |
| 자원 할당 | 전용              | 공유             |
| 성능      | 보장됨            | 가변적           |
| 효율성    | 낮음              | 높음             |
| 사용자 수 | 제한적            | 많음             |

---

## 7. Internet Structure: Network of Networks

### 계층 구조

1. **Access ISP**: 최종 사용자 연결
2. **Regional ISP**: 지역 네트워크 (KT, LG U+)
3. **Global ISP**: 전역 네트워크
4. **Tier 1 ISP**: 최상위 계층

### 연결 방식

- **IXP (Internet Exchange Point)**: ISP 간 트래픽 교환
- **Peering Link**: 직접 연결
- **Content Provider Networks**: 콘텐츠 제공업체 네트워크

### 콘텐츠 제공업체가 사설 네트워크 운영하는 이유

- **성능 최적화**: 지연 시간 감소
- **비용 절감**: 중간 ISP 우회
- **사용자 경험 향상**: 빠른 콘텐츠 전달

---

## 8. 시험 출제 포인트

### 핵심 개념

1. **프로토콜의 정의 범위** (형식, 순서, 행동)
2. **인터넷 구조**: Network of Networks
3. **Access Network 기술**: DSL, Cable, FTTH, WiFi
4. **Physical Media**: 유도/비유도 매체
5. **Packet vs Circuit Switching**
6. **Network Core 기능**: Forwarding, Routing
7. **지연 유형**: Transmission, Queueing, Processing, Propagation
8. **인터넷 계층 구조**: ISP 계층

### 계산 문제

- **Transmission Delay**: L/R
- **End-to-End Delay**: 2L/R
- **Throughput 계산**: 병목 링크 찾기
- **Traffic Intensity**: La/R

### 비교 분석

- **FDM vs TDM**
- **Guided vs Unguided Media**
- **Wired vs Wireless Access**
- **Circuit vs Packet Switching**

---

## 9. 암기 포인트

### 속도 단위

- **bps**: bits per second
- **Bandwidth**: 전송 속도

### 지연 유형

1. **Transmission Delay**: 패킷 전송 시간
2. **Queueing Delay**: 버퍼 대기 시간
3. **Processing Delay**: 라우터 처리 시간
4. **Propagation Delay**: 물리적 전파 시간

### 프로토콜 계층 (상→하)

**Application → Transport → Network → Link → Physical**

### Access Network 기술

- **DSL**: 전화선, 비대칭
- **Cable**: TV 케이블, FDM, 비대칭
- **FTTH**: 광섬유, 고속
- **WiFi**: 무선, 이동성 제한
- **Cellular**: 무선, 높은 이동성
