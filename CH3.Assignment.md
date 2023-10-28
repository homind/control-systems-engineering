.![header](https://capsule-render.vercel.app/api?type=wave&color=auto&height=300&section=header&text=Control-Systems-Engineering&fontSize=30)




#  제어공학1 - 3장 문제풀이 :computer: 



## P3.1
그림 P3.1에 스프링-질량-감쇠기 시스템이 주어져 있다.

(A) 적당한 상태변수를 설정하여라.

해당 시스템의 미분방정식을 세우면 다음과 같다.

$$
M\ddot{y(t)} + b\dot{y(t)} + ky(t) = F(t)
$$

2계 미분 방정식이므로 2개의 1계 미분방정식을 구하기 위해 2개의 상태변수를 설정하면 다음과 같이 정할 수 있다.

$$
x_1(t) = y(t), x_2(t) = \frac{\mathrm{dy(t)} }{\mathrm{d} t}
$$

(B) 상태변수로 표현된 1차 미분방정식을 구하라.
상태 변수를 적용하여 2개의 1차 미분방정식은 다음과 같다.

$$
\dot{x_1(t)} = \dot{y(t)}
$$

$$
\dot{x_2(t)} = \frac{1}{M}F(t) -\frac{b}{M}x_2(t)-\frac{k}{M}x_1(t)
$$

(C) 상태미분방정식을 구하라.
B의 두 식을 통해 다음과 같이 세울 수 있다.

$$
\dot{\tilde{x(t)}} = \begin{bmatrix}
0 & \frac{-k}{M}\\ 
\frac{-K}{M} & \frac{-B}{M}
\end{bmatrix}\begin{bmatrix}
 x_1(t) \\
 x_2(t)
\end{bmatrix}
+
\begin{bmatrix}
0 \\
 \frac{1}{M}
\end{bmatrix}
F(t)
$$


## P3.3
그림 3.3과 같은 RLC회로가 주어져 있다.상태변수 $x_1(t) = i_L(t),x_2(t) = v_c(t)$로 설정하고 상태미분방정식을 구하라. 
#### 풀이

전체 루프에 KVL을, 전류에 대하여  KCL을 적용하여 정리하면 다음의 과정을 거쳐 식을 얻을 수 있다.

$$
L\frac{\mathrm{di(t)} }{\mathrm{d} t} - v_c(t) + v_2(t) - v_1(t) = 0
\rightarrow
\frac{\mathrm{di(t)} }{\mathrm{d} t}  = \frac{1}{L} v_c(t) + -\frac{1}{L}v_2(t) + \frac{1}{L}v_1(t)
$$


$$
i_L(t) = i_R(t) - i_c(t) \rightarrow  \frac{\mathrm{dv_c(t)} }{\mathrm{d} t} = i_R(t) - i_L(t)
$$

상태미분방정식을 구하기 위해서 $x_1(t) = i_L(t), x_2(t) = v_c(t)$ 로 설정하며 이때, $i_R(t)$를  전압에 의한 유도식으로 변경해야한다.

$$
i_R(t) = \frac{1}{R}v_2(t) - \frac{1}{R}v_c(t)
$$

을 적용하여 식을 정리하면

$$
\dot{x_1(t)} = \frac{1}{L}x_2(t) - \frac{1}{L}v_2(t) + \frac{1}{L}v_1(t)
$$

$$
\dot{x_2(t)} = \frac{1}{RC}v_2(t) - \frac{1}{RC}x_2(t) - \frac{1}{C}x_1(t)
$$

따라서, 상태미분 방정식은

$$
\dot{\tilde{x(t)}} = \begin{bmatrix}
0 & \frac{1}{L}\\ 
\frac{-1}{C} & \frac{-1}{RC}
\end{bmatrix}\begin{bmatrix}
 x_1(t) \\
 x_2(t)
\end{bmatrix}
+
\begin{bmatrix}
 \frac{1}{L} & \frac{-1}{L}\\ 
 0 & \frac{1}{RC}
\end{bmatrix}\begin{bmatrix}
 V_1(t) \\
 V_2(t)
\end{bmatrix}
$$




## P3.5
그림 P3.5에 폐루프 제어시스템이 주어져 있다.
(A) 폐루프 전달함수 $T(s) = Y(s) / R(s)$를 구하라.

뒤 시스템은 피드백은 단위 피드백으로 전달함수를 구하면 다음과 같다.

$$
T(s) = \frac{Y(s)}{R(s)} = \frac{s+2}{s^3+5s^2-23s+2}
$$

(B) 상태변수 모델을 구하여라. (위상 변수 표준형)
위 전달함수의 상태변수모델을 위상 변수 표준형으로 구하기위해 분모와 분자에 $Z(s)$를 곱하고 식을 전개한다.

$$
Y(s) = S*Z(s) + 2Z(s)
$$

$$
s^3Z(s)+5s^2Z(s)-23sZ(s)+2
$$

이렇게 구한 식에 대하여 역 라플라스를 취하면 $y(t)$는 출력방정식으로 $r(t)$는 최고차항으로 정리하면 상태미분방정식을 완성할 수 있는 식을 얻게 된다. 따라서, 상태공간방정식을 정의하면 다음과 같다.

$$
\dot{\tilde{x(t)}} = \begin{bmatrix}
0 & 1 & 0\\ 
0 & 0 & 1 \\
-2 & 2 & -5 \\
\end{bmatrix}
x(t)
+
\begin{bmatrix}
 0\\ 
 0\\
 1
\end{bmatrix}
r(t)
$$

$$
y(t) =  \begin{bmatrix}
2 & 1 & 0\\ 
\end{bmatrix}
x(t)
$$

따라서 A,B,C,D는

$$
A = \begin{bmatrix}
0 & 1 & 0\\ 
0 & 0 & 1 \\
-2 & 2 & -5 \\
\end{bmatrix}
,
B=\begin{bmatrix}
 0\\ 
 0\\
 1
\end{bmatrix}
,
C=\begin{bmatrix}
2 & 1 & 0\\ 
\end{bmatrix}
,
D = 0
$$

## P3.12
다음 전달함수를 가지는 시스템에서

$$
\frac{Y(s)}{R(s)} = T(s) = \frac{8(s+5)}{s^3+12s^2+44s+48}
$$

(A) 상태공간모델을 구하라.
위 문제 3.5와 같은 방식으로 위상변수 표준형으로 상태공간모델을 정의하겠다.
분모와 분자에 동일하게 $Z(s)$를 곱해주어 식을 전개하면 다음과 같다.

$$
Y(s) = 8S*Z(s) + 40Z(s)
$$

$$
s^3Z(s)+12s^2Z(s) + 44sZ(s) + 48
$$

상태변수를 정의하면 $x_1(t) = z(t) ,x_2(t) = \dot{x_1(t} = \dot{z(t)}, x_3(t) = \dot{x_2(t)} = \ddot{z(t)} $와 같고 이를 통해 상태미분방정식과, 출력방정식을 정의하면 상태공간정식을 얻을 수 있다.

$$
\dot{\tilde{x(t)}} = \begin{bmatrix}
0 & 1 & 0\\ 
0 & 0 & 1 \\
-48 & -44 & -12 \\
\end{bmatrix}
x(t)
+
\begin{bmatrix}
 0\\ 
 0\\
 1
\end{bmatrix}
r(t)
$$

$$
y(t) =  \begin{bmatrix}
40 & 8 & 0\\ 
\end{bmatrix}
x(t)
$$

$$
A = \begin{bmatrix}
0 & 1 & 0\\ 
0 & 0 & 1 \\
-48 & -44 & -12 \\
\end{bmatrix}
,
B=\begin{bmatrix}
 0\\ 
 0\\
 1
\end{bmatrix}
,
C=\begin{bmatrix}
40& 8 & 0\\ 
\end{bmatrix}
,
D = 0
$$

(B) 상태천이 행렬 $\phi(t)$를 구하라.
$\phi(t)$ 는 $[S*I -A]^-1$의 역 라플라스를 통해 구할 수 있다. 

$$ 
[S*I -A]^-1 = \begin{bmatrix}
s & -1 & 0\\ 
0 & s & -1 \\
48 & -44 & s +12 \\
\end{bmatrix} 
$$ 

다음의 역행렬을 전개하면 다음과 같다.

$$
\begin{bmatrix}
\frac{(s^2+12s+44)}{(s^3+12s^2+44s+48)} & \frac{ (s+12)}{(s^3+12s^2+44s+48)} &\frac{1}{(s^3+12s^2+44s+48)} \\ 
\frac{-48}{(s^3+12s^2+44s+48)} & \frac{(s^2+12s)}{(s^3+12s^2+44s+48)} & \frac{s}{(s^3+12s^2+44s+48)}\\ 
\frac{-48*s}{(s^3+12s^2+44s+48)} & \frac{(-44s-48)}{(s^3+12s^2+44s+48)} & \frac{s^2}{(s^3+12s^2+44s+48)}
\end{bmatrix}
$$

이제 위 식에 역 라플라스를 취하면 상태천이행렬을 얻을 수 있다.

$$
\phi(t) = 
\begin{bmatrix}
e^{-6t} -3e^{-4t} +3e^{-2t} & \frac{3}{4}e^{-6t} -2e^{-4t} +\frac{5}{4}e^{-2t} & \frac{1}{9}e^{-6t} -\frac{1}{4}e^{-4t}+ \frac{1}{8}e^{-2t}\\ 
-6e^{-6t} +12e^{-4t} -6e^{-2t}& \frac{-9}{2}e^{-6t} +8e^{-4t}+ \frac{-5}{2}e^{-2t} & \frac{-3}{4}e^{-6t} +e^{-4t} \frac{-1}{4}e^{-2t} \\ 
 36e^{-6t} -48e^{-4t} +12e^{-2t}& 27e^{-6t} -32e^{-4t} +5e^{-2t} & \frac{9}{2}e^{-6t} -4e^{-4t} +\frac{1}{2}e^{-2t}
\end{bmatrix}
$$

### P3.17
다음과 같은 상태변수 방정식으로 표현된 시스템에서 $G(s) = \frac{Y(s)}{U(s)}$을 구하라.

해당 시스템의 상태공간방정식은 다음과 주어져있다.

$$
\dot{\tilde{x(t)}} = \begin{bmatrix}
1 & 1 & -1\\ 
4 & 3 & 0 \\
-2 & 1 & 10 \\
\end{bmatrix}
x(t)
+
\begin{bmatrix}
 0\\ 
 0\\
 4
\end{bmatrix}
u(t)
$$

$$
y(t) =  \begin{bmatrix}
1 & 0 & 0\\ 
\end{bmatrix}
x(t)
$$

이러한 시스템에서 전달함수 $G(s)$는 $C*\phi(s)*B$를 전개하면 얻을 수 있다. 시스템의 $C,B$는 $0$을 포함하는 요소인 행렬로 식을 모두 전개하지 않고 필요한 부분만 발췌한다면 간단하게 원하는 답을 얻을 수 있다.


$$
\begin{bmatrix}
1 & 0 & 0
\end{bmatrix} \cdot 
\begin{bmatrix}
\frac{(s^2-13s+30)}{(s^3-14s^2+37s+20)} & \frac{ (s-11)}{(s^3-14s^2+37s+20)} &\frac{-s+3}{(s^3-14s^2+37s+20)} \\ 
\frac{+4s-40}{(s^3-14s^2+37s+20)} & \frac{(s^2-11s+8)}{(s^3-14s^2+37s+20)} & \frac{-4}{(s^3-14s^2+37s+20)}\\ 
\frac{-2s+10}{(s^3-14s^2+37s+20)} & \frac{(s-3)}{(s^3-14s^2+37s+20)} & \frac{s^2-4s-1}{(s^3-14s^2+37s+20)}
\end{bmatrix}\cdot \begin{bmatrix}
0\\
0\\
4 
\end{bmatrix}
$$

$\phi(s),B$를 정리하여 $C$를 전개하자. 그 결과는 다음과 같다.

$$
\begin{bmatrix}
1 & 0 & 0
\end{bmatrix} \cdot 
\begin{bmatrix}
&\frac{-4s+12}{(s^3-14s^2+37s+20)}\\ 
&\frac{-16}{(s^3-14s^2+37s+20)}\\ 
&\frac{4s^2-16s-4}{(s^3-14s^2+37s+20)}
\end{bmatrix}
\rightarrow 
\frac{-4s+12}{(s^3-14s^2+37s+20)}
$$





따라서 전달함수는, $\frac{-4s+12}{(s^3-14s^2+37s+20)}$ 이다.
