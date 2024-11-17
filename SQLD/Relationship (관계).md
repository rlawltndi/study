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
![image](https://github.com/user-attachments/assets/1e669ade-ca06-42f5-8198-fe9fca92229b)
#
### 관계차수의 종류
- 1:1 (일대일 관계)
- M:N (다대다 관계)
- 1:N (일대다 관계)
- 필수 : 선택

![image](https://github.com/user-attachments/assets/f8aa7a86-9fee-4128-8004-13b77a48dd7d)
#
### 1:1 (일대일 관계)
- 하나의 엔터티는 하나의 다른 엔터티 값을 갖는다.
![image](https://github.com/user-attachments/assets/40b7cbce-5c30-40d9-a66d-77bf355f0c16)

### M:N (다대다 관계)
- 두개의 엔터티가 서로 여려 개의 관계를 갖는다.
![image](https://github.com/user-attachments/assets/2dc11208-8265-4d24-91af-2c832fb5185b)

### 1:N (일대다 관계)
- 하나의 엔터티는 다른 엔터티의 값을 여러개 갖는다.
![image](https://github.com/user-attachments/assets/5d473b88-2220-4af7-accd-229a792b9399)

### 필수적 관계
- 하나의 엔터티는 반드시 관계된 엔터티의 값을 가져야한다.
![image](https://github.com/user-attachments/assets/3f817506-374c-49dd-a51f-4bb0cdb6926a)

### 선택적 관계
- 하나의 엔터티에 관계된 다른 엔터티의 값의 유무를 선택 할 수 있다.
![image](https://github.com/user-attachments/assets/3dab8af3-10ab-4a84-8124-a9ce1a648642)

### 

