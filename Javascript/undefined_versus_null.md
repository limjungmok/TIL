#**Undefined**
> Undefined 타입은 값이 1개밖에 없다. 그냥 Undefined 하나.<br>
> '변수를 초기화하지 않았다'를 의미한다.<br>
<br>
```javascript
var check;
console.log(check);         // undefined
console.log(typeof check);  // undefined
console.log(unclared);      // Uncaught Reference Error
                            // 얘는 애초에 선언이 안돼있기 때문에 참조불가능 에러가 뜬다
```
<br>
----
<br>
#**Null**
> Null 타입은 원시자료형에 사용되고, 복합자료형과 오브젝트에만 쓰인다.
> Null 타입은 빈 객체를 가르키는 포인터이고
> undefined의 상위값이라 보면된다.
<br>
```javascript
var check = null;
console.log(check);             // null
console.log(typeof check);      // object
console.log(null == undefined); // true (Null 이 상위값이다.)
console.log(null === undefined);// false(완벽하게 같지 않다.)
```
<br>
####**Refer**
---

Tistory muckycode : https://muckycode.blogspot.kr/2015/01/javascript-undefined-null.html
