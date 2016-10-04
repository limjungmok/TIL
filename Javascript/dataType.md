#**숫자와 문자**

>데이터 숫자와 문자에 관한 연산에 대해 알아보자.

---
##**숫자**

>JS에서는 따옴표(", ')가 붙어있지 않으면, 숫자로 취급한다.


`alert(1+1);         // 2
alert(1.5+2.3);      // 3.8
Math.pow(3,2);       // 9,   3^2 제곱승
Math.round(10.6);    // 11,  10.6을 반올림
Math.ceil(10.2);     // 11,  10.2를 올림
Math.floor(10.6);    // 10,  10.6을 내림
Math.sqrt(9);        // 3,   3의 제곱근(루트 9)
Math.random();       // 0부터 1.0 사이의 랜덤한 숫자`


---

##**문자**

>JS에서 따옴표(", ')로 감싸진 문자열이면, 문자로 취급한다.

`alert(typeof "1");                               // string
alert('egoing's javascript');                     // Error
alert('egoing\'s javascript');                    // 역슬래시('\')를 붙여줌으로써 사용가능
alert("안녕하세요.\n생활코딩의 세계에 오신 것을 환영합니다"); // 여러줄 가능
alert("coding"+" everybody");                     // coding everybody
`
