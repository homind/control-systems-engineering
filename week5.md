.![header](https://capsule-render.vercel.app/api?type=wave&color=auto&height=300&section=header&text=Control-Systems-Engineering&fontSize=30)




#  제어공학1 - 5주차 강의요약 :computer: 
## State Variables
  ### State Variables이란?  
   시스템의 state variable은 system이 지금 어떤 상태에 있는지 알 수 있게 해주는 변수로 현재 시스템의 전체 상태를 간결하게 파악하고 예측할 수 있다.
   
   __이때, 주의할 점으로는 $N$차 미분 방정식에서 $N$개 state를 정의함에 있어 방법은 상관 없지만, state들 간의 관계가 항등식이 되면 안된다.__

이러한 점을 주의하며 $N$개의 state를 통해 $N$차 미분 방정식을 $N$개의 1차 미분방정식으로 식을 세우게 되면, 수식으로부터 중간 과정에서 의미 파악이 용이하며 식 자체가 1차 행렬 미분 방정식으로 바뀌어서 컴퓨터에게 연산을 명령을 내리기 쉬워진다.

다음 2가지 예제를 통해 State varialbe을 이해하도록 하자.

---


###  Spirng - mass - damper system & R-L-C circuit system

#####  Spirng - mass - damper system
![화면 캡처 2023-10-06 005237](https://github.com/homind/control-systems-engineering/assets/101074052/b0a27ad8-bf29-42c6-8d26-b23f45562de8)

위 그림에 뉴턴의 운동법칙을 적용하면 그 식은 $M\frac{d^2y(t)}{dt^2} + b\frac{dy(t)}{dt} + ky(t) = r(t)$이 된다.


$$
상태 변수 : x_1(t) = y(t), x_2(t) = \frac{dy(t)}{dt}
$$

이러한 state variables를 위 식에 적용하면 2차 미분방정식을 2개의 일차 미분 방정식으로 표현할 수 있다.

$$
식 1 : \frac{x_1(t)}{dt} = x_2(t)
$$

$$
식 2 : \frac{x_2(t)}{dt} = \frac{-2}{M} \cdot x_2(t) - \frac{k}{M} \cdot x_1(t) + \frac{1}{M} \cdot r(t) ,  y(t) = x_1(t) 
$$

#####  R-L-C circuit system
![화면 캡처 2023-10-06 010159](https://github.com/homind/control-systems-engineering/assets/101074052/b47b13a9-0019-4924-9049-a6d008c73e3b)

마찬가지로, 위 R-L-C 회로에 전압과 전류를 아래와 같이 state variables로 정의하고 키르히호프 법칙을 통해 정리하면 2개의 1차 미분 방정식으로 표현할 수 있다.

$$
상태변수 : x_1(t) = v_c(t), x_2(t) = i_L(t)
$$

$$
식1 : u(t) = C \cdot \frac{dx_1(t)}{dt} + x_2(t)  \rightarrow   \frac{dx_1(t)}{dt} = \frac{1}{C}[-x_2(t) + u(t)]
$$

$$
식2 : L \cdot \frac{dx_2(t)}{dt} + Rx_2(t) - x_1(t) = 0 \rightarrow \frac{dx_2(t)}{dt} = \frac{1}{L}[x_1(t) - Rx_2(t)] ,  y(t) = Rx_2(t)
$$

----------
## State space Equation
state space equation은 두 종류로 이루어 진다고 볼 수 있다. 그 중 하나는, 위에서 $N$개의 1차 방정식을 통해 행렬 방정식을 만드는 $state different equation$과 $out put equation$이다.






#### 사진 출처
https://tnwjdyd.tistory.com/13

