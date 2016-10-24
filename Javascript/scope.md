#**Scope의 이해**
유효범위는 어느 범위까지 참조하는지, 즉 변수와 매개변수의 접근성과 생존기간을 뜻한다.<br>
1. 전역 유효범위(Global Scope) : <b>script 전체</b>에서 참조된다.<br>
2. 지역 유효범위(Local Scope)  : <b>정의된 함수 안</b>에서만 참조된다.<br>

---

##**Lexical 특성**
렉시컬 특징은, 함수 실행시 유효범위를 함수 정의 환경으로 참조하는 특성이다.<br>
밑의 코드를 보면, f2 함수가 f1 내부에서 호출된다고 해서, f1 의 지역변수 a를 참조할 수 있는건 아니다.<br>
렉시컬 특성으로 인해 f2 가 실행될 때 자신이 정의된 환경을 참조하기 때문에, a 변수를 찾을 수 없다.<br>

```javascript
function f1(){  
    var a= 10;
    f2();
}
function f2(){  
    return a; // f2 내부에는 지역변수 a가 선언되어있지 않아서 참조할 수 없다.
}

f1();

//실행결과
/*
Uncaught Reference Error  
: a is not defined
*/
```
##**Hoisting**
<b>변수의 선언문</b>을 끌어올린다는 뜻이다.<br>
Hoisting 속성때문에 함수 내에서 전역변수를 참조하지 않고,<br>
함수 내부의 지역변수 value의 선언을 최상단으로 끌어올린다.<br>
하지만, <b>value의 선언</b> 자체만 끌어올리는것이지, 10이라는 초기화된 값을 끌어올리진 않는다.<br><br>

* 단, Hoisting 속성은 함수 선언문에서만 적용되는 특성이다.
* ex)  function A( ){ ... }          // <b>함수 선언문</b> 형태, Hoisting 가능
*      var a = function( ){ ... }    // <b>함수 표현식</b> 형태, Hoisting 불가능
*      var b = new Function( );      // <b>생성자</b> 형태, Hoisting 불가능

```javascript
var value = 30;
function hoistingExam(){
    console.log("value = " + value);
    var value = 10;
    console.log("value = " + value);
}
hoistingExam();  

//실행결과(Hoisting 속성 때문에 30은 참조되지 않는다.)
/*
value= undefined  
value= 10  
*/
```
