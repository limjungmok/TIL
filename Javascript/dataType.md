#**숫자와 문자**
<br>
>데이터 숫자와 문자에 관한 연산에 대해 알아보자.

---
<br>
##**원시(기본) 데이터 타입**

숫자(기본 8bytes), 문자(열), true/false, null, undefined<br>
원시 데이터 타입변수는 '값'으로 접근하는데, <b>변수에 저장된 실제값</b>을 조작한다.

<br>
##**객체(참조) 데이터 타입**

'원시'데이터타입 제외한 나머지 모든 타입<br>
참조 데이터 타입이 접근하는 참조값은 <b>메모리에 저장된 객체</b>이다.

<br>

```javascript
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
```
<br>
---
<br>
##**매개변수의 값 전달**

매개변수는 무조건 '값'을 전달하는것이지, <b>절대 '참조'를 전달하지 않는다.</b><br>
매개변수로 전달되는 값이 원시/참조 값의 유무에 상관없이 무조건 '값'을 전달하는것이다.

```javascript

[원시타입의 매개변수 전달]
function addTen(num){
  num += 10;
  return num;
}
var count = 20;
var result = addTen(count); // count에 담겨있는 20이라는 단순한 '값'을 전달한다.
console.log(count);  // 20
console.log(result); // 30

[참조타입의 매개변수 전달 1]
function setName(obj){  // 사용자는 넘어온 obj 를 참조할것이라 생각하지만
  obj.name = "Nicolas"; // 단순히 person이 obj에 복사되어, 함수 내부에서 obj와 person이 같은 객체를 가리킨다.
                        // 결과적으로 매개변수는 값을 전달한것이지만, 참조를 통해 객체에 접근할수있다.
}
var person = new Object();
setName(person);
console.log(person.name); // Nicolas


[참조타입의 매개변수 전달 2]
function setName(obj){  
  obj.name = "Nicolas"; // 위와같이 값을 매개변수로 전달하였지만 obj에 참조객체가 복사되었다.
  obj = new Object();   // 함수 내부에서 obj에 새로운 객체를 참조하도록 시키고
  obj.name = "Greg";    // 여기서 person과 obj가 가리키는 참조객체가 달라졌다.
}

var person = new Object();
setName(person); //참조타입의 person 객체를 넘긴다.
console.log(person.name); // Nicolas

```
<br>
---
<br>
##**숫자**

JS에서는 따옴표(", ')가 붙어있지 않으면, 숫자로 취급한다.
<br>

```javascript
    alert(1+1);         // 2</br>
    alert(1.5+2.3);      // 3.8<br>
    Math.pow(3,2);       // 9,   3^2 제곱승<br>
    Math.round(10.6);    // 11,  10.6을 반올림<br>
    Math.ceil(10.2);     // 11,  10.2를 올림<br>
    Math.floor(10.6);    // 10,  10.6을 내림<br>
    Math.sqrt(9);        // 3,   3의 제곱근(루트 9)<br>
    Math.random();       // 0부터 1.0 사이의 랜덤한 숫자
```
<br>
---
<br>
##**문자**

JS에서 따옴표(", ')로 감싸진 문자열이면, 문자로 취급한다.
<br>

```javascript
    alert(typeof "1");                                // string<br>
    alert('egoing's javascript');                     // Error <br>
    alert('egoing\'s javascript');                    // 역슬래시('\')를 붙여줌으로써 사용가능<br>
    alert("안녕하세요.\n생활코딩의 세계에 오신 것을 환영합니다"); // 여러줄 가능<br>
    alert("coding"+" everybody");                     // coding everybody<br>
```

<br>
---
<br>

##**Reference**

생활코딩 : https://opentutorials.org/course/743/4647
