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

- @Service : 비즈니스 로직을 처리하는 클레스에 주로 사용된다. @Component와 동일하지만, 서비스 계층을 명확히 나타내기 위해 사용한다.
```
@Service
public class MyService{
  //service logic
}
```
