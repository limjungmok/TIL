#**변수**
ES5의 var, ES6의 const, let 을 비교해보자<br>

##**var**
ES5 버전의 변수 선언이다. 초기화를 하지 않으면 기본 undefined.<br>
* Function Scope
* Hoisting 지원
* 중복으로 선언 가능
<br>
```javascript

function foo() {    // foo
  var x = 1;
  console.log(x);   // 1
  if(true) {        // JS5에서 if 블록은 무시된다.
    var x = 2;
    console.log(x); // 2
  }
  console.log(x);   // 2
}

foo();
```
<br>
##**let**
ES6 버전의 변수 선언이다.
* Block Scope
* Hoisting 불가능
* 중복으로 선언 불가능
<br>
```javascript

function foo() {    // foo
  let x = 1;
  console.log(x);   // 1
  if(true) {        // JS6 에서 if 블록은 Block처리되어, x 는 지역변수이다.
    let x = 2;
    console.log(x); // 2
  }
  console.log(x);   // 1
}

foo();
```
<br>
##**const**
ES6 버전의 상수를 담는 변수 선언이다.<br>
원시형 데이터 타입으로 쓰일경우 '상수'로 쓰인다.<br>
(string, integer, boolean, null, undefined)<br>
즉, const 선언된 변수는 재할당시 에러가 발생한다.<br>
<b>단. 참조형은 const로 선언하고, 내부 인자들은 변경이 가능하다.</b><br>
```javascript
const foo1 = 0;
foo1 = 1; // 에러 발생

const foo2 = [0, 1];
const bar = foo2;

foo2.push(2);
bar[0] = 10;

console.log(foo2, bar)
// [10, 1, 2] [10, 1, 2]
```
