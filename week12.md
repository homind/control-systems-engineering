피드백의 성능 part 2

trasient 성능 - pole의 위치!가 중요함 > 이를 위한 방정식-> 특성방정식!

steady -state의 성능 : system의 type 분석

----

![image](https://github.com/homind/control-systems-engineering/assets/101074052/0d2d84b7-2d72-4eeb-93ac-ef9a90ebc3e8)

transient performace를 결정하는 요소가 무엇인가????
외란, 노이즈는 0이고 피드백 게인은 1이라고 가정한 상태에 진행함.
![image](https://github.com/homind/control-systems-engineering/assets/101074052/21867cdb-06f5-4de1-85cd-750e1de2d1d5)

전체 전달함수의 분모가 0이 되는 식이 특성방정식이며

이 특성방정식이 0이 되는 s값(극점)을 찾으면 실수해가 나오거나 혹은 복소수해가 나오는데 실수해가 나온다면 그 시스템의 출력은
완전한 지수함수적 특성을 갖고 복소수해라면 지수함수적특성이 포함된 sin 특성을 갖는 것.

다음과 같음

![image](https://github.com/homind/control-systems-engineering/assets/101074052/4cd10bc1-9890-4ef0-adbd-dfa2a5749871)


dominant가 무엇인가???? -> 오른쪽의 pole일 수록 영향이 크다는 것. 

-----

steady - state performance

![image](https://github.com/homind/control-systems-engineering/assets/101074052/5d6398b4-a94c-4683-9c71-afa804f45f3d)


최종값 정리를 하였을때

![image](https://github.com/homind/control-systems-engineering/assets/101074052/4f9be133-fabc-4326-9523-5f71a7e22f19)

이러한 결과가 나옴

![image](https://github.com/homind/control-systems-engineering/assets/101074052/9d70af7b-45e2-4750-895b-be627f3cd0fb)









---------------
실습
![image](https://github.com/homind/control-systems-engineering/assets/101074052/8dc74942-c32a-4c96-ab75-1b6d11e24839)
p는 에러가 비례한다는 뜻. i는 1/s로 적분을 하여 에러를 컨트롤로 보낸 다는듰. d는 미분의 뜻.
i제어는 transient response를 좋게하는 역할은 아님, 에러를 줄이는역할?
d제어가 transient response를 좋게함, 


![image](https://github.com/homind/control-systems-engineering/assets/101074052/9742d696-89f1-4ed6-9962-e4d474f47610)


 








 












