#**This**
Scope와, 호출자가 누구인지에 따라 값이 결정된다.<br>
자바스크립트에서는 global 객체가 존재하며, 브라우저에서 window 객체가 그 역할을 하고있다.<br>
기본적으로 this는 global 객체이고, function영역 내부에서 this는 부모 객체를 나타낸다.<br>
<br>
```javascript
function Person(name, age) {
    this.name = name; // 함수 내부에서 this는 부모객체인 Person을 가리킨다.
    this.age = age;
}

var jeongmok = new Person('임정목', 26); // 생성자를 이용해 객체를 생성하면, 내부 this는 jeongmok 객체를 가리킨다.
                                       // new 연산자를 이용해 생성된 객체영역의 this는 객체 자신이다.
console.log(jeongmok.name);            // 임정목
console.log(jeongmok.age);             // 26

Person.prototype.isYoung = function(){ // 프로토타입을 이용해 this를 사용할때에도,
    return this.age < 25;              // this는 Person 형태로 만들어진 객체 자신을 가리킨다.
}

console.log(jeongmok.isYoung()); // false


** 생성자를 이용한 객체 생성과, 단순 함수를 이용한 변수 선언의 차이

var jeongmok2 = Person('정목',26);// 함수호출에서 this가 있는데, 이놈이 곧 전역객체를 가리킨다.

console.log(jeongmok2);         // Person 함수는 리턴하는 값이 없기때문에 undefined가 호출된다
//console.log(jeongmok2.name);  // 오류가난다 단순한 함수가 만들어진것이고
console.log(name);              // name, age 값은 현재 Global 변수가 된것이다.
console.log(age);               // 각각 '정목', 26이 호출된다.

age = 30;                       // Global 변수인 age의 값을 변화시키면
console.log(age);               // 30으로 출력된다

```

<br>
####**Refer**
---

Tistory RESONEIT   : http://resoneit.blogspot.kr/2014/01/this.html <br>
github.io hyunseob : https://hyunseob.github.io/2016/03/10/javascript-this/
