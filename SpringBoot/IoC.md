### IOC(Inversion of Control) : 제어의 역전
- IoC는 사용할 객체를 직접 생성하지 않고 , 객체의 생명주기 관리를 프레임 워크나 스프링 컨테이너에 위임하는 것이다.
- 애플리케이션의 유연성과 유지보수성을 높일 수 있다. 
#
### IoC 개념
1. 의존성 주입 (DI:Dependency Injection)
- 객체가 스스로 의존성을 관리하는 것이 아닌 외부에서 필요한 의존성을 주입받는 방식
- 필드, 생성자, 세터 메서드를 통해 의존성을 주입할 수 있다. (가장 일반적인 사용 방법)

2. 제어의 역전
- 전통적인 방법은 개발자가 객체를 직접 생성하고 관리하지만, IoC에서는 스프링 프레임워크와 같은 
  컨테이너가 객체간의 의존성을 주입하고 관리한다.
- 프레임워크가 객체의 생명주기를 관리한다.

3. 스프링 IoC컨테이너
- 스프링에서 IoC는 ApplicationContext 또는 BeanFactory라는 IoC 컨테이너를 통해 구현되고 
  애플리케이션에서 필요한 객체(Bean)를 생성하고 필요한 의존성을 주입해준다.
- 컨테이너는 XML,Java 어노테이션, Java 설정 클래스를 통해 설정된 객체(Bean)의 정의를 보고 생성,관리한다.
#
