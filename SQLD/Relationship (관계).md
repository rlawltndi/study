### 관계 (Relationship)
- 엔터티간 논리적인 연관성을 의미한다.
- 엔터티의 정의에 따라 영향을 받을 수 있다.
- 속성 정의 및 관계 정의에 따라서 다양하게 변할 수 있다.
#
### 관계의 분류
- 존재에 의한 관계  
  ex) 사원 김지수는 부서 A팀에 소속되어있다.(존재)
- 행위에 의한 관계  
  ex) 김지수 고객은 A제품을 구매한다.(행위)
#
### 관계의 표기법
- 관계명
  - 관계에 엔터티가 참여하는 형태를 정의
  - 각 두개의 관계명을 갖는다.
  - 관계명은 능동적 또는 수동적으로 명명된다.
  - 추상적인 동사를 피하고 현재형으로 표기한다.
#
### 관계의 기수성
- 기수성 : 집합의 크기를 나타내는 개념
- 관계의 기수성 : 관계에 참여하는 엔터티 인스턴스의 수를 나타내는 것
#
### ERD 표기방식
> ![식관계의 패어링 erd표기방식](https://private-user-images.githubusercontent.com/177000859/386408067-28900601-824a-4446-a3b4-a88b65509e10.png?jwt=eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJpc3MiOiJnaXRodWIuY29tIiwiYXVkIjoicmF3LmdpdGh1YnVzZXJjb250ZW50LmNvbSIsImtleSI6ImtleTUiLCJleHAiOjE3MzE2Mjk2NjUsIm5iZiI6MTczMTYyOTM2NSwicGF0aCI6Ii8xNzcwMDA4NTkvMzg2NDA4MDY3LTI4OTAwNjAxLTgyNGEtNDQ0Ni1hM2I0LWE4OGI2NTUwOWUxMC5wbmc_WC1BbXotQWxnb3JpdGhtPUFXUzQtSE1BQy1TSEEyNTYmWC1BbXotQ3JlZGVudGlhbD1BS0lBVkNPRFlMU0E1M1BRSzRaQSUyRjIwMjQxMTE1JTJGdXMtZWFzdC0xJTJGczMlMkZhd3M0X3JlcXVlc3QmWC1BbXotRGF0ZT0yMDI0MTExNVQwMDA5MjVaJlgtQW16LUV4cGlyZXM9MzAwJlgtQW16LVNpZ25hdHVyZT01N2ExZDAzMDRkYmFlNmEwNGVhZDYzNTQ0ZDkzMDQyMTVhMmQzMWFiYjdjNTViYmYzMmQ5NzVmN2EwOTk0ODUyJlgtQW16LVNpZ25lZEhlYWRlcnM9aG9zdCJ9.FLe6szvLO8EXc6vfYFZ97NOg8fsdniT5KqOvfC4vF-I)
#
### 관계차수
- 두 테이블 간의 관계가 몇개의 요소를 연결하는지를 나타낸다. 주로 관계형 데이터 베이스에서
  다양한 관계의 종류를 설명하는데 사용된다.
#
### 관계차수의 종류
1. 1:1 관계 (One-to-One Relationship)
- 한 테이블의 한 행이 다른 테이블의 한 행과 연결된다.
- 관계차수 : 1
```
CREATE TABLE students (
    student_id INT PRIMARY KEY, -- student_id를 기본 키로 설정하여 각 학생을 고유하게 식별 가능
    name VARCHAR(100) -- 학생의 이름 저장
);

CREATE TABLE student_details (
    student_id INT,  -- 외래 키로 사용 할 student_id
    address VARCHAR(255), -- 주소
    phone_number VARCHAR(50), -- 전화번호 
    PRIMARY KEY (student_id),  -- student_id를 기본 키로 설정
    FOREIGN KEY (student_id) REFERENCES students(student_id)  -- 외래 키
);
```
- student 테이블은 학생의 기본정보를 ,student_details 테이블은 해당 학생의 상세정보를 저장한다.
- student_details 테이블은 student 테이블의 student_id를 외래키로 사용하여 두 테이블을 연결한다.
- student_details 테이블의 각 레코드는 반드시 student 테이블의 한 학생과 연결된다.
- 두 테이블을 연결함으로써 student 테이블의 학생정보가 변경되거나 삭제되면 해당 학생의 student_details의
  정보다 함께 수정되거나 삭제될 수 있도록 관계가 설정되어있다.

