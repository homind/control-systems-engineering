
피드백 제어

1. 무엇인가?
먼저 개념이해하자.
open - loop

![image](https://github.com/homind/control-systems-engineering/assets/101074052/57bd0111-3be2-4359-a6af-b22c749ca140)

입력 -> 신호 -> 액츄에이어테의한 동작 - > 결과  : 단방향이라는 점과 입력 후 우리가 할 수 있는 것은 없음

![image](https://github.com/homind/control-systems-engineering/assets/101074052/8ea8c493-f52b-44a6-92c0-1c2278c06147)


액츄에이터는 하드웨어시스템인데, 내가 컨트롤러 설계를 잘 해놔도 외란의 영향에 의해 그렇게 동작 안할 수 도 있음.

![image](https://github.com/homind/control-systems-engineering/assets/101074052/76ad136e-18b4-4d7a-b8ce-89c7d9682027)

오픈루프는 장담 할 수 없다!!

closed- loop

![image](https://github.com/homind/control-systems-engineering/assets/101074052/4b8b7de7-7301-4649-b474-fd9d331489fe)

루프가 다시 돌아와 영향을 주는 것. 언젠가 평형상태에 도달하고 이것이 내가 바란 상태임
언제까지?? (실제 결과값 = 기대했던 결과값) _> 차이가 존재하면 error로 나타나서 다시조정

센서를 통해 동작을 관찰하고 다시 컨트롤러에 정보를 전달해서 다시 제어함. 

![image](https://github.com/homind/control-systems-engineering/assets/101074052/f89ef768-e7b8-46f2-bf31-9eb10a2ddfbc)

해당 센서들

문제점은?

![image](https://github.com/homind/control-systems-engineering/assets/101074052/7b0b394f-2e98-45e8-98a1-3f0f92caddff)

이 센서가 100퍼 동작하냐? -> 아니다, 오차가 발생한다. 그것이 노이즈(N)이라함. 
T를 보상하기위해 센서를 쓰는데 노이즈가 생김 ->  우리는 노이즈와 외란을 없애도록 해야한다.!!!!!

![image](https://github.com/homind/control-systems-engineering/assets/101074052/63943398-4291-42f7-a94e-6cf51b29319b)

위의 블록선도에서 외란과 노이즈의 영향을 알아보자. (라플라스 식으로)

H는 1이라 생각,  

![image](https://github.com/homind/control-systems-engineering/assets/101074052/29f7a0e1-c8f8-431d-a520-395733bee8c5)

출력은 이렇게 됨, 입력에 대해 뒤에 쓸대없는 식 2개가 생김.

흔히 에러는

![image](https://github.com/homind/control-systems-engineering/assets/101074052/eeb51fc1-f249-4aa2-b393-c9051ede3ba0)

와 같이 표현하니 

![image](https://github.com/homind/control-systems-engineering/assets/101074052/9f0ba318-5f0b-4a18-89a1-e0a57ff8638c)

요렇게 나타낼 수 있음.
에러는 우리가 이론적으로 발생하는 에러 앞에, 외란, 노이즈 로생기는 것 3개로 볼 수 있음.

수식 정리를 해보자. 

 ![image](https://github.com/homind/control-systems-engineering/assets/101074052/67b9db65-b962-494f-8ef0-5d53b9a1e3bf)

 
e(sS)식을 보면 앞에 2개는 s의 지배 뒤에는 c의 지배를 받으며  관계를 이해할 수 있다. ~~

![image](https://github.com/homind/control-systems-engineering/assets/101074052/1653e2ff-3537-4c8b-9e0b-66b91c57208e)




-----
 

![image](https://github.com/homind/control-systems-engineering/assets/101074052/3de28cd1-9bc4-429c-8662-c384c759adde)


외란을 최소화하고 싶다. !

바꿀수 있는 건 S(s)를 0으로 만들어야함. 이를 위해선  L(s)를 무한대로 보내야함 ->  이를 위해선 - > $G_c(S)$를 무한대로 보내야함.

노이즈를 최소화하고 싶다.!
C(s)를 영으로 하자. -> L(s)를 영으로 만들자! -> $G_c(S)$가 작아야한다.

![image](https://github.com/homind/control-systems-engineering/assets/101074052/64005323-6f76-49ba-a016-9be6adc35fc0)

하지만!
![image](https://github.com/homind/control-systems-engineering/assets/101074052/97d213ad-642d-4676-bd9e-ef06394ce099)

로 인해서 둘 다 컨트롤하기 힘듬.
(나중에  어떤 주파수에서 조절하면 노이즈, 외란 어떻게 하면 어느정도 효과적으로 줄일 수 있음.)

----
내부 에러

plant 인 G(s)가 예쌍대로 움직이지 않아 발생 하는 것 어떤 미세한

![image](https://github.com/homind/control-systems-engineering/assets/101074052/d5a4b44c-3181-4b8e-bbdf-2a820dce2183)

델타 값에 의해 발생한다고 생각 해보자 이떄 이 값은 매우 작음(노이즈와 외란은 영이라고 생각해서 이런 식이 나온 것인데 ! 델타 G(s)가 생겼다 ~)이걸 internal variation이라 한다???


그래서

![image](https://github.com/homind/control-systems-engineering/assets/101074052/1102f08b-6883-4dc4-94ac-0c26b108872f)

에러값도 변화가 생기고 

 그 변화 값만 알아보기위해 식을 정리하면, 

![image](https://github.com/homind/control-systems-engineering/assets/101074052/7f40a427-6897-4209-8a1c-a68478c195b9)

와 같이됨.

이식에서 델타가 매우작다고했으니 없애버리자 그러면, 근사화 할 수 있는데 (분모만! 그렇게 생각하자)

![image](https://github.com/homind/control-systems-engineering/assets/101074052/d80764f0-d3bd-4db4-be07-d0d12a1155bd)
       
이 식을 보면 델타 G(s)가 있을때 델타 외란을 줄이고 싶으면 루프게인L(s)를 줄이면 된다.~~~~~~

----
예제를 보면

![image](https://github.com/homind/control-systems-engineering/assets/101074052/4086f2da-6974-4632-96c7-b02bd7ce8fe9)



![image](https://github.com/homind/control-systems-engineering/assets/101074052/e023354c-bdad-432c-b89e-e2bacbf0bffb)

T(s)는 전달함수 게인, Ka는 메인 플랜트의 게인함수 를 비로 나타낸게 S(s)  -> 민감도임.


폐회로는

![image](https://github.com/homind/control-systems-engineering/assets/101074052/ea6f593f-9726-4061-8d70-72d975aa14ef)
![image](https://github.com/homind/control-systems-engineering/assets/101074052/31b9be1c-1d4c-48c2-abbc-c63108a125b4)

을 해석하면

![image](https://github.com/homind/control-systems-engineering/assets/101074052/eccbe197-e8da-4955-93ce-15b28cbf3d13)

처럼됨, 

![image](https://github.com/homind/control-systems-engineering/assets/101074052/f45cff5d-5be3-4a67-8f22-edf4152e5aa1)

이라는데 공부하자. 먼말인지 모르겠다.

















