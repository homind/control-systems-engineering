피드백의 정량적 효과(open-loop 대비 외란과 노이즈의 감소량)

1.  복습 : 외란과 노이즈


![image](https://github.com/homind/control-systems-engineering/assets/101074052/fd4411af-d0b8-4571-aac9-2a72e91fa104)

외란은 시스템에 직접적으로 작용하는 에러, 노이즈는 피드백 과정중 센싱에서 일어나는 오차

위 그림에서
![image](https://github.com/homind/control-systems-engineering/assets/101074052/9da6cff2-01f3-4b9a-b454-63f5f6dbf522)

이게 외란과 노이즈인데 둘 다 그 자체로 줄일 수 없음. 건들일 수 있는게 S(S)랑 C(S)를 작게 해야함

결과적으로 루프의 전체 게인이 커야 루프의 외란이 줄어짐 -> G(S)는 못건드니까 센서쪽이나 컨트롤러 게인을 키우면 됨.

노이즈를 최소화 하려면 루프의 전체 게인이 작아야 노이즈가 작아짐 

-> S(S)와 C(S)의 합은 1이라 둘다 동시에 줄이거나 늘일 수는 없음. 
그래도 다행히 외란은 저주파에 노이즈는 고주파에서 주로 몰려있는 특징이 있음.

그런데 피드백 시스템을 사용하면 정말 에러가 감소하나?? 오픈루프에 비해 장점이 있나??를 예제로 확인

![image](https://github.com/homind/control-systems-engineering/assets/101074052/0232ed86-7177-4281-9ee5-c102cc816657)

Va가 인가 되면코일의 영향이 작다고 가정하면 저항의 성분만 고려한다. 그렇게 전업이 전류로 나타낼 수 있고 km(토크상수)의 배수 만큼의 토크를 만들어 낸다.
부하가 분수꼴로 나타남. 초반에는 모터를 방해하지만 나중에는 그 영향이 감소함. 이때 외란이 존재함. 
피드백 처럼 보일 수는 있지만 역기전력임 (그래도 너무 빨리 돌면 안되니까 적당히 조절하는??)

그래서 결론적으로 전압이 인가되면 속도로 결과가 나오는 오픈 루프 시스템으로 볼 수 있음.

![image](https://github.com/homind/control-systems-engineering/assets/101074052/4e15dc05-2d5d-40c7-b65c-5bc6785ef375)

해당 시스템에 최종값 정리와 외란을 정의하고 식을 정리하면 값을 얻을 수 있음. 이러한 시스템에 피드백을 걸어줌.

![image](https://github.com/homind/control-systems-engineering/assets/101074052/dbde6d1d-e5e1-4820-8961-c530bc936f43)


이후 오픈 루프 일때와 같이 외란을 정의하고 최종값정리를 적용하면
![image](https://github.com/homind/control-systems-engineering/assets/101074052/814b04ac-1093-43f9-a472-a91780666198)

Ka를 오픈루프떄와 달리 우리가 설정할 수 있어 외란을 줄일 수 있음.

또 다른 장점이 존재함
![image](https://github.com/homind/control-systems-engineering/assets/101074052/af95ac49-f2eb-43b7-84aa-27c999ae9634)
과도 응답(시스템이 시작하고 매우 짧은 시간동안의 결과?)를 보면 오픈루프는 원하는값에늦게 도달하지만 피드백인 클로즈 루프는 빠르게도달함.
그래서 두 그래프 어느거든 출력은 
![image](https://github.com/homind/control-systems-engineering/assets/101074052/c5fec0b4-45d8-4f29-92e8-e9d244d42a30)

이렇게 인데 
그 차이를 본다면
![image](https://github.com/homind/control-systems-engineering/assets/101074052/30b9bc18-b3e3-4dc9-9da6-c9dfa994e886)

그 지수함수의 기울기가 달라지는 것. 피드백을 달아준 것만으로 계수가 달라서 점근선에 근접하는 시정수가 바뀐 것. ! 시스템의 빠른 동작을 만든 것.


steady-state error 분석하기

![image](https://github.com/homind/control-systems-engineering/assets/101074052/0df55a86-f963-4e27-a847-5b31ed8b2b1a)

오픈 루프에서 외란을 0이라고 가정하여도 주파수가 0일때 즉, dc상태일때의 게인때문에 그 에러 값이 무시할 수 없는 값이 나옴.

피드백이라면???

![image](https://github.com/homind/control-systems-engineering/assets/101074052/52d0dafd-7c26-43df-babb-efee982206d1)


굉장히 작아짐. 


















