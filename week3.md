.![header](https://capsule-render.vercel.app/api?type=wave&color=auto&height=300&section=header&text=Control-Systems-Engineering&fontSize=30)




#  제어공학1 - 2장 문제풀이 :computer: 



## P2.7 
### 그림 2.7과 같이 1차 저역통과 필터로 구현한 적분 증폭기 회로의 전달함수를 구하라.
#### 풀이

이상적인 연상증폭기의 동작조건으로  $i_1 =0,v_1,v_2=0$이다.
키르히호프 법칙을 적용하여 

$$
$\frac{(V_1(S) - v_1)}{R} + C\times \frac {d(v_1 - V_2(S))}{dt} = 0 \to \frac{V_1(S)}{R} =  C\times \frac {dV_2(S)}{dt}$
$$

