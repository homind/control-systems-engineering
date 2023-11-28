피드백의 성능
1. 제어 초기의 성능 (응답이 빠른가? -> 신속성)
2. 제어의 steady-state 성능( 나의 지령에 얼마나 정확하게 도달하는가, 어떻게 수렴하는가? - > 정확성)

----
![image](https://github.com/homind/control-systems-engineering/assets/101074052/9b1b6067-d98f-4388-b4a1-4ccf0e268616)

transient 연관 
peak : 얼마나 높이 올라가는지?? 
risetime : 올라가는 속도

steady-state 연관 
final, settlingtime(짧아야 좋음)

risetime에서 빨리올라가면 내가 원하는 지점을 지나가는 경우가 있음 -> 정확성과 신속성은 같이 공존하기 힘든 것.

![image](https://github.com/homind/control-systems-engineering/assets/101074052/1e72ce2d-5aae-4548-994a-aec0589a889c)

파라미터가 변하면 신속성은 감소하고 정확성은 증가하는 추세의 그래프로 원하는 점으로 제어의 성능을 정해야함.


---

![image](https://github.com/homind/control-systems-engineering/assets/101074052/b3d2af08-ab50-42dc-978b-f481ab2291cd)
시스템 자체의 잠재적인 능력을 확인하기 위해서 임펄스 입력을 넣어주면 된다.

이외의 다양한 입력(step, ramp, parabolic)

![image](https://github.com/homind/control-systems-engineering/assets/101074052/ca4aef77-7710-47c8-9292-0d4bd28c9770)


------

2차 시스템을 가정해보자. 이떄 gain은 1!
![image](https://github.com/homind/control-systems-engineering/assets/101074052/fd844b6c-e769-4912-bc71-df1d5eb5d983)

위의 식에서 전달함수를 통해 출력을 구하고 역라플라스를 취하면 다음과 같다.

![image](https://github.com/homind/control-systems-engineering/assets/101074052/e0ecdf85-3113-4530-b67a-71989c2b0771)

이 식에서 고유진동수가 일정하다고 하였을때 제타가 크면 진동은 작은데 그 peak?? 늦게올라가고
제타가 작다면 진동의 영향이 크게 일어나면서 ( sin함수의 영향이 큰것) peak가? 높다? 크게 올라갈 것.

![image](https://github.com/homind/control-systems-engineering/assets/101074052/49652314-b5e1-469b-a96b-50eaa667ff8a)


진동을 억제하는 선에서 괜찮은 결과를 얻고 싶으면 제타를 1로 설정함. 이 1이 critical damping임


----

성능 지표

![image](https://github.com/homind/control-systems-engineering/assets/101074052/698f65ba-1605-4825-a174-055d776ac2f2)

risetime : 우리내린 성능의 기준값의 10%부터 90%에 도달하는 시간. or 그냥 90%에 도달하는 시간.

10%부터 시작하는 경우는 why?? -> 시정수가 커서 늦게 매우 늦게 도달하는 경우를 고려해서 



peak time : over shoot 되었을때 얼마나 빨리증가되었는지의 지표이면서 정확도에서 얼마나 넘어섰는지를 말함. 

settling time : 최종지령값에 오차2%로 도달하는 순간 (보통 2%임)

해당 2차 시스템에서는

![image](https://github.com/homind/control-systems-engineering/assets/101074052/e98a297e-7031-4321-b1bf-c48dbfa6f396)
와 같이 계산이 된다.

즉 2차 시스템에서는 제어기를 설계할 때, 제타 혹은 고유진동수와 관련됨. 
오버슈트를 설정하면 ->  제타를 설정할 수 있음 -> 고유진동수를 결정할 수 있음 -> 나머지시간들(스펙, 성능)이 결정됨.


2차시스템에서도

![image](https://github.com/homind/control-systems-engineering/assets/101074052/a4e3caee-5f37-4ae2-8fcb-47262fb9834a)

제타 값에 따른 그래프가 존재


고유진동수가 증가하면 진동이크고 빠르게 수렴 작으면 진동은 작은데 주기가 길어지면서 수렴


------


![image](https://github.com/homind/control-systems-engineering/assets/101074052/9f182d84-1dbc-4a5e-a8ae-30734356d852)



극점: 분모가 0
영점 : 분자가 0

이러한 점을 알고

![image](https://github.com/homind/control-systems-engineering/assets/101074052/a56da473-5851-401c-8f6d-7e98a22bf28e)

극점이 멀리 떨어져있으면 무시가능함 가까이있으면 영향이 큼

극점이 늘어나면 진동이 억제되고 라이즈타임이 증가되는 경향이 있음. 

영점이 증가되면 진동이 커지고 라이즈타임이 짧아지고 
영점이 작아지면  
마찬가지로, 기존의 영점에비해 추가된 영점이 멀리 존재할 경우 그것은 영향이 작아서 무시할 수 있고 이를 통해서 3차를 2차로 근사화 할 수 잇음.


---










