### 주요 Spring 어노테이션들은 의존성 주입, 트렌잭션 처리, 웹 관련 등 여러 분야에 결쳐 사용된다.
#

### @Component / @Service / @Repository / @Controller

- @Component : Spring에서 가장 기본적인 Bean 정의 어노테이션이다. Spring 컨테이너가 클레스를 자동으로 감지하고 빈으로 등록할수 있다.
 ```
    @Component
    public class MyComponent{
      //class definition
    }
  ```
#
- @Service : 비즈니스 로직을 처리하는 클레스에 주로 사용된다. @Component와 동일하지만, 서비스 계층을 명확히 나타내기 위해 사용한다.
```
@Service
public class MyService{
  //service logic
}
```
#
- @Repository : 데이터 접근 계층을 나타내는 특수한 어노테이션, 데이터베이스와 상호작용하는 컴포넌트에 사용된다.
```
@Reopsitory
public class MyRepository{
 // 데이터베이스와의 상호작용 코드
 public Product findById(Long id){
 //SQL 쿼리 실행 도는 다른 데이터 접근 로직
  return new Product(); //예시로 Product 객체 반환
 }
}
```
#
- @Controller : Spring MVC에서 사용되는 어노테이션으로, 웹 애플리케이션에서 요청을 처리하는 컨트롤러 클래스를 정의할 때 사용한다. 특정 클래스가 HTTP 요청을 처리하고, 그에 맞는 뷰를 반환하는 역할을 한다는 것을 Spring에 알려준다.

**특징**
1. 웹 요청 처리
 - @controller가 붙은 클래스는 클라이언트의 HTTP 요청을 처리하는 메서드를 가지고 있으며, 해당 메서드는 요청에 맞는 응답을 반환한다.
 - ex) 사용자가 /home 경로로 요청을 보내면, 그 요청을 처리하는 메서드가 실행된다.
2. MVC 패턴 구현
 - Spring MVC(Model - View - Controller)아키텍처에서 Controller 역할을 맡는다.
 - 클라이언트의 요청을 받아서, 적절한 서비스 로직을 호출하고, 그 결과를 View에 전달하는 역할을 한다.
3. 메서드 매핑
 - @RequestMapping, @GetMapping, @PostMapping 등과 함께 사용되어 특정 URL 경로에 대한 HTTP 메서드 (POST, GET)와     해당 메서드를 매핑한다.
4. 뷰 반환
   - ;
   
 
