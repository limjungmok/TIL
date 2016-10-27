#**동등 연산자(==) Vs 일치 연산자(===)**
==  는 동등연산자로 좌항과 우항을 비교, 단순히 '값'이 같은지 판별<br>
=== 는 일치 연산자로 좌항과 우항을 비교, '정확'하게 같은 형식과 타입인지를 비교한다.<br>
=== 는 typeof 성질을 포함한다.<br>
<br>
```javascript
console.log(1 == "1");    //true
console.log(1 === "1");   //false

console.log(true == "1"); //true
console.log(true == 1);   //true
console.log(true === 1);  //false

console.log(0 === -0);    //true
console.log(NaN == NaN);  //false
console.log(NaN === NaN); //false NaN 의 경우 0/0 과 같은 연산으로 특수한 데이터 형태인데 숫자값이 아니라는 뜻이다

console.log(null == undefined);  //true  null의 경우 값이 없음을 명시적으로 표시한것이고  (빈 객체를 표현)
console.log(null === undefined); //false undefined의 경우 값이 없는 상태를 표현하는것이다(초기화되지 않은 변수)
```
<br>

####**Refer**
Tistory : http://devbox.tistory.com/entry/%EB%B9%84%EA%B5%90-%EC%99%80-%EC%9D%98-%EC%B0%A8%EC%9D%B4-1
