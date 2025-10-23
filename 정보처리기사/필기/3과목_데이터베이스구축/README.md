# 3과목: 데이터베이스 구축

## 📌 과목 개요
데이터베이스 설계부터 SQL 작성까지 DB 전반을 다룹니다. **실기와 연계되는 중요 과목**입니다.

## 📚 주요 학습 내용

### 1. SQL 응용
- **DDL (Data Definition Language)**
  - CREATE, ALTER, DROP, TRUNCATE

- **DML (Data Manipulation Language)**
  - SELECT, INSERT, UPDATE, DELETE

- **DCL (Data Control Language)**
  - GRANT, REVOKE

- **TCL (Transaction Control Language)**
  - COMMIT, ROLLBACK, SAVEPOINT

### 2. SQL 활용
- **집계 함수**
  - COUNT, SUM, AVG, MAX, MIN
  - GROUP BY, HAVING

- **조인 (JOIN)**
  - INNER JOIN
  - LEFT/RIGHT/FULL OUTER JOIN
  - CROSS JOIN
  - SELF JOIN

- **서브쿼리**
  - 단일 행 서브쿼리
  - 다중 행 서브쿼리 (IN, ANY, ALL, EXISTS)
  - 상호연관 서브쿼리

### 3. 논리 데이터베이스 설계
- **정규화**
  - 1NF: 원자값
  - 2NF: 부분 함수 종속 제거
  - 3NF: 이행 함수 종속 제거
  - BCNF: 결정자가 후보키

- **이상 현상**
  - 삽입 이상
  - 삭제 이상
  - 갱신 이상

- **ER 모델**
  - 개체(Entity), 속성(Attribute), 관계(Relationship)

### 4. 물리 데이터베이스 설계
- **인덱스 설계**
  - B-Tree, B+Tree
  - 클러스터 인덱스 vs 논클러스터 인덱스

- **뷰(View) 설계**
  - 논리적 독립성
  - 보안성

- **파티션 설계**
  - Range, Hash, List

### 5. 데이터 전환
- **데이터 전환**
  - ETL (Extract, Transform, Load)
  - 데이터 검증

## 🎯 핵심 키워드

### SQL 명령어 분류
| 분류 | 명령어 | 설명 |
|-----|--------|------|
| DDL | CREATE, ALTER, DROP, TRUNCATE | 테이블 구조 정의 |
| DML | SELECT, INSERT, UPDATE, DELETE | 데이터 조작 |
| DCL | GRANT, REVOKE | 권한 제어 |
| TCL | COMMIT, ROLLBACK, SAVEPOINT | 트랜잭션 제어 |

### 정규화 단계
- **1NF**: 모든 속성이 원자값 (반복 그룹 제거)
- **2NF**: 1NF + 부분 함수 종속 제거
- **3NF**: 2NF + 이행 함수 종속 제거
- **BCNF**: 3NF + 모든 결정자가 후보키

### JOIN 종류
```sql
-- INNER JOIN (교집합)
SELECT * FROM A INNER JOIN B ON A.id = B.id;

-- LEFT OUTER JOIN (A 전체)
SELECT * FROM A LEFT JOIN B ON A.id = B.id;

-- RIGHT OUTER JOIN (B 전체)
SELECT * FROM A RIGHT JOIN B ON A.id = B.id;

-- FULL OUTER JOIN (합집합)
SELECT * FROM A FULL OUTER JOIN B ON A.id = B.id;
```

### ACID 특성
- **Atomicity (원자성)**: All or Nothing
- **Consistency (일관성)**: 일관된 상태 유지
- **Isolation (고립성)**: 독립적 실행
- **Durability (지속성)**: 영구적 저장

## 📝 학습 체크리스트
- [ ] SQL 명령어 종류별 분류 암기
- [ ] 정규화 1NF~BCNF 이해
- [ ] JOIN 종류와 문법 숙지
- [ ] 집계 함수 및 GROUP BY 활용
- [ ] 서브쿼리 작성 연습
- [ ] 트랜잭션 ACID 특성 암기

## 💡 암기 팁
- **DDL**: "창조 변경 삭제" (CREATE ALTER DROP)
- **DML**: "선삽갱삭" (SELECT INSERT UPDATE DELETE)
- **정규화**: "원부이결" (원자값-부분종속-이행종속-결정자)
- **ACID**: "원일고지" (원자성-일관성-고립성-지속성)

## ⚠️ 실기 연계
이 과목의 SQL 내용은 **실기 시험에서 가장 많은 배점**을 차지합니다.
반드시 손으로 직접 SQL 문을 작성하는 연습을 하세요!
