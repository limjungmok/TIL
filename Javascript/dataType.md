#**숫자와 문자**
<br>
>데이터 숫자와 문자에 관한 연산에 대해 알아보자.

---
<br>
##**원시(기본) 데이터 타입**

숫자, 문자(열), true/false, null, undefined

<br>
##**객체(참조) 데이터 타입**

'원시'데이터타입 제외한 나머지 모든 타입


<br>
> 문자열에서, var str = "coding";을 선언하고</br>
> str.length; 를 호출하면 6이 리턴된다.</br>
> 접근자를 이용할수있는 선언은 모두 '객체'라고 알고있다.</br>
> 하지만, 결론부터 말하면 문자열은 객체타입은 아니다.

> var str = new String("coding"); 과 같은 설정이 내부적으로 돌아가고</br>
> 사용이 끝난 직후(str.length 호출 후) 객체성질을 소멸시킨다.

> var str = "coding";</br>
> str.prop = "everybody"; //이 순간에는 객체로 취급되어 에러가 발생하지 않지만</br>
> console.log(str.prop); // undefined가 리턴된다.</br>

> JS에서는 문자열과 관련해 필요한 기능을 객체지향적으로 제공해야할 필요가 있다.</br>
> 그렇기때문에 Wrapper Object 객체가 원시 데이터 타입을 감싸고 있으며,</br>
> 객체처럼 다루는것을 자동으로 처리하며 지원한다.(내부적으로, 즉 몰라도 됌)

> 필요에 따라서 원시 데이터타입에 Wrapper 객체가 존재하는데,</br>
> 숫자     -> Number</br>
> 문자     -> String</br>
> T/F     -> Boolean</br>
> null, undefined 는 없다.
<br>
</br>

##**숫자**

>JS에서는 따옴표(", ')가 붙어있지 않으면, 숫자로 취급한다.
<br>
    alert(1+1);         // 2</br>
    alert(1.5+2.3);      // 3.8<br>
    Math.pow(3,2);       // 9,   3^2 제곱승<br>
    Math.round(10.6);    // 11,  10.6을 반올림<br>
    Math.ceil(10.2);     // 11,  10.2를 올림<br>
    Math.floor(10.6);    // 10,  10.6을 내림<br>
    Math.sqrt(9);        // 3,   3의 제곱근(루트 9)<br>
    Math.random();       // 0부터 1.0 사이의 랜덤한 숫자

---
<br>
##**문자**

>JS에서 따옴표(", ')로 감싸진 문자열이면, 문자로 취급한다.
<br>
    alert(typeof "1");                               // string<br>
    alert('egoing's javascript');                     // Error<br>
    alert('egoing\'s javascript');                    // 역슬래시('\')를 붙여줌으로써 사용가능<br>
    alert("안녕하세요.\n생활코딩의 세계에 오신 것을 환영합니다"); // 여러줄 가능<br>
    alert("coding"+" everybody");                     // coding everybody<br>
