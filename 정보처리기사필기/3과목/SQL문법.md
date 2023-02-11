# SQL 문법

## DDL(Data Define Launguage)

스키마, 태이블, 뷰를 정의하거나 삭제할 때 사용하는 언어

### CREATE

```SQL
CREATE TABLE 테이블 명
```

- PRIMARY KEY : 기본키로 사용할 속성
- UNIQUE : 대체키로 사용할 속성, 중복된 값ㅇ르 가질 수 없음

### ALTER

```SQL
ALTER TABLE 테이블명
```

- ADD : 새로운 속성(열)
- ALTER : 특성 속성의 DEFAULT 값을 변경할 때 사용
- DROP COLUMN : 특정 속성을 삭제할 때 사용

### DROP

스키마, 도메인, 기본 테이블, 뷰테이블, 인덱스, 제약 조건들을 제거하는 명령문

- CASCADE : 제거할 요소를 참조하는 다른 모든 개체를 함께 제거함
- RESTRICT : 다른 개체가 제거할 요소를 참조중일 때는 제거를 취소함

## DML(Data Maimpulation Language)

데이터를 처리하는데 사용하는 언어

### INSERT

```SQL
INSERT INTO 테이블명([속성명1,,]) VALUES (데이터)
```

### DELETE

```SQL
DELETE FROM 테이블명 [WHERE 조건]
```

### UPDATE

```SQL
UPDATE 테이블명 SET 속성명 = 데이터 [WHERE  조건]
```

### SELECT

```SQL
SELECT [PREDICATE][테이블명.]속성명[AS 별칭][그룹함수] FROM 테이블명 [WHERE] [GROUP BY] [HAVING] [ORDER BY]
```

#### 그룹 함수

- COUNT(속성명)
- SUM(속성명)
- AVG(속성명)
- MAX(속성명)
- MIM(속성명)
- STDDEV(속성명) : 그룹 별 표준 편자
- VARIANCE(속성명) : 그룹별 분산

#### PREDICATE : 불러올 튜플 수를 제한

- ALL : 모든 튜플 검색, 생략 가능
- DISTINCT : 중복된 튜플이 있으면 그 중 첫번째 1개만 검색
- DISTINCTROW : 중복된 튜플을 제거하고 한 개만 검색하지만 선택된 속성을 제외하고 전체 튜플을 가져옴

#### 연산자

- = : 같다
- <> : 같지 않다
- <, >, >=, <=

#### LIKE 연산자

- % : 모든 문자를 대표함
- \_ : 문자 하나
- `#` : 숫자 하나

#### 집합 연산자

```SQL
SELECT FROM UNION|UNION ALL|INTERSECT|EXCEPT FROM SELECT FROM
```

- UNION : 합집합 출력, 중복된 행은 한번만
- UNION ALL : 중복된 행도 그대로
- INTERSECT : 공통된 행만
- EXCEPT : 첫번째 SELECT 조회 결과에서 두번째 SELECT문의 조회 결과를 제외한 결과

## DCL(Data Countrol Language)

데이터의 보안, 무결성, 회복, 병행 수행 제어등을 정의하는데 사용, DB 관리자가 데이터 관리를 목적으로 사용

### GRANT

DB 관리자가 DB 사용자에게 권한을 부여하기 위한 명령어

```SQL
GRANT 권한 ON 개체 TO 사용자 [WITH GRANT OPTION];
```

- WITH GRANT OPTION : 부여받은 권한을 다른 사용자에게도 부여할 수 있는 권한

### REVOKE

권한 취소를 위한 명령어

```SQL
REVOKE [GRANT OPTION FOR] 권한 ON 개체 FROM 사용자 [CASCADE];
```

- GRANT OPTION FOR : 다른 사용자에게 권한을부여할 수 있는 권한을 취소
- CASCADE : 권한 췻 시 권한을부여바당ㅆ던 사용자가 다른 사용자에게 부여한 권한도 연쇄적으로 취소

### COMMIT

트랙잭션이 성공적으로 끝나면 DB가 새로운 일간성 상태를 가지기 위해 변경된 모든내용을 DB에 반영할 때 사용하는 명령어

### ROLBACK

아직 COMMIT 되지 않은 변경딘 모든 내용들을 취소하고 DB를 이전 상태로 되돌리는 명령어
