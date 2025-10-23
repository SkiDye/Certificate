# SQL 기본 문법 총정리

## 📌 DDL (Data Definition Language) - 데이터 정의어

### CREATE (생성)
```sql
-- 테이블 생성
CREATE TABLE 학생 (
    학번 CHAR(10) PRIMARY KEY,
    이름 VARCHAR(20) NOT NULL,
    학과 VARCHAR(30),
    학년 INT DEFAULT 1,
    FOREIGN KEY (학과) REFERENCES 학과(학과명)
);

-- 인덱스 생성
CREATE INDEX idx_name ON 학생(이름);

-- 뷰 생성
CREATE VIEW 학생_뷰 AS
SELECT 학번, 이름 FROM 학생 WHERE 학년 = 1;
```

### ALTER (수정)
```sql
-- 컬럼 추가
ALTER TABLE 학생 ADD 전화번호 VARCHAR(20);

-- 컬럼 수정
ALTER TABLE 학생 MODIFY 이름 VARCHAR(30);

-- 컬럼 삭제
ALTER TABLE 학생 DROP COLUMN 전화번호;
```

### DROP (삭제)
```sql
-- 테이블 삭제
DROP TABLE 학생;

-- 인덱스 삭제
DROP INDEX idx_name;
```

### TRUNCATE (데이터 전체 삭제)
```sql
-- 테이블 구조는 유지, 데이터만 전체 삭제
TRUNCATE TABLE 학생;
```

## 📌 DML (Data Manipulation Language) - 데이터 조작어

### SELECT (조회)
```sql
-- 기본 조회
SELECT * FROM 학생;
SELECT 학번, 이름 FROM 학생;

-- 조건 조회
SELECT * FROM 학생 WHERE 학년 = 1;
SELECT * FROM 학생 WHERE 이름 LIKE '김%';

-- 정렬
SELECT * FROM 학생 ORDER BY 학번 ASC;
SELECT * FROM 학생 ORDER BY 학년 DESC, 이름 ASC;

-- DISTINCT (중복 제거)
SELECT DISTINCT 학과 FROM 학생;
```

### INSERT (삽입)
```sql
-- 전체 컬럼 삽입
INSERT INTO 학생 VALUES ('2024001', '홍길동', '컴퓨터공학', 1);

-- 특정 컬럼만 삽입
INSERT INTO 학생(학번, 이름) VALUES ('2024002', '김철수');

-- 여러 행 삽입
INSERT INTO 학생 VALUES
    ('2024003', '이영희', '전자공학', 2),
    ('2024004', '박민수', '기계공학', 1);
```

### UPDATE (수정)
```sql
-- 전체 수정
UPDATE 학생 SET 학년 = 2;

-- 조건부 수정
UPDATE 학생 SET 학년 = 2 WHERE 학번 = '2024001';

-- 여러 컬럼 수정
UPDATE 학생 SET 학년 = 3, 학과 = '컴퓨터공학' WHERE 학번 = '2024001';
```

### DELETE (삭제)
```sql
-- 전체 삭제
DELETE FROM 학생;

-- 조건부 삭제
DELETE FROM 학생 WHERE 학년 = 1;
```

## 📌 DCL (Data Control Language) - 데이터 제어어

### GRANT (권한 부여)
```sql
-- SELECT 권한 부여
GRANT SELECT ON 학생 TO 사용자1;

-- 모든 권한 부여
GRANT ALL ON 학생 TO 사용자1;

-- WITH GRANT OPTION (권한 재부여 가능)
GRANT SELECT ON 학생 TO 사용자1 WITH GRANT OPTION;
```

### REVOKE (권한 취소)
```sql
-- SELECT 권한 취소
REVOKE SELECT ON 학생 FROM 사용자1;

-- 모든 권한 취소
REVOKE ALL ON 학생 FROM 사용자1;
```

## 📌 TCL (Transaction Control Language) - 트랜잭션 제어어

### COMMIT (확정)
```sql
BEGIN TRANSACTION;
UPDATE 학생 SET 학년 = 2 WHERE 학번 = '2024001';
COMMIT;  -- 변경사항 확정
```

### ROLLBACK (취소)
```sql
BEGIN TRANSACTION;
DELETE FROM 학생 WHERE 학년 = 1;
ROLLBACK;  -- 변경사항 취소
```

### SAVEPOINT (저장점)
```sql
BEGIN TRANSACTION;
UPDATE 학생 SET 학년 = 2;
SAVEPOINT sp1;
DELETE FROM 학생 WHERE 학번 = '2024001';
ROLLBACK TO sp1;  -- sp1 지점으로 복구
COMMIT;
```

## 📌 집계 함수

### 기본 집계 함수
```sql
-- COUNT (개수)
SELECT COUNT(*) FROM 학생;
SELECT COUNT(DISTINCT 학과) FROM 학생;

-- SUM (합계)
SELECT SUM(학년) FROM 학생;

-- AVG (평균)
SELECT AVG(학년) FROM 학생;

-- MAX (최대값)
SELECT MAX(학년) FROM 학생;

-- MIN (최소값)
SELECT MIN(학년) FROM 학생;
```

### GROUP BY (그룹화)
```sql
-- 학과별 학생 수
SELECT 학과, COUNT(*) AS 학생수
FROM 학생
GROUP BY 학과;

-- 학년별 평균 (조건: 학생 수 2명 이상)
SELECT 학년, AVG(학점) AS 평균학점
FROM 학생
GROUP BY 학년
HAVING COUNT(*) >= 2;
```

## 📌 JOIN (조인)

### INNER JOIN (내부 조인)
```sql
-- 명시적 INNER JOIN
SELECT 학생.이름, 수강.과목명
FROM 학생 INNER JOIN 수강
ON 학생.학번 = 수강.학번;

-- 암시적 INNER JOIN
SELECT 학생.이름, 수강.과목명
FROM 학생, 수강
WHERE 학생.학번 = 수강.학번;
```

### OUTER JOIN (외부 조인)
```sql
-- LEFT OUTER JOIN
SELECT 학생.이름, 수강.과목명
FROM 학생 LEFT OUTER JOIN 수강
ON 학생.학번 = 수강.학번;

-- RIGHT OUTER JOIN
SELECT 학생.이름, 수강.과목명
FROM 학생 RIGHT OUTER JOIN 수강
ON 학생.학번 = 수강.학번;

-- FULL OUTER JOIN
SELECT 학생.이름, 수강.과목명
FROM 학생 FULL OUTER JOIN 수강
ON 학생.학번 = 수강.학번;
```

### SELF JOIN (자체 조인)
```sql
-- 같은 테이블을 조인
SELECT A.이름 AS 학생, B.이름 AS 멘토
FROM 학생 A, 학생 B
WHERE A.멘토번호 = B.학번;
```

## 📌 서브쿼리 (Subquery)

### 단일 행 서브쿼리
```sql
-- = , >, <, >=, <=, != 사용
SELECT 이름
FROM 학생
WHERE 학년 = (SELECT MAX(학년) FROM 학생);
```

### 다중 행 서브쿼리
```sql
-- IN
SELECT 이름
FROM 학생
WHERE 학과 IN (SELECT 학과 FROM 학과 WHERE 캠퍼스 = '서울');

-- ANY (하나라도 만족)
SELECT 이름
FROM 학생
WHERE 학년 > ANY (SELECT 학년 FROM 학생 WHERE 학과 = '컴퓨터공학');

-- ALL (모두 만족)
SELECT 이름
FROM 학생
WHERE 학년 > ALL (SELECT 학년 FROM 학생 WHERE 학과 = '컴퓨터공학');

-- EXISTS (존재 여부)
SELECT 이름
FROM 학생 A
WHERE EXISTS (SELECT * FROM 수강 WHERE 학번 = A.학번);
```

## 📌 WHERE 조건

### 비교 연산자
```sql
SELECT * FROM 학생 WHERE 학년 = 1;
SELECT * FROM 학생 WHERE 학년 >= 2;
SELECT * FROM 학생 WHERE 학년 != 4;
```

### 논리 연산자
```sql
-- AND
SELECT * FROM 학생 WHERE 학년 = 1 AND 학과 = '컴퓨터공학';

-- OR
SELECT * FROM 학생 WHERE 학년 = 1 OR 학년 = 2;

-- NOT
SELECT * FROM 학생 WHERE NOT 학과 = '컴퓨터공학';
```

### 패턴 매칭 (LIKE)
```sql
-- % : 0개 이상의 문자
SELECT * FROM 학생 WHERE 이름 LIKE '김%';  -- 김으로 시작
SELECT * FROM 학생 WHERE 이름 LIKE '%수';  -- 수로 끝남
SELECT * FROM 학생 WHERE 이름 LIKE '%철%'; -- 철 포함

-- _ : 정확히 1개 문자
SELECT * FROM 학생 WHERE 이름 LIKE '김_수'; -- 김X수
```

### 범위 (BETWEEN)
```sql
SELECT * FROM 학생 WHERE 학년 BETWEEN 1 AND 3;
```

### 집합 (IN)
```sql
SELECT * FROM 학생 WHERE 학과 IN ('컴퓨터공학', '전자공학', '기계공학');
```

### NULL 체크
```sql
SELECT * FROM 학생 WHERE 학과 IS NULL;
SELECT * FROM 학생 WHERE 학과 IS NOT NULL;
```

## ⚠️ 시험 주의사항

1. **세미콜론(;)** 반드시 마지막에 붙이기
2. **키워드 철자** 정확히 (SELECT, FROM, WHERE 등)
3. **별칭** 사용 시 AS는 생략 가능
4. **따옴표** 문자열은 작은따옴표(' ')
5. **대소문자** SQL 키워드는 대문자 권장
