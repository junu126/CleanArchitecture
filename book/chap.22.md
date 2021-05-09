# Chap.22 클린 아키텍처

수 십년간 여러 시스템 아키텍처가 나타났다. 모두 세부적인 면에서는 다소 차이가 있었지만, 그 내용은 상당히 비슷했다. 모두의 목표는 `관심사의 분리 (separation of concerms)`이다.

이들은 모두 소프트웨어를 계층으로 분리 함으로써 관심사의 분리 라는 목표를 달성할 수 있었다.

[**https://junukim-dev-1.gitbook.io/clean-architecture/the\_clean\_architecture**](https://junukim-dev-1.gitbook.io/clean-architecture/the_clean_architecture)

**\(Clean Architecture에 대한 정리 글.\)**

## 의존성 규칙

* 소스 코드 의존성은 반드시 안쪽으로, 고수준의 정책을 향해야 한다.
* 내부로 향할 수록 바깥에 속한 어떠한 것도 알 수 없다.
* 같은 맥락으로 외부의 데이터를 내부에서 사용할 수도 없다.

## 엔티티

* 전사적인 핵심 업무 규칙을 캡슐화 한다.
* 엔티티는 메서드를 가지는 객체이거나 일련의 데이터 구조와 함수의 집합일 수도 있다.
* 형태는 중요하지 않다.
* 가장 고수준의 규칙을 캡슐화한다.
* 외부에서 어떠한 영향도 받으면 안된다.

## 유스케이스

* 유스케이스 계층의 소프트웨어는 애플리케이션에 특화된 업무 규칙을 포함한다.
* 또한 시스템의 모든 유스케이스를 캡슐화하고 구현한다.
* 엔티티로 들어오고 나가는 데이터흐름을 조정하며, 엔티티가 자신의 핵심 업무 규칙을 사용해 유스케이스의ㅏ 목적을 달성하도록 이끈다.

## 인터페이스 어댑터

* 일련의 어댑터들로 구성되는 계층이다.
* 어댑터는 데이터를 유스케이스와 엔티티에게 가장 편리한 형식에서 데이터베이스나 웹 같은 외부 에이전시에게 가장 편리한 형식으로 변환한다. \(예를 들면, MVC\(Model, View, Controller 모두 포괄한다.\)
* 데이터를 외부 서비스와 같은 외부적인 형식에서 유스케이스나 엔티티에서 사용되는 내부적인 형식으로 변환하는 또 다른 어댑터가 필요.

## 프레임워크와 드라이버

* 가장 바깥 계층은 일반적으로 DB나 웹 프레임워크 같은 프레임워크나 도구로 구성된다.
* 안쪽과 통신하기 위한 접합 코드 외에는 특별히 작성할 코드가 많지 않다.

## 원은 네 개여야만 하나?

* 클린아키텍처에서 항상 4개의 원만 사용할 필요는 없다.
* 하지만 어떠한 경우에도 의존성 규칙은 적용된다. → 항상 안쪽을 향하며 점점 추상화와 정책의 수준이 높아짐.

## 경계 횡단하기

* 컨트롤러와 프레젠터가 다음 계층에 속한 유스케이스와 통신한다.
* 제어 흐름과 의존성의 방향이 명백히 반대여야 하는 경우 의존성 역전 원칙을 사용해 해결한다.

## 경계를 횡단하는 데이터는 어떤 모습인가

* 경계를 가로지르는 데이터는 흔히 간단한 데이터 구조로 이루어진다.
* 기본적인 구조체나 인터페이스 등으로 구현되며 함수 호출로도 구현한다.
* 데이터 구조 또한 의존성을 갖고 규칙을 위배하지 않는다.
* 경계를 가로질러 데이터를 전달할 때, 데이터는 항상 내부의 원에서 사용하기에 가장 편리한 형태를 띄어야한다.

## 결론

소프트웨어를 계층으로 분리하고 의존성 규칙을 준수한다면 본질적으로 테스트하기 쉬운 시스템을 만들 수 있다.

그리고 DB나 프레임워크 등도 야단스럽지 않게 교체할 수 있게된다.
