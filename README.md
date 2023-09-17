![header](https://capsule-render.vercel.app/api?type=wave&color=auto&height=300&section=header&text=Control-Systems-Engineering %20render&fontSize=50)




#  제어공학1 - 강의요약 :computer: 
## :one: Google Colab & Markdown
  ### :books: Google colab이란?  
  구글에서 제공하는 **머신러닝 클라우드 플랫폼**으로, 웹 브라우저 내에서 다양한 머신러닝 기법을 프로그래밍하고 그 결과까지 확인해볼 수 있다. 특히 GPU를 지원하여 제한된 범위 내에서 개인용 PC보다 빠른 성능을 보여주기도 한다.  
  ### :books:  Google Colab 기본설정  
   1.구글 계정에 로그인한 후 (https://colab.research.google.com) 접속한다.  
   2.위 주소에 접속한 후 `새 노트`를 클릭하여 좌측에 있는 ![파일모양](https://user-images.githubusercontent.com/101074052/156951688-29426a86-17fe-4d7a-8f72-9ba912840206.jpg)
 을 클릭하여 `드라이브 마운트`를 통해 Google Drive와 연결을 한다.  
   3.드라이브 마운트가 되었으면 런타임 - 런타임 유형 변경을 통해 NONE을 GPU로 변경해 준다.(굳이 변경 안해도 되지만 후에 필요함)  
   4.이후 **+코드**를 통해 자신이 원하는 코드를 입력할 수 있고 **+텍스트**를 통해 자신이 원하는 문서 작업을 실행할 수 있다.  
   

 ### :books: Google Colab의 Notebook 단축키 및 Markdown사용법
  >#### :keyboard:  Notebook단축키 
- Notebook의 단축키는 **Ctrl + M H**를 통해 여러 기본 단축키를 알 수 있으며 사용자의 편의대로 단축키를 설정할 수 있다. 아래의 사진은 **Ctrl + M H**을 통한 화면이다.  
![단축키 캡처](https://user-images.githubusercontent.com/101074052/156962736-fb4e6c7e-5c2d-4436-bbda-7157f9aeaed9.jpg)

      
 > #### :computer_mouse: Markdown 사용법  	
- Google Colab의 Notebook은 텍스트 편집할때 사용하는  Markdown이라는 문법을 이용해 문서와 소스코드를 한 문서에 배치할 수 있다. Markdown은 **확장자명이 md**이며 서식 편집언어를 이용해 Coding으로 문서를 작성한다. Markdown을 이용해 _타이틀, 강조, 줄바꿈, Code Block, 이미지, 표, 수식_ 등 여러 문법을 Notebook에 나타낼 수 있다.  
- **Markdown 주요 문법**을 이미지 링크로 나타내줄테니 확인해 보자.
>> - 링크 [![링크 ](https://user-images.githubusercontent.com/101074052/156950974-7aec9cf2-3ac0-473f-b108-fc25bb3472af.jpg)
](https://drive.google.com/file/d/1TeS-B46ifwO1U1B9SsuTtlbIgBI1pU2A/view?usp=sharing)
>> - 순서없는 목록 [![순서없는목록](https://user-images.githubusercontent.com/101074052/156951099-c22fd06f-eec5-4fa9-9b8d-88db29dba660.jpg)
](https://drive.google.com/file/d/1p9z9ol_wRNya5KrB0Y22x8pTH_wze8Jz/view?usp=sharing)
>> - 순서있는 목록 [![순서있는목록](https://user-images.githubusercontent.com/101074052/156951196-64f23ef8-f03f-4d33-a7dc-73ab593ce2ac.jpg)](https://drive.google.com/file/d/1dJUoPPPI52PsF3NWEyvduj23BlMEzz_6/view?usp=sharing)
>> - 인용 [![인용](https://user-images.githubusercontent.com/101074052/156951310-9559e2b3-0950-4342-9cd9-51457b513c86.jpg)](https://drive.google.com/file/d/1pxzaz-y6S1qNYM5XVr1HFQSj6O6cvYue/view?usp=sharing)  
>> - 헤더 [![헤더](https://user-images.githubusercontent.com/101074052/156951421-4b12da2d-fd46-4bc7-9212-cf9788954796.jpg)
](https://drive.google.com/file/d/1Dd0ROHs24TJIJ6ybCIW6PSavbSow64dI/view?usp=sharing)  
>> - 코드블럭 [![코드블럭](https://user-images.githubusercontent.com/101074052/156951483-5bcbaf94-e369-4d39-a6a8-20e9f23a6b73.jpg)
](https://drive.google.com/file/d/1yG8Vcxmp6BtLY239WAHK_fX7ZfQio8-J/view?usp=sharing)    
    **코드블럭은 ```다음  c,  python등 언어를 입력하면 해당언어의 코드로 변경한다.**


## :two: Markdown 실습(2023-09-14)
### :hash: 타이틀
###### 굵게6
##### 굵게5
#### 굵게4
### 굵게3
## 굵게2
# 굵게1


### :hash: 강조
**진하게**  
__밑줄__  
~~취소~~  
_기울임_  
*기울임*  
`인라인코드`  


### :hash: 줄 바꿈
문장
줄바꿈
안함  
문장  
줄바꿈  
함  
### :hash: 블럭(인용) 들여쓰기
> 들여쓰기 1단
>> 들여쓰기 2단
>> 
### :hash: Code Block
```pytyon
import something
a = 10
print(a)
if a>10:
print(a)
```
### :hash: 행렬
$$\begin{matrix} 
1&2\\
3&4\\ 
\end{matrix}$$

$$\begin{pmatrix}
1&2\\
3&4\\ 
\end{pmatrix}$$

$$\begin{bmatrix}
1&2\\
3&4\\ 
\end{bmatrix}$$

$$\begin{Bmatrix}
1&2\\
3&4\\ 
\end{Bmatrix}$$

$$\begin{vmatrix}
1&2\\
3&4\\ 
\end{vmatrix}$$

$$\begin{Vmatrix}
1&2\\
3&4\\ 
\end{Vmatrix}$$




---
### :hash: 수식 & 특수식
$$
\begin{aligned}
f(x)&=ax^2+bx+c\\
g(x)&=Ax^4
\end{aligned}
$$

문장내 $\frac{1+s}{s(s+2)}$ 삽입

$$\frac{1+s}{s(s+2)}$$

$\displaystyle\lim_{s\rightarrow\infty}{s^2}$
$\displaystyle\sum_{i=0}^{\infty}{(y_i-t_i)^2}$

---
### :hash: 이미지, 체크박스

![이미지설명문구](이미지주소)


* [ ] 비어있는 체크박스
* [x] 체크된 체크박스

### :hash: 하이퍼링크, 수평선, 표
#하이퍼링크
[바로가기](링크주소)  
<http://www.google.com>

### :hash: 수평선
***
---

### :hash: 표
| 1열 | 2열 | 3열 |
| --- | :---: | ---: |
|`바디1`|바디2| 바디3|
|`바디4`|바디5| 바디6|

### :hash: 목록

* 사과
* 오렌지
  + 딸기
  +자두
- 포도
- 바나나
1. 참외
2. 수박







## :three: 마무리  
이번 실습으로 Google colab의 Notebook과 Markdowm의 사용법을 익히고 알아보았습니다. 이러한 플랫폼이 기존 문서작성 플랫폼보다 문법이 쉽고 직관적이며 지원가능한 플랫폼과 프로그램이 많을뿐만 아니라 다양한 형태로 변환이 가능하기 때문에 점점 널리 사용되고 있는 이유를 알 수 있었습니다.  
:smile:
