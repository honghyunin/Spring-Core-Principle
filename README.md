# 🍃 Spring-Core-Principle
김영한의 스프링 핵심 원리 기본편을 학습한 내용을 정리하는 레포지토리입니다.

## 객체지향 설계와 스프링 | Chapter 1

스프링이란?

좋은 객체 지향 프로그래밍이란?

좋은 객체 지향 설계의 5가지 원칙(SOLID)

객체 지향 설계와 스프링

## 객체 지향 원리 적용 | Chapter 2

프로젝트 생성

비즈니스 요구사항과 설계

회원 도메인 설계

회원 도메인 개발

회원 도메인 실행과 테스트

주문과 할인 도메인 설계

주문과 할인 도메인 실행과 테스트

## 객체 지향 원리 적용 | Chapter 3

새로운 할인 정책 개발

새로운 할인 정책 적용과 문제점

관심사의 분리

AppConfig 리팩터링

새로운 구조와 할인 정책 적용

전체 흐름 정리

좋은 객체 지향 설계의 5가지 원칙의 적용

IoC, DI, 그리고 컨테이너

스프링으로 전환하기

## 스프링 컨테이너와 스프링 빈 | Chapter 4

스프링 컨테이너 생성

컨테이너에 등록된 모든 빈 조회

스프링 빈 조회 - 기본

스프링 빈 조회 - 동일한 타입이 둘 이상

스프링 빈 조회 - 상속 관계

BeanFactory와 ApplicationContext

다양한 설정 형식 지원 - 자바 코드, XML

스프링 빈 설정 메타 정보 - BeanDefinition

## 싱글톤 컨테이너 | Chapter 5

웹 어플리케이션과 싱글톤

싱글톤 패턴

싱글톤 컨테이너

싱글톤 방식의 주의점

@Configuration과 싱글톤

@Configuration과 바이트코드 조작의 마법

## 컴포넌트 스캔 | Chapter 6

컴포넌트 스캔과 의존관계 자동 주입 시작하기

탐색 위치와 기본 스캔 대상

필터

중복 등록과 충돌

## 의존관계 자동 주입 | Chapter 7

[다양한 의존관계 주입 방법](https://github.com/honghyunin/Spring-Core-Principle/blob/main/Chapter_7/%EB%8B%A4%EC%96%91%ED%95%9C_%EC%9D%98%EC%A1%B4%EA%B4%80%EA%B3%84_%EC%A3%BC%EC%9E%85_%EB%B0%A9%EB%B2%95.md)

[옵션 처리](https://github.com/honghyunin/Spring-Core-Principle/blob/main/Chapter_7/%EC%98%B5%EC%85%98_%EC%B2%98%EB%A6%AC.md)

[생성자 주입을 선택해라!](https://github.com/honghyunin/Spring-Core-Principle/blob/main/Chapter_7/%EC%83%9D%EC%84%B1%EC%9E%90_%EC%A3%BC%EC%9E%85%EC%9D%84_%EC%84%A0%ED%83%9D%ED%95%98%EB%9D%BC!.md)

롬복과 최신 트렌드

[조회 빈이 2개 이상 - 문제](https://github.com/honghyunin/Spring-Core-Principle/blob/main/Chapter_7/%ec%a1%b0%ed%9a%8c_%eb%b9%88%ec%9d%b4_2%ea%b0%9c_%ec%9d%b4%ec%83%81-%eb%ac%b8%ec%a0%9c.md)

@Autowired 필드 명, @Qualifier, @Primary

애노테이션 직접 만들기

조회한 빈이 모두 필요할 때, List, Map

자동, 수동의 올바른 실무 운영 기준

## 빈 생명주기 콜백 | Chapter 8

빈 생명주기 콜백 시작

인터페이스 InitializingBean, DisposableBean

빈 등록 초기화, 소멸 메서드

애노테이션 @PostConstruct, @PreDstroy

## 빈 스코프란 | Chapter 9

빈 스코프란?

프로토타입 스코프

프로토타입 스코프 - 싱글톤 빈과 함께 사용시 문제점

프로토타입 스코프 - 싱글톤 빈과 함께 사용 시 Provider로 문제 해결

웹 스코프

request 스코프 예제 만들기

스코프와 Provider

스코프와 프록시