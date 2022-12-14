
# 2장. 
 중요한 것은 엘리스가 그 어떤 음식을 먹어도 ‘엘리스’라는 사실이 변하지 않는다는 것이다.

## 객체

### 상태

예외를 찾을 때 정상 거래와 비정상 거래를 비교하며 어떤 메서드를 마지막 호출로 비교했는지 보고, 파라미터 등 상태값을 확인하게 된다.

### 행동
상태가 변경되는 이유는 행동을 취해서이다.

* 사이드 이펙트: 객체의 행동에 의해 또 다른 객체의 상태가 변경되는 것
  예 ) 엘리스가 케이크를 먹음으로서 자신의 키도 작아지며, 케이크의 양(상태)도 줄어드는 것

- 객체 자신의 상태 변경

- 행동 내에서 협력하는 객체에 대한 메시지 전송

### 식별자
  식별자란, 어떤 객체가 다른 객체와 구분하는 데 사용하는 객체의 프로퍼티이다.

모든 객체는 식별자를 가지며, 식별자를 이용해 객체를 구별할 수 있다.

    값 → 식별자를 가지지 않음(보통, 값의 상태는 변하지 않기 때문에 ‘불변상태(Immutable)’ 하다. → 값 객체(value object)
    
    객체 → 식별자를 가짐 → 참조 객체(reference object), 엔티티(entity)


### 동등성(equality)

상태를 이용해 두 값이 같은지 판단.
(상태를 이용해 동등성을 판단할 수 있는 이유→ 값의 상태가 변하지 않기 때문)

***객체***는 시간에 따라 변경되는 상태를 포함하며, 행동을 통해 상태를 변경한다.
따라서, 가변 상태(mutable) 를 가진다.

### 동일성(identical)

식별자를 기반으로 객체가 같은지 판단

### 기계로서의 객체

객체가 외부에 제공하는 행동은 쿼리(query)와 명령(command)으로 구성된다.

- 쿼리(query): 객체의 상태를 조회하는 작업
- 명령(command): 객체의 상태를 변경하는 작업


객체는 다른 객체의 상태에 직접적으로 접근할 수도, 상태를 변경할 수도 없다. 스스로 자신의 상태를 책임져야 한다.
→ 간접적으로 객체의 상태를 변경하거나 조회할 수 있는 방법이 ***행동(메서드)***이다.


### 행동이 상태를 결정한다.

1. 상태를 먼저 결정할 경우 캡슐화가 저해된다.
2. 객체를 협력자가 아닌 고립된 섬으로 만든다.
3. 객체의 재사용성이 저하된다.

객체는 다른 객체와 협력하기 위해 존재한다.
객체의 행동은 객체가 협력에 참여하는 유일한 방법이다.

객체지향 설계는 애플리케이션에 필요한 협력을 생각하고, 협력에 필요한 행동을 생각한 후 행동을 수행할 객체를 선택한다.
따라서, 객체의 행동(책임)을 결정하고, 그 후에 행동에 적절한 상태를 선택하게 된다.

### 책임주도설계(Responsibility-Driven Design)