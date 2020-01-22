# Chap.3 패러다임 개요

세 가지 패러다임을 설명한다.

* 구조적 프로그래밍
* 객체지향 프로그래밍
* 함수형 프로그래밍

## 구조적 프로그래밍

최초로 적용된 패러다임 \(최초로 만들어진건 아님.\)으로 1968년 _**에츠허르 비버 데이크스트라**_가 발견했다.

무분별한 점프\(goto\)가 프로그램 구조에 해롭다는 사실을 제시하고 이를 `if / then / else`와 `do / while / until`등으로 익숙한 구조로 대체했다.

이를 요약하면..

> 구조적 프로그래밍은 제어 흐름의 직접적인 전환에 대해 규칙을 부과한다.

## 객체 지향 프로그래밍

두 번째로 도입된 패러다임으로 1966년에 _**요한 달**_과 _**크리스텐 니가드**_에 의해 등장했다.

이들은 **알골언어**의 함수 호출 스택 프레임을 _**힙**_으로 옮기면, 함수 호출이 반환된 이후에도 함수에서 선언된 지역 변수가 오랫동안 유지될 수 있음을 발견했다.

→ 함수 = **클래스의 생성자**

→ 지역변수 = **인스턴스 변수**

→ 중첩 함수 = **메서드**

그리고 이를 통해 필연적으로 **다형성**이 등장했다.

이를 요약하면..

> 객체 지향 프로그래밍은 제어흐름의 간접적인 전환에 대해 규칙을 부과한다.

## 함수형 프로그래밍

세 번째 패러다임은 최근에 도입되기 시작했다. 하지만 가장 첫 번째로 만들어 졌다.

함수형 프로그래밍은 _**알론조 처치**_와 _**앨런 튜링**_이 똑같이 흥미를 가졌던 어떤 수학적 문제를 해결하는 과정에서 **람다 계산법**을 발명했는데, 여기서 직접적인 영향을 받아 만들어지게 된다.

1958년에 _**존 매카시**_가 만든 **LISP언어**의 근간이 되는 개념이 바로 이 **람다 계산법** 이다.

* 불변성 \(심볼의 값이 변경되지 않는다는 개념\)

이를 요약하면..

> 함수형 프로그래밍은 할당문에 대해 규칙을 부과한다

## 결론

우리는 아키택처 경계를 넘나들기 위한 메커니즘으로 다형성을 이용한다.

우리는 함수형 프로그래밍을 이용하여 데이터의 위치와 접근 방법에 대해 규칙을 부과한다.

우리는 모듈의 기반 알고리즘으로 구조적 프로그래밍을 사용한다.

**세 가지 패러다임과 아키택처의 세 가지 큰 관심사\(함수, 컴포넌트 분리, 데이터 관리\)**가 어떻게 서로 **연관**되는지에 주목.
