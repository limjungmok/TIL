#**Scope의 이해**
유효범위는 어느 범위까지 참조하는지, 즉 변수와 매개변수의 접근성과 생존기간을 뜻한다.<br>
1. 전역 유효범위(Global Scope) : <b>script 전체</b>에서 참조된다.<br>
2. 지역 유효범위(Local Scope)  : <b>정의된 함수 안</b>에서만 참조된다.<br>

---

##**Lexical 특성**
렉시컬 특징은, 함수 실행시 유효범위를 <b>함수를 정의한 내부환경으로 제한</b>해서 참조하는 특성이다.<br>
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
<b>함수 내부의 지역변수 value의 선언</b>을 ####최상단으로 끌어올린다.<br>
하지만, <b>value의 선언</b> 자체만 끌어올리는것이지, 10이라는 초기화된 값을 끌어올리진 않는다.<br><br>

* 단, Hoisting 속성은 함수 선언문에서만 적용되는 특성이다.
ex)<br>  
* function A( ){ ... }          // <b>함수 선언문</b> 형태, Hoisting 가능
* var a = function( ){ ... }    // <b>함수 표현식</b> 형태, Hoisting 불가능
* var b = new Function( );      // <b>생성자</b> 형태, Hoisting 불가능
<br>

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

var value = 30;
function hoistingExam(){
    console.log("value = " + value);
    var value;
    console.log("value = " + value);
}
hoistingExam();  
// 실행결과(함수 선언을 호이스팅 하기때문에, 둘다 undefined 호출)

```
##**Scope Chain**
Closure개념과 같이 생각하자.<br>
유효범위 체인이란, 함수가 중첩함수일 경우 상위함수의 유효 Scope까지 흡수하는 것이다.<br>
즉, 하위함수(내부함수)가 실행되는 동안, 상위함수의 유효 Scope 내에 존재하는 변수 및 함수의 메모리를 참조하는 것이다.<br>

1. 전역 Scope에서 a와 outerFunction에 대한 유효 Scope가 생성되어있고, outerFunction을 호출한다.
2. 호출된 outerFunction의 경우, 전역함수 내에서 중첩되어있으므로 <b>내부 함수에서 부모/자식관계가 형성</b>된다.
3. outerFunction에서 innerFunction 을 리턴하므로, 부모/자식관계가 형성된다.
4. 가장 하위 innerFunction에서 형성된 부모/자식관계를 이용해 변수 a,b,c 모두에 대한 유효 Scope를 가지게 되고, 참조가 가능하다.

```javascript
var a = 10; // 전역 Scope

function outerFunction(){ // 전역 Scope
    var b = 20;               // outerFunction Scope

    function innerFunction(){ // outerFunction Scope
        var c = 30;               // innerFunction Scope
        console.log(a,b,c);       // innerFunction Scope
    }

    return innerFunction();   // outerFunction Scope
}

outerFunction();          // 전역 Scope
//실행결과
// 10 20 30
```
