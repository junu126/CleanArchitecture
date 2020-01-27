# Chap.8 OCP: 개방-폐쇄 원칙

> * 소프트웨어 개체는 확장에는 열려있어야 하고, 변경에는 닫혀 있어야 한다.
> * 소프트웨어 개체의 행위는 확장 가능 → 산출물을 변경 하면 X

## 사고 실험

상황 A와 B가 주어지고 이를 구현에 성공했을때 갑자기 C의 상황이 추가로 들어왔다. 이럴 때 원래 코드를 얼마나 많이 수정해야할까? → 이상적인 변경량 0

### How?

_**단일 책임 원칙과 의존성 역전 원칙을 통해 최소화할 수 있다.**_ 서로 다른 목적으로 변경되는 요소를 적절하게 분리\(SRP\)하고 이들 요소사이의 의존성을 체계화\(DIP\)함으로써 변경량을 최소화할 수 있다.

* 아키텍트는 기능이 _**어떻게**_ \| _**왜**_ \| _**언제**_ 발생하는지에 따라서 기능을 분리하고, 분리한 기능을 컴포넌트의 계층 구조로 조직화한다.
* 이와 같은 변경은 저수준 컴포넌트에서 발생한 변경으로부터 고수준 컴포넌트를 보호할 수 있다.

## 방향성 제어

* 컴포넌트 간 의존성의 방향을 확실히 해야한다.
*     의 순서로 은닉된다. \(Interactor가 최고 은닉\)

## 정보 은닉

* **추이 종속성**: 추이 종속성을 갖게 되면 소프트웨어 엔티티는 '자신이 직접 사용하지 않는 요소에는 절대로 의존해서는 안 된다.'는 소프트웨어 원칙을 위반하게 된다.
* 클래스 A가 B에 의존하고, 다시 클래스 B가 C에 의존한다면 클래스 A는 클래스 C에 의존한다. → 이러한 현상을 추이 종속성이라고 한다.

## 결과

OCP는 시스템의 아키텍처를 떠받치는 원동력 중 하나이다.

* 시스템을 확장하기 쉬운 동시에 변경으로 인해 시스템이 너무 많은 영향을 받지 않도록 하는데 OCP의 목표가 있다.
* 목표 달성을 위해 시스템을 컴포넌트 단위로 분리한다.
* 목표 달성을 위해 저수준 컴포넌트에서 발생한 변경으로부터 고수준 컴포넌트를 보호할 수 있는 형태의 의존성 계층 구조가 만들어지도록 해야 한다.
