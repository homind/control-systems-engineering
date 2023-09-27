.![header](https://capsule-render.vercel.app/api?type=wave&color=auto&height=300&section=header&text=Control-Systems-Engineering&fontSize=30)




#  제어공학1 - 2장 문제풀이 :computer: 



## P2.7 
그림 2.7과 같이 1차 저역통과 필터로 구현한 적분 증폭기 회로의 전달함수를 구하라.
#### 풀이

이상적인 연상증폭기의 동작조건으로  $i_1 =0,v_1,v_2=0$이다.
키르히호프 법칙을 적용하여 

$$
\frac{(V_1(S) - v_1)}{R} + C\times \frac {d(v_1 - V_2(S))}{dt} = 0 \to \frac{V_1(S)}{R} =  C\times \frac {dV_2(S)}{dt}
$$

라플라스 변환을 통해 전달함수를 구하면

$$
\frac{V_1(S)}{R} =  CsV_2(S) \to V_2(S) = \frac{V_1(S)}{RCs} \to G(s) = \frac{V_2(S)}{V_1(S)} = \frac{1}{RCs}
$$


## P2.12

그림 p2.12에 주어진 블록선도로 표현된 개루프 제어 시스템에 대해 $t \to \infty$ 일 때 단위계단 입력 $r(t)$에 대한 응답  $y(t)\to\ 1$ 이되도록 $K$ 값을 정하라. 초기조건은 영이라고 가정한다.
#### 풀이
초기조건이 0 이므로, Laplace로 입,출력 비 표현이 가능하다. $\to\$ $\frac{Y(S)}{R(S)} = \frac{K}{(S+50)}$ 이다.

$$
Y(S) = \frac{K}{(S+50)} \cdot R(S) 이다. 이때 r(t)는 단위계단입력으로 그 라플라스 변환 값은 R(S) = \frac{1}{S}
즉, Y(S) = \frac{K}{S(S+50)} \to Y(S) = \frac{K}{50} \cdot ( \frac{1}{S} - \frac{1}{(S+50)} )이며, 역라플라스 변환을 통해

y(t) = \frac{K}{50} \cdot ( 1 - exp^(-50t) ) 이다. $t \to \infty$ 일때 , $y(t) \to \ 1$ 이 되기위해서 K = 50이 되어야한다. 
$$




