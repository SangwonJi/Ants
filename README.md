# 🐜 개미 대 꿀벌 🐝 타워 디펜스 게임 프로젝트
(Ants Vs. SomeBees)

## 프로젝트 개요
이 프로젝트에서는 객체지향 프로그래밍을 이용하여 '개미 대 꿀벌 (Ants Vs. SomeBees)'이라는 타워 디펜스 게임을 개발했습니다.

각각의 개체(여러 종류의 개미와 꿀벌)는 독립된 클래스로 설계되어 있으며,

이 개체들이 어떻게 상호 작용하고 게임의 동적 환경 속에서 어떻게 움직이는 지를 중점적으로 다뤘습니다. 

플레이어는 여왕개미가 되어 꿀벌의 공격으로부터 개미집을 방어하고, 이 과정에서 다양한 유형의 개미를 전략적으로 배치하여 방어 매커니즘을 강화하는 방식으로 게임이 플레이 됩니다. 

## 사용된 언어 및 기술
- Python
- 객체지향 프로그래밍 (Object-oriented programming (OOP))

## 핵심 기능 및 구현 요소
- **Place 클래스**:
  - 게임의 각 위치를 나타내며, 개미나 꿀벌을 저장할 수 있는 클래스. 
  - 각 위치는 출구(exit)와 입구(entrance)를 갖고 있어 다른 위치와 연결됨.

- **Insect 클래스**:
  - 모든 곤충(개미와 꿀벌)의 기본 클래스로, 건강 상태와 위치를 관리.

- **Ant 클래스**:
  - 다양한 유형의 개미를 구현하는 클래스. 각 개미는 고유한 행동을 가지며, 게임 상태에 영향을 미침
  - `HarvesterAnt`(음식을 수집)와 `ThrowerAnt`(잎사귀를 던져 꿀벌을 공격) 등이 포함됨.

- **Bee 클래스**:
  - 꿀벌은 개미집으로 진입하려고 시도하며, 개미를 공격하거나 위치를 이동할 수 있음.

- **게임 상태 관리**:
  - 게임의 진행 상황을 관리하고, 각 턴에서 곤충의 행동을 조정.

## 결
- 객체지향 원칙을 활용하여 복잡한 게임 로직을 체계적으로 구현.
- 클래스 상속과 다형성을 사용하여 코드의 재사용성과 확장성을 높였음.
- GUI를 통해 사용자 상호작용을 구현하여 직관적인 게임 경험을 제공.

## 예제 코드

```python
class Place:
    def __init__(self, name, exit=None):
        self.name = name
        self.exit = exit
        self.entrance = None
        self.ant = None
        self.bee = None

class Ant(Insect):
    def __init__(self, health, position):
        super().__init__(health, position)
        self.damage = 0

    def action(self, gamestate):
        # Implement specific actions for each ant type
        pass

class Bee(Insect):
    def __init__(self, health, position):
        super().__init__(health, position)

    def move_to(self, place):
        if place.is_empty():
            self.position = place

    def action(self, gamestate):
        if self.position.ant:
            self.attack(self.position.ant
``` 
