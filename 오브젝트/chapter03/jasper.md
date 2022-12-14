# 역할, 책임, 협력

- 애플리케이션의 기능을 구현하기 위해 어떤 협력이 필요하고 협력을 위해 어떤 역할과 책임이 필요한지를 고민하지 않은 채 너무 이른 시기에 구현에 초점을 맞추는 것은 변경하기 어렵고 유연하지 못한 코드를 낳는 원인이 됨

- 객체지향에서 가장 중요한 것은 역할, 책임, 협력이다

## 협력

- 객체들이 애플리케이션의 기능을 구현하기 위해 수행하는 상호작용 -> 협력

- 객체가 협력에 참여하기 위해 수행하는 로직 -> 책임

- 객체들이 협력 안에서 수행하는 책임들이 모여 객체가 수행하는 역할을 구성

### 협력

- 객체는 고립된 존재가 아니라 시스템의 기능이라는 더 큰 목표를 달성하기 위해 다른 객체와 협력하는 사회적인 존재

- 두 객체 사이의 협력은 하나의 객체가 다른 객체에게 도움을 요청할 때 시작됨

- 메시지 전송(message sending)은 객체 사이의 협력을 위해 사용할 수 있는 유일한 커뮤니케이션 수단

- 객체는 다른 객체의 상세한 내부 구현에 직접 접근할 수 없기 때문에 오직 메시지 전송을 통해서만 자신의 요청을 전달

- 자율적인 객체란 자신의 상태를 직접 관리하고 스스로의 결정에 따라 행동하는 객체

- 객체의 자율성을 보장하기 위해서는 필요한 정보와 정보에 기반한 행동을 같은 객체 안에 모아놓아야 함

- 캡슐화를 통해 변경에 대한 파급효과를 제한할 수 있기 때문에 자율적인 객체는 변경하기도 쉬워짐

- 자율적인 객체는 자신에게 할당된 책임을 수행하던 중에 필요한 정보를 알지 못하거나 외부의 도움이 필요한 경우 적절한 객체에게 메시지를 전송해서 협력을 요청

### 협력이 설계를 위한 문맥을 결정한다

- 협력은 객체가 필요한 이유와 객체가 수행하는 행동의 동기를 제공

- 협력이라는 문맥을 고려하지 않고 객체의 행동을 결정하는 것은 아무런 의미가 없다

- 협력이 존재하기 때문에 객체가 존재하는 것

- 상태는 객체가 행동하는 데 필요한 정보에 의해 결정되고 행동은 협력 안에서 객체가 처리할 메시지로 결정됨

- 결과적으로 객체가 참여하는 협력이 객체를 구성하는 행동과 상태 모두를 결정

- 협력은 객체를 설계하는 데 필요한 일종의 문맥(context)을 제공

## 책임

### 책임이란 무엇인가

- 협력에 참여하기 위해 객체가 수행하는 행동을 책임이라고 부름

- 책임이란 객체에 의해 정의되는 응집도 있는 행위의 집합으로, 객체가 유지해야 하는 정보와 수행할 수 있는 행동에 대해 개략적으로 서술한 문장

- 협력 안에서 객체에게 할당한 책임이 외부의 인터페이스와 내부의 속성을 결정함

- 객체지향 설계에서 가장 중요한 것은 책임이다

- 객체에게 얼마나 적절한 책임을 할당하느냐가 설계의 전체적인 품질을 결정

### 책임 할당

- 자율적인 객체를 만드는 가장 기본적인 방법은 책임을 수행하는 데 필요한 정보를 가장 잘 알고 있는 전문가에게 그 책임을 할당 하는 것 -> Information Expert(정보 전문가) 패턴

- 객체에게 책임을 할당하기 위해서는 먼저 협력이라는 문맥을 정의

- 협력을 설계하는 출발점은 시스템이 사용자에게 제공하는 기능을 시스템이 담당할 하나의 책임으로 바라보는 것

- 객체지향 설계는 시스템의 책임을 완료하는 데 필요한 더 작은 책임을 찾아내고 이를 객체들에게 할당하는 반복적인 과정을 통해 모양을 갖춰감

- 객체지향 설계는 협력에 필요한 메시지를 찾고 메시지에 적절한 객체를 선택하는 반복적인 과정을 통해 이뤄진다
그리고 이런 메시지가 메시지를 수신할 객체의 책임을 결정한다

- 이렇게 결정된 메시지가 객체의 퍼블릭 인터페이스를 구성

- 협력을 설계하면서 객체의 책임을 식별해 나가는 과정에서 최종적으로 얻게 되는 결과물은 시스템을 구성하는 객체들의 인터페이스와 오퍼레이션의 목록

### 책임 주도 설계 

- 책임을 찾고 책임을 수행할 적절한 객체를 찾아 책임을 할당하는 방식으로 협력을 설계하는 방법을 책임 주도 설계(Responsibility-Driven Design, RDD)라고 부른다

1. 시스템이 사용자에게 제공해야 하는 기능인 시스템 책임을 파악한다

2. 시스템 책임을 더 작은 책임으로 분할한다

3. 분할된 책임을 수행할 수 있는 적절한 객체 또는 역할을 찾아 책임을 할당한다

4. 객체가 책임을 수행하는 도중 다른 객체의 도움이 필요한 경우 이를 책임질 적절한 객체 또는 역할을 찾는다

5. 해당 객체 또는 역할에게 책임을 할당함으로써 두 객체가 협력하게 한다

- 구현이 아닌 책임에 집중하는 것이 중요한 이유는 유연하고 견고한 객체지향 시스템을 위해 가장 중요한 재료가 바로 책임이기 때문이다

- 책임을 할당할 때 고려해야 하는 두 가지 요소

    - 매시지가 객체를 결정

    - 행동이 상태를 결정

### 메시지가 객체를 결정한다

- 객체가 메시지를 선택하는 것이 아니라 메시지가 객체를 선택하게 함

- 메시지가 객체를 선택하게 해야 하는 두 가지 중요한 이유

    - 객체가 최소한의 인터페이스(minimal interface)를 가질 수 있게 된다, 필요한 메시지가 식별될 때까지 객체의 퍼블릭 인터페이스에 어떤 것도 추가하지 않기 때문에 객체는 애플리케이션에 크지도, 작지도 않은 꼭 필요한 크기의 퍼블릭 인터페이스를 가질 수 있다
    
    - 객체는 충분히 추상적인 인터페이스(abstract interface)를 가질 수 있게 된다, 객체의 인터페이스는 무엇(what)을 하는지 표현해야 하지만 어떻게(how) 수행하는지를 노출해서는 안된다. 메시지는 외부의 객체가 요청하는 무언가를 의미하기 때문에 메시지를 먼저 식별하면 무엇을 수행할지에 초점을 맞추는 인터페이스를 얻을 수 있다

### 행동이 상태를 결정한다

- 객체가 존재하는 이유는 협력에 참여하기 위해 -> 객체는 협력에 필요한 행동을 제공해야 함

- 객체를 객체답게 만드는 것은 객체의 상태가 아니라 객체가 다른 객체에게 제공하는 행동

- 객체의 행동은 객체가 협력에 참여할 수 있는 유일한 방법

- 객체가 협력에 적합한지를 결정하는 것은 그 객체의 상태가 아니라 행동

- 개별 객체의 상태와 행동이 아닌 시스템의 기능을 구현하기 위한 협력에 초점을 맞춰야만 응집도가 높고 결합도가 낮은 객체들을 창조할 수 있다

## 역할

### 역할과 협력

- 객체는 협력이라는 주어진 문맥 안에서 특정한 목적을 갖게 됨

- 객체가 어떤 특정한 협력 안에서 수행하는 책임의 집합을 역할이라고 부른다

- 실제로 협력을 모델링할 때는 특정한 객체가 아니라 역할에게 책임을 할당한다고 생각하는 게 좋다

### 유연하고 재사용 가능한 협력

- 역할이 중요한 이유는 역할을 통해 유연하고 재사용 가능한 협력을 얻을 수 있기 때문

- 동일한 책임을 수행하는 역할을 기반으로 두 개의 협력을 하나로 통합 -> 불필요한 중복 코드 제거, 유연한 협력

- 책임과 역할을 중심으로 협력을 바라보는 것이 바로 변경과 확장이 용이한 유연한 설계로 나아가는 첫걸음

- 역할을 구현하는 가장 일반적인 방법은 추상 클래스와 인터페이스를 사용하는 것

- 협력의 관점에서 추상 클래스와 인터페이스는 구체 클래스들이 따라야 하는 책임의 집합을 서술한 것

### 객체 대 역할

- 협력에 참여하는 후보가 여러 종류의 객체에 의해 수행될 필요가 있다면 그 후보는 역할이 되지만 단지 한 종류의 객체만이 협력에 참여할 필요가 있다면 후보는 객체가 됨

- 설계 초반에는 적절한 책임과 협력의 큰 그림을 탐색하는 것이 가장 중요한 목표여야 하고 역할과 객체를 명확하게 구분하는 것은 그렇게 중요하지 않다는 것

- 따라서 애매하다면 단순하게 객체로 시작하고 반복적으로 책임과 협력을 정제해가면서 필요한 순간에 객체로부터 역할을 분리해내는 것이 가장 좋은 방법

- 다양한 객체들이 협력에 참여한다는 것이 확실하다면 역할로 시작

- 하지만 모든 것이 안개 속에 둘러싸여 있고 정확한 결정을 내리기 어려운 상황이라면 구체적인 객체로 시작

- 다양한 시나리오를 탐색하고 유사한 협력들을 단순화하고 합치다 보면 자연스럽게 역할이 그 모습을 드러낼 것

### 역할과 추상화

- 세부 사항에 억눌리지 않고도 상위 수준의 정책을 쉽게 간단하게 표현할 수 있다는 것

- 추상화를 적절하게 사용하면 불필요한 세부 사항을 생략하고 핵심적인 개념을 강조할 수 있다

