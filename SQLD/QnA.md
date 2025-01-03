### 관계형 데이터베이스란?
- 관계형 데이터베이스는 데이터를 테이블 형식으로 저장하고 관리하는 데이터베이스 시스템이다.
- 각 테이블은 행(레코드)과 열(필드)로 구성되며 , SQL을 사용하여 데이터를 조직하고 쿼리(Query명령어를 사용하는 작업)한다.
- 데이터의 일관성과 무결성이 중요한 경우에 적합하고 , NoSQL은 확장성과 성능이 필요한 경우에 적합하다.

### 관계형 테이터베이스의 테비블 개념을 설명, 행과 열 이란?
- 테이블은 데이터를 저장하는 기본 단위로 행(row)과 열(column)으로 구성되어있다.
- 열 : 데이터의 속성이나 필드를 나타내고 , 각 열은 특정 데이터 유형을 갖는다.
- 행 : 각 속성에 대한 실제 데이터를 담고 있는 개별 레코드를 의미한다.

### 기본 키란?, 관계형 데이터베이스에서 중요한 이유
- 기본 키(Primary Key)는 테이블 내의 각 행의 고유하게 식바하는데 사용되는 하나 이상의 열 이다.
- Null값을 가질 수 없고 중복될 수 없다.
- 데이터의 무결성을 유지하고, 테이블 간의 관계를 설정하는데 필수이다.
- 기본 키를 통해 빠르고 효율적인 데이터 검색이 가능, 외래 키를 통해 다른 테이블과의 연결을 가능하게 한다.

### 외래키란? 
- 한 테이블의 열이 다른 테이블의 기본 키를 참조하는 키 이다.
- 외래키는 테이블 간의 관계를 정의하고 , 데이터의 참조 무결성을 유지하는데 사용된다.

### 데이터베이스에서 제약조건의 목적
- 데이터의 무결성과 일관성을 유지하기 위해 사용되는 규칙이다.
- NOT NULL : 열에 NULL 값을 허용하지 않는다.
- UNIQUE : 열의 모든 값이 고유해야한다.
- PRIMARY KEY : NOY NULL, UNIQUE 두 속성을 모두 갖는다. 테이블의 기본키로 사용
- FOREIGN KEY : 다른 테이블의 기본키를 참조하여 테이블 간의 관계를 유지한다.
- CHECK : 열의 값이 특정조건을 만족해야한다.
- DEFAULT : 열의 기본값 설정

### SQL이란?
- SQL이란 관계형 데이터베이스를 관리하고 조작하기 위한 표준언어이다.
- DDL (Data Definition Language) : 데이터베이스의 구조를 정의하거나 수정한다. (CREATE, ALTER, DROP)
- DML (Data Manipulation Language) : 데이터베이스의 데이터를 조작한다. (SELECT, INSERT, UPDATE, DELETE)
- DCL (Data Control Language) : 데이터베이스의 접근 권한과 보안을 관리한다. (GRANT,REMOVE)
- TCL (Transaction Control Language) : 트렌젝션의 시작과 종료를 관리한다. (COMMIT, ROLLBACK, SAVEPOINT)

### 정형 데이터와 비정형 데이터의 차이점
- 정형 데이터 (Structured Data) : 고정된 필드에 저장되는 데이터로 , 관계형 데이터베이스의 테이블과 같은 명확한 구조를 갖는다.
                                (스프레드 시트, 데이터베이스 테이블 등)
- 비정형 데이터 (Unstructured Data) : 고정된 구조가 없는 데이터로, 텍스트 파일, 이미지, 동영상 등이 해당
                                     (eamil, 문서 파일 ,멀티미디어 컨텐츠)

### JOIN이란?
- 두개 이상의 테이블을 연결하여 하나의 결과 세트로 만드는 SQL 연산자이다.
- 여러 테이블에 분산되어있는 관련 데이터를 조합하여 원하는 정보를 추출할 수 있다.
- 데이터베이스의 정규화로 인해 나누어진 테이블을 재결합하는데 필수적이다.

### INNER JOIN, LEFT JOIN, RIGHT JOIN ,FULL JOIN이란?
- INNER JOIN : 왼쪽 테이블의 모든 행을 반환하고 , 오른쪽 테이블에서 일치하는 행이있으면 함께 반환
              일치하지 않으면 NULL
- RIGHT JOIN : 오른쪽 테이블의 모든 행을 반환하고 , 왼쪽 테이블에서 일치하는 행이 있으면 함께 반환
              일치하지 않으면 NULL
- FULL JOIN : 두 테이블의 모든 행을 반환 , 일치하지 않는 경우 NULL

### 관계형 데이터베이스에서 다대다 관계를 표현하는 방법
- 중간 테이블 (교차 테이블)을 사용하여 구현한다.
- 이 연결 테이블은 두 테이블의 기본 키를 외래 키로 갖고 , 이 외래 키들의 조합을 키본키로 설정한다.

### 셀프조인의 목적
- 동일한 테이블을 두 개의 별칭으로 나누어 자신과 조인하는 기법이다.
- 테이블 내에서 관련된 데이터를 연결해야 할 때 사용된다.
-  ex) 직원 테이블에서 각 직원들의 상사의 정보를 조회하기 위해서는 직원 테이블을 자신과 조인하여
        직원과 상사의 관계를 나타낼 수 있다.


