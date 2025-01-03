### 무결성
- 데이터 정확성, 일관성 및 유효성을 보장하기 위한 규칙 또는 제약 조건
#
### 무결성의 종류
|종류|설명|
|---|---|
|개체 무결성(Entity Integrity)|기본키는 NULL이 아니며, 모든 레코드에 대해 고유해야 한다.|
|참조 무결성(Referntail Integrity)|외래키는 참조하는 테이블의 기본키 값을 가지거나 NULL이어야 한다.|
|도메인 무결성(Domain Integrity)|각 속성은 허용된 도메인 내에서만 값을 가져야 한다.|
|사용자 정의 무결성(User-Defined Integrity)|특정 비즈니스 규칙이나 요구 사항에 맞추어 데이터 무결성을 정의하는 것|
#
### 기본 키(Primary Key) 제약조건
- 테이블 내에서 각 레코드를 고유하게 식별하는 필드 또는 필드 조합이다.
- 기본 키는 NULL 값을 허용하지 않고 중복 값도 허용하지 않는다.

### 외래 키(Forein Key) 제약조건
- 다른 테이블의 기본 키를 참조하는 필드이다.
- 외래 키를 사용하여 테이블 간의 관계를 정의하고, 참조 무결성을 보장한다.
#
### 무결성 제약조건 
- SQL에서 테이블을 생성하거나 수정할 때 데이터의 유효성을 검사하는 규칙을 설정할 수 있다.

1. NOT NULL : 특정 열에 NULL 값을 허용하지 않는다.
2. UNIQUE : 특정 열에 중복된 값이 없도록 보장한다.
3. CHECK : 특정 열의 값이 주어진 조건을 만족하는지 확인한다.
4. DEFAULT : 특정 열의 기본값을 설정한다.
5. FOREIGN KEY : 다른 테이블과의 관계를 정의하고, 참조 무결성을 유지한다.
#
```SQL
-- entity 무결성 : PRIMARY KEY 사용
CREATE TABLE 학생 (
  student_id INT PRIMARY KEY,
  name VARCHAR(50),
  age INT
)

-- 참조 무결성 : FOREIGN KEY 사용
CREATE TABLE 주문 (
  order_id INT PRIMARY KEY,
  customer_id INT,
  order_date DATE,
  FOREIGN KEY(customer_id) REFERENCES 고객(customer_id)
)

-- 도메인 무결성 : CHECK 사용
CREATE TABLE 제품(
    product_id INT PRIMARY KEY,
    product_name VARCHAR(100),
    price DECIMAL(10, 2),
    CONSTRAINT price_check CHECK (price > 0)
)
```
