안정성

![image](https://github.com/homind/control-systems-engineering/assets/101074052/98c253ab-b59c-4992-af09-67478a22d9bc)

불안정 : 제 위치로 돌아오지 않거나, 어디로 가는지 모르는 발산하는 상태

안정 : 입력이 들어와도 제 위치로 돌아올 수 있는 상태 (절대적인 안정은 없음 -> 가정이 존재 -> 

bounded in bounded out: 안정된 상태를 넘겨버리는 입력은 들어오지 않으며, 그 출력이 내가 정한 값안에만 속한다면 안정하다고 하는 가정으로 BIBO Stability라고 함.)

중립 : 안정, 불안정도 아닌 상태

------

수식으로 bibo stability 이해하기

 ![image](https://github.com/homind/control-systems-engineering/assets/101074052/768b49cb-ef1b-446c-a73a-53d9ad49a615)


개어렵게 보이지만 결론으로 bibo stability은 극점의 위치가 왼쪽 평면에 존재하면 안정! 


그렇다면 극점이 모두 왼쪽에 있는가!!!를 알아보기 위해서는 루스안정도로 판단함.
 
   
매트랩에서 해보기 루스안정도

루스 어레이

 다운받아서 ~~~~하면 결과가 나오는데

 ![image](https://github.com/homind/control-systems-engineering/assets/101074052/849a08ef-a20b-4dd6-8cac-6e16eab9e887)


m만 필요하지 L은 필요없다고 한다.


특이케이스가 있어도 

![image](https://github.com/homind/control-systems-engineering/assets/101074052/29b950bc-e7df-49d5-9dc0-7d950dd04b04)

뭐라뭐라ㅏ 하면서 알려줌

그런데 이건 좀 비효율적인 방식이라고함. 그냥 특성방정식의 해를 찾아버리면 되기 때문에
 
![image](https://github.com/homind/control-systems-engineering/assets/101074052/1d9e107b-6f78-4d0e-9449-0910c9b535be)


matlab 기본함수를 써서 찾아버릴 수 있음. 


그러면 진짜 사용해야하는 경우는?? -> 파라미터가 있어서 지정해야할때 안정적으로 하기위할때 ~~ 사용함.

![image](https://github.com/homind/control-systems-engineering/assets/101074052/04eae2a2-822f-433e-a27a-a8badfeec334)

요렇게 그리고

![image](https://github.com/homind/control-systems-engineering/assets/101074052/9a507965-f02b-4830-b68c-d52b385a3603)


요렇게

![image](https://github.com/homind/control-systems-engineering/assets/101074052/4574b4f1-754d-4a27-8fd4-2d5476ec75b9)


요렇게








