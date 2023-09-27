.![header](https://capsule-render.vercel.app/api?type=wave&color=auto&height=300&section=header&text=Control-Systems-Engineering&fontSize=30)




#  제어공학1 - 2장 문제풀이 :computer: 



## P2.7 
### 그림 2.7과 같이 1차 저역통과 필터로 구현한 적분 증폭기 회로의 전달함수를 구하라.
#### 풀이

이상적인 opamp 조건 : \(i_- = 0\), \(V_- = V_+ = 0\)

\(i_- = 0\)에 의해 다음식이 성립한다.

\[
\frac{V_1-V_-}{R} = \frac{V_--V_2}{\frac{1}{Cs}}
\]

\(V_- = V_+ = 0\)임으로 다음과 같이 정리된다.

\[
\frac{V_2}{V_1} = \frac{-1}{RCs}
\]

__답 )__ \(G(s) = \frac{-1}{RCs}\)

