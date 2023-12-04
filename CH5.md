.![header](https://capsule-render.vercel.app/api?type=wave&color=auto&height=300&section=header&text=Control-Systems-Engineering&fontSize=30)




#  제어공학1 - 5&6장 문제풀이 :computer: 



## P5.3
레이저 광선은 그림P5.3(a)와 같이 금속을 용접, 천공, 부식, 절단 표시하기 위해 사용한다. 그림 P5.3(b)와 같은 폐루프 제어시스템으로 표현되는 정밀한 레이저를 사용하여 직선 경로를 표시할 작업이 있다고 가정한다. $r(t) = t mm$에 대해 정상상태 오차가 5mm가 되도록 필요한 이득 $K$와 $K_1$을 계산하라.

#### 풀이
정상상태 오차를 계산을 위해 시스템 전달함수 $T(S)$를 우선 구한다.

$T(S) = \frac{\frac{k}{s(s+k_1)}}{1+\frac{k}{s(s+k_1)}} = \frac{k}{s(s+k_1) + k}$

입력 $r(t) = t 는 곧 R(S) = \frac{1}{s^2}$이므로 정상상태 오차 $e_ss$는 다음과 같다.

$$
e_ss = \lim_{s\rightarrow 0}s\cdot E(s) = \lim_{s\rightarrow 0}s\cdot (1 - T(s))\cdot R(s) = \lim_{s\rightarrow 0}(1 - \frac{k}{s(s+k_1) + k})\cdot \frac{s}{s^2} = \lim_{s\rightarrow 0} \frac{s+k_1}{s(s+k_1) + k} 
$$

정리하면, $k_1 = 5k$이다.



## P5.5
시스템이 그림P5.5에 그려져 있다. 제어시스템은 그림P5.5(b)에 있다. $\tau_1 = 1, \tau_2 = 0$이라고 가정한다.

#### 풀이
(a) 백분율 오버슈트가 $P.O. \leq 5%$ 이내에서 게단명령에 대한 응답이 가능한 한 신속하도록 필요한 이득 $K = K_1K_2$를 결정하라.

해당시스템의 전달함수는 $T(s) = \frac{\frac{k_1k_2(s+1)}{s^2}}{1 + \frac{k_1k_2(s+1)}{s^2}} = \frac{k_1k_2(s+1)}{s^2 + k_1k_2s + k_1k_2}$

해당 시스템의 특성방정식은 전달함수의 분모로 $s^2 + k_1k_2s + k_1k_2 = 0 $이며 문제에서 문제에서 백분율 오버슈트는 $5%$이내라고 하였으므로 식을 통해 감쇠비를 구해준다.

$$
P.O. = 100e^{\frac{-\xi \pi }{\sqrt{1-\xi ^{2}}}} \rightarrow  \xi = 0.69
$$

감쇠비를 통해서 특성방정식을 이용하면 $k_1k_2$를 구할 수 있다. 


$$
2\xi\omega_n = k_1k_2 그리고 (\omega_n)^2 = k_1k_2 \rightarrow \rightarrow = 1.38
$$

따라서 $k_1k_2 = 1.9$이다.


(b) 계단 입력과 경사입력에 대한 시스템의 정상상태 오차를 결정하라.

계단 입력에 대한 정상상태 오차는 다음과 같다.

$$
e_ss = \lim_{s\rightarrow 0}s\cdot E(s) = \lim_{s\rightarrow 0}s\cdot (1 - T(s))\cdot R(s) = \lim_{s\rightarrow 0}\frac{s^2}{s^2 + k_1k_2s + k_1k_2} = 0
$$

경사입력에 대한 정상상태 오차는 다음과 같다.

$$
e_ss = \lim_{s\rightarrow 0}s\cdot E(s) = \lim_{s\rightarrow 0}s\cdot (1 - T(s))\cdot R(s) = \lim_{s\rightarrow 0}\frac{s}{s^2 + k_1k_2s + k_1k_2} = 0
$$

결과적으로 계단입력, 경사입력에 대하여 해당시스템의 정상상태 오차는 모두 0이다.

## P5.7
제어기는 그림 P5.7과 같이 이득 $K_2$로 표현할 수 있다. 관성력 $I = 25Kgm^2$이다.
#### 풀이

(a) 단위경사 입력에 대해 정상상태 오차를 $1cm$로 유지하는데 필요한 이득 $K_3$을 결정하라.

동일하게 시스템의 전달함수를 우선적으로 계산하면 다음과 같다.

$$
T(s) = \frac{k_1\cdot k_2\cdot \frac{1}{Is}\cdot \frac{1}{s}}{1 +k_1\cdot k_2\cdot \frac{1}{Is}\cdot k_3 + k_1\cdot k_2\cdot \frac{1}{Is}\cdot \frac{1}{s}} = \frac{k_1\cdot k_2}{Is^2 + k_1k_2k_3s + k_1k_2}
$$

이에 입력에 대한 정상상태 오차를 구하면 다음과 같다.

$$
e_ss = \lim_{s\rightarrow 0}s\cdot E(s) = \lim_{s\rightarrow 0}s\cdot (1 - T(s))\cdot R(s) = \lim_{s\rightarrow 0}\frac{Is + k_1\cdot k_2\cdot k_3}{Is^2 + k_1k_2k_3s + k_1k_2} = k_3
$$

따라서 $k_3 = 0.01$이다.


(b) 앞에서 구한 이득 $K_3$에서 필요한 백분율 오버슈트를  $P.O. \leq 10%$ 이내로 제한하기 위해 필요한 이득 $K_1K_2$를 결정하라.

a에서 구한 $k_3$를 통해 전달함수를 구하면 다음과 같다. $T(s) = \frac{k_1k_2}{25s^2 + 0.01k_1k_2s + k_1k_2} = \frac{\frac{k_1k_2}{25}}{s^2 + \frac{0.01k_1k_2}{25}s + \frac{k_1k_2}{25} }$

해당 특성 방정식은 $s^2 + \frac{0.01k_1k_2}{25}s + \frac{k_1k_2}{25}$ 이므로 주어진 백분율 오버슈트를 통해 감쇠비를 구하면 $k_1k_2$를 구할 수 있다.

감쇠비는 $P.O. = 100e^{\frac{-\xi \pi }{\sqrt{1-\xi ^{2}}}} \rightarrow  \xi = 0.59 = 0.6$ 이다.

이를 통해 

$$
\omega ^{2} = \frac{0.01k_1k_2}{25\cdot 1.2}^{2} = \frac{k_1k_2}{25} \rightarrow k_1k_2 = \frac{(25\cdot 1.2)^{2}}{0.01^{2}\cdot 25}=36\cdot 10^4
$$

## P5.10
전기자제어 직류 전동기의 속도제어시스템은 전동기의 역기전력 전압을 궤환신호로 이용한다.

#### 풀이
(a) 이 시스템의 블록선도를 그려라

![image](https://github.com/homind/control-systems-engineering/assets/101074052/1afe1c5c-773e-411b-a367-aa1b558d81b2)



(b) 속도를 새로운 기준치로 지정하는 계단입력 명령에 대해 이 시스템의 정상상태 오차를 계산하라.
$R_a = L_a =  J = b = K_m = K_b = 1$

전달함수를 구하면 다음과 같다.

$T(s) = \frac{\frac{k}{(s+1)(s+1)}}{1 + \frac{k}{(s+1)(s+1)}} = \frac{k}{s^2 + 2s + k+1}$

이를 통해 정상상태 오차를 구하면 다음과 같다.

$$
e_ss = \lim_{s\rightarrow 0}s\cdot E(s) = \lim_{s\rightarrow 0}s\cdot (1 - T(s))\cdot R(s) = \lim_{s\rightarrow 0}\frac{s^2 + 2s + 1}{s^2 + 2s + k + 1} = \frac{1}{k+1} 
$$




(c) 백분율 오버슈트  $P.O. \leq 15%$를 갖는 계단응답을 산출하기 위한 역기전력 신호의 궤환이득을 선정하라. 

백분율 오버슈틀를 통해 감쇠비를 구하면 다음과 같다.

$P.O. = 100e^{\frac{-\xi \pi }{\sqrt{1-\xi ^{2}}}} \rightarrow  \xi = 0.517$

마찬가지로 특성방정식을 이용하여 $k$를 구하면 

$$
0.517\omega_n = 1 \rightarrow \omega_n = 1.93 
$$


$$
k + 1 = (\omega_n)^{2} \rightarrow k=2.7
$$



