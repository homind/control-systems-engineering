제어 정리 상태공간방정식3
지난 내용정리
  ![image](https://github.com/homind/control-systems-engineering/assets/101074052/7e17a68f-f60b-453e-af3d-9b1bd246d01d)
  
  전달함수를 구하졌다 가정하고 -> 분모, 분자 계수 설정 - > tf2ss함수를 사용하여 상태방정식 abcd계수를 얻음.
  결과는 다음과 같음
  ![image](https://github.com/homind/control-systems-engineering/assets/101074052/16bbdf03-0032-472d-8fd4-3bac12c6974b)

 이때, abcd를 통해 전달함수를 못 구하나? 있음. ss2ff가 있는데 문자가 아닌 숫자를 넣어줘야 진행이 됨
 ![image](https://github.com/homind/control-systems-engineering/assets/101074052/56d8250f-fe6f-4ab9-9c31-79fc636aeb34)


그래도 a b c d 를 구할 때, 문자가 포함된 전달함수를 통해서 구했던 것 처럼, a b c d 가 문자일때도 전달함수를 구할 수 있지않을까?

![image](https://github.com/homind/control-systems-engineering/assets/101074052/e74cb809-a994-43bc-8a82-0077086fe1b5)
이렇게 $x(t) y(t)$ 를 라플라스 변환하여 구함.

ss2ff를 이용해서 구할수는 없만 g(s)를 통해서 구할 수 있겠다! 
![image](https://github.com/homind/control-systems-engineering/assets/101074052/ca663104-b68b-44a4-b438-937504611b0e)

파이(s) = s*단위행렬(eye라고표현) - A의 역행렬
결과로는
![image](https://github.com/homind/control-systems-engineering/assets/101074052/90484b26-b4c0-4ff9-907a-12721fdc24a1)
이를통해 문자가 행렬안에 포함되어이더라도 상태공간방정식으로부터 전달함수를 구할 수 있다.

------

보통 상태공간방정식을 전달함수로 바꾸는 경우는 상태공간 방정식을 알고 있는 경우에서 출발한 것.

그래서
![image](https://github.com/homind/control-systems-engineering/assets/101074052/84e0f351-3497-4f96-92c9-9fdf05c1d268)

해당 각각의 시스템을 알고 있으면 각 시스템에 상태변수를 설정해 
![image](https://github.com/homind/control-systems-engineering/assets/101074052/7917df6b-b9e9-482b-b1b6-c9845a2f8edd)

의 신호흐름선도를 알고 있다고 가정을할 수 있음. 이를 통해 상태공간방정식을 미리 알고있다고 가정할 수 있음

---

![image](https://github.com/homind/control-systems-engineering/assets/101074052/3bb85751-f89d-451b-ad4d-796f454f77e4)

이렇다고 가정하고 전달함수를 구해보자.
![image](https://github.com/homind/control-systems-engineering/assets/101074052/bdb2aa50-d2ef-4117-8a0c-4a9e7c9a6c1a)

-> numden함수는 G함수를받고 분자를 n에 분모를 d에 넣어주는 함수임

그래서
![image](https://github.com/homind/control-systems-engineering/assets/101074052/cea5da5c-ef5c-4b0f-99ad-ad082116fed2)

이렇게 나옴.

즉, ss2ff를 사용해서 상태공간방정식 -> 전달함수를 구하려했는데 이게 문자가 포함되어있어 안됐었음.
그래서 행렬을 식을 가져왔음 위의 예시는 ss2ff를 할 수 있는 경우임.(숫자이니까)


----
![image](https://github.com/homind/control-systems-engineering/assets/101074052/5184c7e8-202b-448f-98a1-d5df8f9fd0ed)
그렇다면 구해진 전달함수의 분모 분자가 올바른지 확인하기 위한 과정

tf2ss에는 분자,분모 계수 벡터가 들어가기떄문에 sym2poly을 통해 계수만뽑아옴(문자가 하낭닐떄 사용하기 좋음 문자가 여러개일ㄸ는 coeffs를 상용)
 ![image](https://github.com/homind/control-systems-engineering/assets/101074052/f09575b6-0e86-4a33-97bc-126f453cbbf7)



 --------------------------
![image](https://github.com/homind/control-systems-engineering/assets/101074052/590964cc-b4e3-4e60-aa82-22adc7eee6d5)

![image](https://github.com/homind/control-systems-engineering/assets/101074052/dbc0d7d4-47ee-4b77-9c4b-7bde5838ef59)
여기서 출력은 p(t)에 대해서만 본다 가정하고 y=[1000]으로 설정함.

![image](https://github.com/homind/control-systems-engineering/assets/101074052/1151e9f5-0f51-454c-8a72-7957ede0f72b)

결과 잘 나옴


-----
전달함수 -> 상태공간방정식

![image](https://github.com/homind/control-systems-engineering/assets/101074052/34ca97bb-e6a9-4fa0-9a84-62794e816a02)


coeffs를 사용해서 s의 계수들만 가져옴 근데 저차부터 가져오기 떄문에 flip를 통해 뒤집음.

![image](https://github.com/homind/control-systems-engineering/assets/101074052/4a6d5420-ff77-4d86-a830-fe9712738441)

num과 den이 잘 나오며 tf2ss를 통해 

![image](https://github.com/homind/control-systems-engineering/assets/101074052/08bc4362-f62f-4c76-b48f-f05bea33f355)

출력됨.



------

시스템 전달함수와 상태공간방정식을 안다는것은 직접 시뮬레이션 할 수 있따 -> 시간이지남에 따라의출력을알고 그래프를 그려볼 수 있음.


![image](https://github.com/homind/control-systems-engineering/assets/101074052/2cb72515-c032-446f-ac0c-49539aa4c1c5)
행렬미분방정식을 통해서 x(t)를 얻는대 앞쪽은 초기 state에 state trasition matrix을 곱한 것이며, 뒷쪽은 입력에 대한 state trasition matrix은 을 곱해서 컨벌루젼 연산임

state trasition matrix만 알수 있으면 시뮬레이션 가능

state trasition matrixㄴ느 결국 파이를 역라플라스~~~블라블라~~ -> a매트리스만 알수있으면 초기상태 해석가능!

b매트릭스의 인풀을 알면 전체를 알수 있따.!!!!

------
![image](https:/ /github.com/homind/control-systems-engineering/assets/101074052/adb7609b-db7b-42bb-b2c2-176179ac3588)


![image](https://github.com/homind/control-systems-engineering/assets/101074052/94f255b5-034c-4d34-a788-e83d60ed234a)

이러한 상태공간방정식을 통해 시스템의 정보를 알고 시뮬레이션을 해보자 


![image](https://github.com/homind/control-systems-engineering/assets/101074052/310825a0-7aa9-43d6-9877-dc0d376832cd)

 state trasition matrix를 구하자.

 ![image](https://github.com/homind/control-systems-engineering/assets/101074052/944fe84f-7fd9-4b0b-ad9c-061b31fae3c0)

를 입력하고
 
![image](https://github.com/homind/control-systems-engineering/assets/101074052/c0b6d437-e557-4a29-85a2-873c1baef23c)

파이t를 구하자 파이s를 구하고 역라플라스해서!

![image](https://github.com/homind/control-systems-engineering/assets/101074052/13be65d4-d863-42ed-9ec3-a865914a49d2)

파이타우구하기 t대신 t-tau를 넣음.

 ![image](https://github.com/homind/control-systems-engineering/assets/101074052/7695f4fb-711e-48d7-a897-086eee71f514)


초기조건 및 x(t)식 

ut는 단위계딴이라 1임 그냥 ㄱ래서 적분식에 없ㄷ음.

-----

좀더 간단하게
![image](https://github.com/homind/control-systems-engineering/assets/101074052/0885b256-d421-4681-ae6a-fa22841251d2)

step을 사용

input이 단위계딴이라 가정하고 output을 출력하ㅗㄱ 그래프 그려주는 함수

abcd를 정의하고 ss로 상태변수로 정의

10초까지 시뮬레이션

