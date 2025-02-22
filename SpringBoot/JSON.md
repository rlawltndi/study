### JSON (JavaScript Object Notation)
- JavaScript 객체 문법으로 구조화된 데이터를 표현하기 위한 문자 기반의 표준 포멧이다.
- 데이터를 저장하고 전송하는데 사용되는 경량의 데이터 교환 형식, 사람과 기계 모두 읽고 쓰기 편하게 설계되었다.
- 주로 웹에서 클라이언트와 서버 간의 데이터 교환 형식으로 많이 사용한다.
#
### 특징
1. 텍스트 기반 
  - 텍스트로 구성되어 있어 사림이 읽기 쉽다.
  - 데이터를 네트워크를 통해 전송하거나 파일 형태로 저장하는데 적합하다.

2. 언어 독립적
  - 특정 프로그래밍 언어에 종속되지 않는다.
  - 대부분의 프로그래밍 언어에서 JSON을 쉽게 파싱하거나 생성할 수 있는 라이브러리를 제공한다.

3. {"키" : "값"} 쌍
  - JSON 데이터는 {"키" : "값"} 한 쌍의 구조로 이루어져있다.
  - 각 키는 문자열로 나타내고 값은 다양한 자료형(문자열, 숫자, 배열, 객체 등)을 나타낸다.

4. 데이터 구조 표현
  - JSON은 객체,배열,숫자,문자열,true,false,null 과 같은 자료형을 표현할 수 있어
    복잡한 데이터 구조를 직관적으로 표현할 수 있다.
#
### 기본 구조
- 객체(Object)
```
{ "name" : "JISU" ,
  "gender" : "Male" ,
  "age" : 28  }
```
- 중괄호 {} 로 감싸고 , 여러개의 키:값 을 ( , )을 사용해 포함 할 수 있다.
#
### 장점
1. 경량
- 데이터의 표현이 간결해서 네트워크를 통해 데이터를 효율적으로 전송할 수 있다.
2. 호환성
- 대부분의 프로그래밍 언어에서 JSON을 지원하여 데이터를 쉽게 파싱하고 생성 할 수 있다.
3. 가독성
- 사람이 읽고 쓰기 쉽게 설계되었으면 디버깅과 유지보수에 유리한 점이 있다.
#



