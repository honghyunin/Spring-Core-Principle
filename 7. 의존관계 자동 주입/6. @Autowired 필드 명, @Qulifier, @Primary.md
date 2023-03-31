# @Autowired 필드 명, @Qulifier, @Primary

### @Autowired 필드 명 매칭

`@Autowired` 는 타입 매칭을 시도하고, 이때 여러 빈이 있으면 필드 이름, 파라미터 이름으로 빈 이름을 추가 매칭한다.

**기존 코드**

```java
@Autowired
private DiscountPolicy discountPolicy
```

**필드 명을 빈 이름으로 변경**

```java
@Autowired
private DiscountPolicy rateDiscountPolicy
```

필드 명이 `rateDiscountPolicy` 이므로 `RateDiscountPolicy` 클래스 타입이 정상 주입된다.

필드 명 매칭은 먼저 타입 매칭을 시도 하고 그 결과에 여러 빈이 있을 때 추가로 동작하는 기능이다.

### 빈 등록 시 @Qualifier를 붙여준다

```java
@Component
@Qualifier("mainDiscountPolicy")
public class RateDiscountPolicy implements DiscountPolicy {}
```

주입 시에 `@Qulifier` 사용

**생성자 자동 주입 예시**

```java
@Autowired
public OrderServiceImpl(MemberRepository memberRepository,
 @Qualifier("mainDiscountPolicy") DiscountPolicy 
discountPolicy) {
 this.memberRepository = memberRepository;
 this.discountPolicy = discountPolicy;
}
```

### @Qualifier 정리

`@Qualifier` 는 추가 구분자를 붙여주는 방법이다. 주입 시 추가적인 방법을 제공하지만 빈 이름을 변경하진 않는다.

- `@Qualifier` 끼리 매칭
- 빈 이름 매칭
- `NoSuchBeanDefinitionException` 예외 발생

```java
@Component
@Qualifier("mainDiscountPolicy")
public class RateDiscountPolicy implements DiscountPolicy {}
```

주입 시에 `@Qualifier` 를 붙여주고 등록한 이름을 적어준다.

**생성자 자동 주입 예시**

```java
@Autowired
public OrderServiceImpl(MemberRepository memberRepository,
 @Qualifier("mainDiscountPolicy") DiscountPolicy 
discountPolicy) {
	 this.memberRepository = memberRepository;
	 this.discountPolicy = discountPolicy;
}
```

### @Primary 사용

`@Primary` 는 우선순위를 정하는 방법이다.

`rateDiscountPolicy` 가 우선권을 가지도록 하자.

```java
@Component
@Primary
public class RateDiscountPolicy implements DiscountPolicy {}
@Component
public class FixDiscountPolicy implements DiscountPolicy {}
```

위 코드에서 DiscountPolicy 빈 등록 시 `@Primary` 가 달린 RateDiscountPolicy가 지정된다.

### @Primary, @Qualifier 활용

코드에서 자주 사용하는 메인 DB의 커넥션을 획득하는 스프링 빈과 코드에서 특별한 기능으로 가끔 사용하는 서브 DB 커넥션으 획득하는 스프링 빈이  있을 경우 메인 DB의 커넥션을 `@Primary` 를 적용해서 조회하는 곳에 `@Qualifier` 지정 없이 편리하게 조회하고, 서브 DB 커넥션 빈을 획득할 때는 `@Qualifier` 를 지정해서 명시적으로 획득하는 방식으로 사용하여 코드를 깔끔하게 유지할 수 있다.

### 우선순위

`@Primary` 는 기본값처럼 동작하는 것이고, `@Qualifier` 는 매우 상세하게 작동한다. 이런 경우 어떤 것이 우선권을 가져갈까? 스프링은 자동보다는 수동이, 넓은 범위의 선택권 보다는 좁은 범위의 선택권이 우선순위가 높다. 따라서 여기서도 `@Qualifier`가 우선권이 높다.