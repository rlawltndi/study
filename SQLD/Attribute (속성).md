### Attribute(속성)
- 엔터티를 설명하고 인스턴스를 구성하는 요소  
  (인스턴스 : 데이터베이스에 저장된 데이터의 전체 집합)
- 의미상 분리되지 않는 데이터의 최소 단위
```
회원 - 회원ID , PW , Name , Age 등
상품 - 상품번호, 상품명 , 재고 , 가격 등
회사 - 회사번호 , 회사명, 담당자 등
```
#
### 특징
- 업무에서 필요하고 관리하고자 하는 정보여야한다.
- 정규화 이론에 근간하여 정해진 주 식별자에 함수적 종속성을 가진다.
- 하나의 속성에는 한 개의 값만 갖는다.
- 하나의 속성에 여러개의 값이 있는 다중 값일 경우 별도의 엔터티를 이용하여 분리한다.
#
### 엔터티 , 인스턴스 , 속성 , 속성 값의 관계
- 1개의 엔터티는 2개 이상의 인스턴스의 집합
- 1개의 엔터티는 2개 이상의 속성을 갖는다.
- 1개의 속성은 1개의 속성 값을 갖는다.
<img width="568" alt="엔터티 관계도" src="https://github.com/user-attachments/assets/9643e543-652f-4596-956d-c9979ada50db">

#
### 분류
1. 특성에 따른 분류
- 기본 속성
  - 업무로부터 추출한 모든 속성, 가장 일반적이고 많은 속성을 차지한다.      
    ex) 이자, 회원ID, 이름 
- 설계 속성 
  - 데이터 모델링을 위해, 업무를 규칙화하기 위해 새로 만들거나 변형하여 정의하는 속성    
    ex) 상품코드, 지점코드 (코드성 속성)
- 파생 속성
  - 다른 속성에 영향을 받아 발생하는 속서으로, 보통 계산된 값들이 이에 해당된다.
  - 데이터 정합성을 유지하기 위해 파생 속성을 적게 정의하는 것이 좋다.  
  - 계산 방법에 대해서 반드시 정의되어야 한다.    
    ex) 이자율, 합계, 평균

2. 분해 여부에 따른 속성
- 단일 속성
  - 속성의 원자값으로 이루어져 있다, 더 이상 분해 할 수 없는 속성  
  - 하나의 의미로 구성된 속성이다.  
     ex) 주문번호, 고객이름, 제품 가격
- 복합 속성
  - 여러개의 속성이 합쳐져 하나의 속성을 이루는 형태  
  - 분해 될 수 있는 여러개의 의미를 갖는 속성이다.  
     ex) 주소(도시,우편번호 등) , 이름(성,이름) 등
- 다중값 속성
  - 하나의 엔터티가 여러개의 값을 가질 수 있는 속성  
  - 여러개의 동일한 속성 값을 가질 수 있고, 엔터티로 분해 가능  
     ex) 전화번호, email 등
#   
               
     
