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

### INSERT INTO

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
