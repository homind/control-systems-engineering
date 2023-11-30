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

시스템 전달함수 $T(s)$를 우선 구하면 $T(s) = \frac{100k}{0.2s^3 + 6s^2 + 45s + 100 + 100k}$이다.

$\textrm{S}_{K}^{T} = \frac{1}{1+G(S)G_c(S)} = \frac{0.2s^3 + 6s^2 + 45s + 100}{0.2s^3 + 6s^2 + 45s + 100 + 100k}$ 


(b) 외란 $T_d(s)$가 출력 $Y(s)$에 미치는 영향을 구하라.

외란에 의한 출력 $Y(S)$는 $\frac{G(s)}{1+G_c(s)G(s)} \cdot T_d(s)$ 이며 이를 풀면

$$
\frac{\frac{100}{s^2 + 25s + 100}}{1 + \frac{100k}{(s^2 + 25s + 100)(0.2s + 1)} \cdot T_d(s) }
$$

정리하면 다음과 같다.

$$
\frac{100(0.2s +1)}{0.2s^3 + 6s^2 + 45s + 100 + 100k}
$$


(c) 출력 $Y(s)$가 크기 $A$인 계단외란 입력 [즉, $T_d(s)$ = A/s]의 10%보다 작도록 하는 $K$의 범위를 찾아라.

외란 입력에 대한 K를 찾기 위해 최종값 정리를 적용한다. 

$$
\lim_{s \rightarrow 0}S\cdot\frac{100(0.2s +1)}{0.2s^3 + 6s^2 + 45s + 100 + 100k}\cdot\frac{A}{S} = 0.1\frac{A}{S}
$$

이를 정리하면

$$
\frac{100}{100+100k} < 0.1
$$

이며 이를 만족하기 위해서는 k는 9 이상의 값이어야 한다.

## P4.12
그림 4.12(a)와 (b)에 두 개의 궤환시스템이 주어졌다. 

![image](https://github.com/homind/control-systems-engineering/assets/101074052/3c6dc335-0029-4ce4-b065-b1b7fde6d53e)



#### 풀이
(a) 각 시스템의 폐루프 전달함수 $T_1$와 $T_2$를 계산하라. 

$$
T_1 = \frac{\frac{k_1\cdot k_2}{(s+4)(s-1)}}{1 + \frac{6k_1 \cdot k_2 }{(s+4)(s-1)}} = \frac{k_1k_2}{(s+4)(s-1)+6k_1k_2}
$$

$T_2$ 는 전달함수 2개를 곱하는 형식으로 구하면 $G_1(S) \cdot G_2(S)$로 구할 수 있다.

$$
\frac{\frac{k_1}{s+4}}{1 - \frac{2k_1}{s+4}} \cdot \frac{\frac{k_2}{s-1}}{1 - \frac{-2k_2}{s-1}}
$$

이며 정리하면 다음과 같다.

$$
\frac{k_1k_2}{s^2 + (3 +2k_2 - 2k_1)s + 8k_2 + 2k_1 -4k_1k_2 -4}
$$

(b) 공칭값이 $K_1 = K_2 = 1$일 때 매개변수 $K_1$에 대한 두 시스템의 감도를 구하라.

$$
\textrm{S}_{K_1}^{T_1} = \frac{K_1}{T_1} \cdot \frac{\mathrm{dT_1} }{\mathrm{d} k_1} 
$$

$$
\frac{(s+4)(s-1)+ 6k_1k_2}{k_2} \cdot \frac{k_2 \cdot ((s+4)(s-1)(6k_1k_2)) - (k_1k_2) \cdot 6k_2}{((s+4)(s-1)+6k_1k_2)^2} 
$$

$$
\frac{(s+4)(s-1)}{(s+4)(s-1)+6k_1k_2}
$$

$$
\textrm{S}_{K_2}^{T_2} = \frac{K_2}{T_2} \cdot \frac{\mathrm{dT_2} }{\mathrm{d} k_2} 
$$

정리하면

$$
\frac{(s^2 + (3 +2k_2 - 2k_1)s + 8k_2 + 2k_1 -4k_1k_2 -4}{k_2} \cdot \frac{k_2 \cdot (s^2 + (3 +2k_2 - 2k_1)s + 8k_2 + 2k_1 -4k_1k_2 -4) - k_1k_2(-2s +2 -4k_2 ) }{(s^2 + (3 +2k_2 - 2k_1)s + 8k_2 + 2k_1 -4k_1k_2 -4)^2} 
$$

$$
\frac{s+4}{s+2}
$$

## P4.17
그림 P4.17(b)에 주어진 직류전동기 제어시스템을 이용하여 그림 P4.17(a)에 그려진 로봇 집게의 각도가 $\theta$ 가 되도록 닫혀지게 제어하고자 한다. 제어시스템의 모델은 그림 P4.17(c)에 있으며, 이때 $K_m = 30, R_f = 1 \Omega , K_f = K_i = 1 , J = 0.1, b = 1$ 이다.

#### 풀이

(a) $K = 20$일 때, $\theta_d(t)$의 계단변화에 대한 시스템 응답 $\theta(t)$를 결정하라.

시스템 전달함수를 구하면 다음과 같다.

$$
T(S) = \frac{ \frac{600}{s(0.1s + 1)}}{1 + (\frac{600}{s(0.1s+1)})}= \frac{600}{s(0.1s + 1) + 600}
$$


해당 시스템 전달함수에 계단 입력을 곱하여 출력을 얻고 역라플라스 변환을 하면 $\theta(t)$를 얻을 수 있다.
해당 출력은 전달함수에 $\frac{1}{s}$만을 곱한 형태로 matlab을 통해 구하면 다음과 같다.

```
syms s
n = [6000];
d = [1 10 6000 0];

eqn1 = 6000 / (s^3 + 10*s^2 + 6000s)

ilaplace(eqn1)
```
![image](https://github.com/homind/control-systems-engineering/assets/101074052/a01f2a13-b0a4-4bc5-8bbb-34e14094b435)




(b) $\theta_d(t) = 0$으로 가정하여 부하외란 $T_d(s) = A/s$의 영향을 구하라.

외란에 의한 출력을 구하면  $Y(S)$는 $\frac{G(s)}{1+G_c(s)G(s)} \cdot T_d(s)$ 으로 다음과 같다.

$$
\frac{ \frac{1}{0.1s^2+s} }{1 + \frac{600}{0.1s^2+s} } \cdot \frac{A}{s}
$$

최종값 정리를 적용하면 

$$
\lim_{s \rightarrow 0}S\cdot\frac{1}{0.1s^2 +s + 600}\cdot\frac{A}{S} = \frac{A}{600}
$$

(c) 입력 $r(t) = t, t>0 $일 때 정상상태 오차 $e_ss$를 결정하라 [ $T_d(s) = 0$ 으로 가정한다.]

해당 입력에 대해 추종오차를 구하면 다음과 같다.
$E(S)$는 $\frac{1}{1+G_c(s)G(s)} \cdot R(s) = \frac{1}{1 + \frac{600}{0.1s^2 + s} } \cdot \frac{1}{s^2}$

$$
\lim_{s \rightarrow 0}S\cdot\frac{0.1s^2 + s}{0.1s^2 +s + 600}\cdot\frac{1}{S} = \frac{1}{600}
$$










