#**Apply vs Call**

함수에는 apply, call 두가지 메서드가 있고, 모두 소유자인 함수를 호출하며 this를 넘기는데<br>
결과적으로, 함수 내부에서 this 객체의 값을 바꾸는것이다.<br>
apply, call의 실행결과는 완벽하게 같다. 차이점은 매개변수를 호출하는 방법이 다르다는점.<br>
<b>apply와 call을 사용하면 객체에 메서드를 모두 등록할 필요가 없다.</b><br>
스코프를 다르게 해서 유연하게 메서드를 사용할 수 있다.
---
<br>

##**Apply**

apply의 경우, arguments 객체를 그대로 전달해도 되거나, 매개변수로 전달할 데이터가 이미 배열형태로 준비된 경우 사용<br>

```javascript

function sum(num1, num2){
    return num1+num2;
}

function callSum1(num1, num2){ // 매개변수를 arguments로 이용해서 연산
    return sum.apply(this, arguments);
}

function callSum2(num1, num2){ // 매개변수 데이터를 배열로 처리
    return sum.apply(this, [num1, num2]);
}

console.log(callSum1(10,10)); // 결과가 똑같다.
console.log(callSum2(10,10));

```

<br>
---
<br>
##**Call**

```javascript
function callSum(num1, num2){ // 위의 apply와 다른점은, call을 사용할 땐 반드시 매개변수를 각각 나열해야한다.
    return sum.call(this, num1, num2);
}

console.log(callSum(30,30)); //60

window.color = "red";
var o = {color:"blue"};

function sayColor(){
    console.log(this.color);
}

sayColor().call(this);  //red
sayColor().call(window);//red
sayColor().call(o);     //blue
```
