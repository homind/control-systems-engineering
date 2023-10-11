![image](https://github.com/homind/control-systems-engineering/assets/101074052/7c221db7-2dc4-4738-91e8-8cbb8001c0e1)강의 리뷰
state variable model

state라는 개념을 사용하여 state space equation을 만듬

이를 통해, 시스템 내부의 수식에서 의미있는 추적 관찰가능

다차원의 미분방정식을 1차원의 행렬 미분방정식으로 바뀌면서 수식이 단순해지는 장점이 있음

그래서 상태변수를 만들어 상태 공간 방정식을 정의하자.

상태변수가 어떻게 정해지는가?? 마음대로 설정해도 되는가????
-> 여러가지 상태 변수들을 정해도 같은 시스템을 설명할 수 있지만, 패턴(방향)이 존재하고, 행렬방정식을 좀 더 쉽게 풀기 위해서는 이러한 상태변수를 잡는 것이 유리하다 라는 툴??이있음.

이러한 방법이 phsase variable canonical form임.
우리가 지금부터 배운 방식으로 상태 공간 방정식을 만들게 되면 일정한 형태를 가진 행렬이 만들어지게 되는데, 이 행렬로 수식이 설명되면 phsase variable canonical form 라함.

이를 쓰면, 2가지 장점. 무조건 풀리고, 쉬움.

상태공강방정식을 만들떄 시스템에서 바로만드는 것이 아니 먼저 전달함수를 구하고 상태공간방정식을 구한다. ( 예외상황을 발생하지 않게하기 위해)
(라플라스 변환을 통해 식을 쉽게만듬)
전달함수를 구해서 분모든 분자든 s의 방정식으로만듬 (모든 4차시스템은 분모는 4차식, 분자는 3차식으로만들수 있음)
![image](https://github.com/homind/control-systems-engineering/assets/101074052/cd04ae94-e3e0-4217-87dd-4c04355be4ac)

이걸 이제 상태공간방정식으로 변경해야함.
z(s)들을 곱해졌다고 가정 why? 상태변수를 일관적으로 설정하기위한 밑작업
곱하고나서 Y(S) =~~~, U(S) =~~~로 설정
이 두식에 역라플라스를 행함. 이떄 Z(s)를 곱한 이유가 나오게 됨. Z(S)를 곱하지 않으면 역라플라스시 t에 대하여등식이 설정되니 이를 막기위해 z(t)로 설정한것
z(t) 가 상태 변수가 되는것.

 ![image](https://github.com/homind/control-systems-engineering/assets/101074052/042ce13d-216f-45df-a76f-00341fffb07b)

4차 미분이 상태변수들로부터 수식이 유도됨
![image](https://github.com/homind/control-systems-engineering/assets/101074052/59a76754-ebc8-433a-830a-d0d3743bee55)

시스템 -> 전달함수 ->  phsase variable canonical form -> 상태공간 방정식

tf2ss - > matlab함수임 두 벡터를 입력으로 넣음.
![image](https://github.com/homind/control-systems-engineering/assets/101074052/b21837b2-fd4c-4ba9-a7aa-7699b79344f7)

뒤집혀짐

![image](https://github.com/homind/control-systems-engineering/assets/101074052/803f2c59-9093-49a1-9c39-b201e302e434)

결과값
