.![header](https://capsule-render.vercel.app/api?type=wave&color=auto&height=300&section=header&text=Control-Systems-Engineering&fontSize=30)




#  제어공학1 - 2장 문제풀이 :computer: 



## P2.7 
### 그림 2.7과 같이 1차 저역통과 필터로 구현한 적분 증폭기 회로의 전달함수를 구하라.
#### 풀이

이상적인 연상증폭기의 동작조건으로 \(i_{1} = 0\), \(v_{2}\), \(v_{1}=0\)이므로, 키르히호프 법칙을 사용하면 다음과 같은 방정식을 얻을 수 있습니다:

\[ V_{1}(S) - \frac{V_{1}}{R} + C \frac{d(V_{1} - V_{2}(S))}{dt} = 0 \]
