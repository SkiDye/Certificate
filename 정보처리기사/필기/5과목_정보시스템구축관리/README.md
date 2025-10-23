# 5과목: 정보시스템 구축관리

## 📌 과목 개요
소프트웨어 개발 방법론, 프로젝트 관리, 보안에 관한 내용을 다룹니다.

## 📚 주요 학습 내용

### 1. 소프트웨어 개발 방법론 활용
- **개발 방법론**
  - 폭포수 모형 (Waterfall)
  - 프로토타입 모형
  - 나선형 모형
  - 애자일 (Agile)

- **애자일 방법론**
  - 스크럼 (Scrum)
  - XP (eXtreme Programming)
  - 칸반 (Kanban)
  - 린 (Lean)

### 2. IT 프로젝트 정보시스템 구축관리
- **프로젝트 관리**
  - 일정 관리: PERT, CPM, 간트 차트
  - 비용 관리: LOC, FP
  - 위험 관리

- **소프트웨어 품질**
  - ISO/IEC 9126
  - ISO/IEC 25010
  - CMMI

### 3. 소프트웨어 개발 보안 구축
- **시큐어 코딩**
  - 입력값 검증
  - SQL Injection 방지
  - XSS 방지
  - CSRF 방지

- **보안 약점**
  - OWASP Top 10
  - CWE

### 4. 시스템 보안 구축
- **암호화 기법**
  - 대칭키: DES, AES, SEED
  - 비대칭키: RSA, ECC
  - 해시: MD5, SHA

- **보안 프로토콜**
  - SSL/TLS
  - IPSec
  - VPN

- **접근 통제**
  - 인증 (Authentication)
  - 인가 (Authorization)
  - 계정 관리

- **보안 공격 기법**
  - DoS, DDoS
  - 스니핑, 스푸핑
  - 피싱, 파밍

## 🎯 핵심 키워드

### 소프트웨어 개발 방법론

**폭포수 모형**
- 순차적 진행
- 이전 단계 완료 후 다음 단계
- 요구사항 변경 어려움

**애자일 방법론**
- 반복적, 점진적 개발
- 고객과의 지속적 소통
- 변화에 유연한 대응

**스크럼**
- 스프린트 (2~4주)
- 데일리 스크럼
- 스크럼 마스터, 프로덕트 오너

### 암호화 기법

| 구분 | 알고리즘 | 특징 |
|-----|---------|------|
| 대칭키 | DES, 3DES, AES, SEED | 빠름, 키 배송 문제 |
| 비대칭키 | RSA, ECC | 느림, 키 배송 안전 |
| 해시 | MD5, SHA-1, SHA-256 | 단방향, 무결성 검증 |

### 보안 공격 유형

**DoS/DDoS**
- Ping of Death
- Smurf Attack
- SYN Flooding
- UDP Flooding

**스니핑/스푸핑**
- 스니핑: 패킷 도청
- 스푸핑: 신분 위조 (IP, ARP, DNS)

**기타**
- 피싱: 가짜 사이트로 유인
- 파밍: DNS 변조
- SQL Injection: SQL 삽입 공격
- XSS: 스크립트 삽입 공격

### PERT/CPM

**PERT (Program Evaluation and Review Technique)**
- 낙관치, 정상치, 비관치 사용
- 기대시간 = (낙관 + 4×정상 + 비관) / 6

**CPM (Critical Path Method)**
- 주 경로(Critical Path) 식별
- 여유시간 계산

### 품질 모델

**ISO/IEC 25010**
1. 기능 적합성
2. 성능 효율성
3. 호환성
4. 사용성
5. 신뢰성
6. 보안성
7. 유지보수성
8. 이식성

## 📝 학습 체크리스트
- [ ] 개발 방법론 종류와 특징 이해
- [ ] 애자일 vs 폭포수 모형 비교
- [ ] 암호화 기법 분류 (대칭키/비대칭키/해시)
- [ ] 주요 보안 공격 기법 정리
- [ ] OWASP Top 10 암기
- [ ] 시큐어 코딩 가이드 이해
- [ ] PERT/CPM 계산 연습

## 💡 암기 팁

**암호화 알고리즘**
- **대칭키**: "디트에시" (DES-3DES-AES-SEED)
- **비대칭키**: "알이" (RSA-ECC)
- **해시**: "엠샤" (MD5-SHA)

**스크럼 3대 역할**
- Product Owner (제품 책임자)
- Scrum Master (스크럼 마스터)
- Development Team (개발팀)

**DoS 공격 유형**
- Ping of Death: 큰 패킷
- Smurf: ICMP 증폭
- SYN Flooding: 3-way handshake 악용

## ⚠️ 실기 연계
- 암호화 알고리즘 이름 (영문 정확히)
- 보안 공격 기법 (약어 암기)
- 개발 방법론 특징
