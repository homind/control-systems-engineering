
![image](https://github.com/homind/control-systems-engineering/assets/101074052/b8411333-b495-401d-8d0c-8c351a821855)

피드백이 1이 아닌 경우 전달함수에는 H(s)가 있는데
이러한 경우에도 그냥 Z(s)라고 가정하고 단위피드백인 시스템과 같다고 해석하고 Z(s)를 푼다.


 최적화

 성능을 높이기 위해 최적화를 함.

 에러가 제일 작은게 좋음. -> 종합적으로 모든 에러를 합쳤을때!가 중요한것

 최적화 함수는 이러한 것을 알 수 있음.  

 ![image](https://github.com/homind/control-systems-engineering/assets/101074052/54e17ae5-4f30-4033-9930-7b81fb4930c3)

 t는 시간을 곱해서 적분하는 방식 -> 시간이 지남에 따라 큰값이 곲해지니 초반에러는 인정하는데 뒷 에러는 인정하지 않는 뒷쪽의 에어를 중요시하는 경우



 3차를 2차로 와같이 차수를 낮추고 싶을 때

 우선 분자를 맞춰야함.

 그리고 원본시스템을 낮춘시스템으로 나눔

 이 나눈 것의 분모와 문자를 각각 정의하고

 1,2,3,4....계 미분에 대한 0의 값을 정함
이때 미분을 몇번해야 하느냐?? 분모와 분자를 정했을때 분자의 근이 2개라면 

미분 식 2개당 1개 이므로 4번 미분하는 것. 그러면 2개 얻어짐.

이렇게 

![image](https://github.com/homind/control-systems-engineering/assets/101074052/5002f229-7bb0-4d32-8299-7e65e040560c)

그 결과는 

![image](https://github.com/homind/control-systems-engineering/assets/101074052/4cf4aee1-373c-4b5c-aaf0-ea366d219acf)


보면 첫번째 폴은 거의 변하지 않음 이것이 도미넌트 폴임 가장 지배적인 영향력이 쎈!, 그런데 -1.565는 그래서 도미넌트 폴을 제외한
-2와 -3을 -1.565로 근사한것




 
