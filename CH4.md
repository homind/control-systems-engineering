.![header](https://capsule-render.vercel.app/api?type=wave&color=auto&height=300&section=header&text=Control-Systems-Engineering&fontSize=30)




#  제어공학1 - 4장 문제풀이 :computer: 



## P4.8
전자회로 주변에서 온도가 극단적으로 변하면 다양한 고장이 발생한다. 온도제어 궤환시스템은 실외 저온을 극복하기 위해 히터를 사용하여 온도변화를 감소시킨다. 한 시스템의 블록선도가 그림 P4.8에 있다. 주변온도 하락은 $T_d(s)$에서 계단 감소로 표현된다. 전자회로의 실제 온도는 $Y(s)$이다. 전자회로의 온도변화의 동역학은 다음과 같은 전달함수로 표현된다.

![image](https://github.com/homind/control-systems-engineering/assets/101074052/77854ffc-09f4-487e-bcfd-4189250c1288)


$$
G(s) = \frac{100}{s^2 +25s +100}
$$


#### 풀이
(a)  $K$에 대한 시스템의 감도를 구하라

(b) 외란 $T_d(s)$가 출력 $Y(s)$에 미치는 영향을 구하라.

(c) 출력 $Y(s)$가 크기 $A$인 계단외란 입력 [즉, $T_d(s)$ = A/s]의 10%보다 작도록 하는 $K$의 범위를 찾아라.




## P4.12
그림 4.12(a)와 (b)에 두 개의 궤환시스템이 주어졌다. 

![image](https://github.com/homind/control-systems-engineering/assets/101074052/3c6dc335-0029-4ce4-b065-b1b7fde6d53e)



#### 풀이
(a) 각 시스템의 폐루프 전달함수 $T_1$와 $T_2$를 계산하라. 

(b) 공칭값이 $K_1 = K_2 = 1$일 때 매개변수 $K_1$에 대한 두 시스템의 감도를 구하라.

## P4.17
그림 P4.17(b)에 주어진 직류전동기 제어시스템을 이용하여 그림 P4.17(a)에 그려진 로봇 집게의 각도가 $\theta$ 가 되도록 닫혀지게 제어하고자 한다. 제어시스템의 모델은 그림 P4.17(c)에 있으며, 이때 $K_m = 30, R_f = 1 \Omega , K_f = K_i = 1 , J = 0.1, b = 1$ 이다.

#### 풀이

(a) $K = 20$일 때, $\theta_d(t)$의 계단변화에 대한 시스템 응답 $\theta(t)$를 결정하라.

(b) $\theta_d(t) = 0$으로 가정하여 부하외란 $T_d(s) = A/s$의 영향을 구하라. 

(c) 입력 $r(t) = t, t>0 $일 때 정상상태 오차 $e_ss$를 결정하라 [ $T_d(s) = 0$ 으로 가정한다.]









