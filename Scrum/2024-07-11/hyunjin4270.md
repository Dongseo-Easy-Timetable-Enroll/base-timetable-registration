#### 작성 : hyunjin4270
**작성 날짜 : 2024-07-10**

---

### 어제까지 무엇을 했는가?
- 김영한의 스프링 기본 복습
    - 객체지향 5원칙
        - 단일 책임 원칙(Single Responsibility Principle)
            - 클래스는 개념 하나에만 책임을 담당해야 한다
        - 개방 폐쇄 원칙 (Open-Close Principle)
            - 클래스의 확장에선 열려 있어야 하고, 변경에는 폐쇄적이여야 한다
        - 리스코프 치환 원칙 (Liskov's Substitution Principle)
            - 자식 클래스가 부모 클래스의 행동을 완전히 대체할 수 있어야 한다
        - 인터페이스 분리 원칙 (Interface Segregation Principle)
            - 클라이언트는 사용하지 않는 메서드에 대해 의존적이지 않아야 된다
        - 의존성 역전 원칙(Dependency Inversion Principle)
            - 상위 모듈이 하위 모듈에 직접 의존하는 것이 아니라, 둘 다 추상화에 의존하도록 설계를 해야한다
    <br>
    - 빈
        - 빈은 스프링 프레임워크에서 관리되는 객체다
        - 빈을 사용하는 이유는 객체의 의존관계를 관리를 해준다. 이는 객체의 서로간의 결합이 느슨해져 코드의 유연성이 증가한다.
        ```java
         @Bean
        public MemberService memberService() {
        return new MemberServiceImpl(memberRepository());
        }
        ```
        <br>
    - 스프링 컨테이너
        - 빈을 관리하는 저장소 역할이다.
        - ApplicationContext(인터페이스)를 이용하여 빈을 관리하고, AnnotationConfigApplicationContext(class), GenericXmlApplicationContext(Xml)을 이용하여 상세한 관리가 가능하다.
        ```java
         AnnotationConfigApplicationContext ac = new AnnotationConfigApplicationContext(TestConfig.class);
        ```
    <br>
    - 싱글 톤 (빈 스코프)
        - 디자인 패턴중 하나로, 특정 클래스의 인스턴스가 오직 하나만 생성되고, 이 인스턴스에 대한 전역 접근을 제공한다.
        - 전역적 접근성이라는 장점으로 인해 서버의 트래픽을 쉽게 관리하게 해준다.
        - 하지만 인스턴스 하나로 관리되기 때문에 여러 사용자들의 상태를 하나로만 관리하여 지금 프로젝트에는 어울리지 않는다.
    <br>
    - 의존성 자동 주입, 컴포넌트 스캔
        - @Bean을 이용해서 수동적으로 스프링 컨테이너에 넣는 방법도 있지만, @ComponentScan을 이용해 자동적으로 스프링 컨테이너에 넣고, @Autowired를 이용해 자동으로 의존성 주입이 가능하다.
        - 이렇다해서 수동 빈 등록을 아예 안사용하는건 아니다. 기술적인 문제나 공통 관심사(AOP)를 처리할 때 주로 사용된다.
        
        ```java
        @Configuration
        @ComponentScan(
            // basePackages = "hello.core.member", // 이렇게 하면 member 패키지만 스캔
            excludeFilters = @ComponentScan.Filter(type = FilterType.       ANNOTATION, classes = Configuration.class)
        )
        public class AutoAppConfig {

        }
        @Autowired
        public MemberServiceImpl(MemberRepository memberRepository) {
            this.memberRepository = memberRepository;
        }
    <br>
    - 빈의 생명주기
        - 빈은 의존관계를 주입하고, 초기화 콜백이 일어나고, 사용이 가능한 순서기 때문에 객체의 생성과 초기화를 분리시켜 단계적으로 만들어 지는 것을 뚜렷하게 만들 필요가 있다.
        - @PostConstruct 애노테이션을 이용해서 의존성 주입이 완료된 후에 초기화 작업을 수행하고, @Predestroy 애노테이션을 이용해서 빈이 소멸되기 전에 정리를 해줄 수 있다.

### 오늘 무엇을 계획하고 있는가?
- Figma
- 프론트엔드
    

### 어떤 문제점이 있거나 도움이 필요한 것이 있는가?
- 없음