#**JS 5가지 배열 메소드**

<br>
##**IndexOf**

```javascript
var isExist = false;
for(var i =0; i< array.length; i++){
  if(array[i] === "특정한 값"){
    isExist = true;
  }
}

var isExist = (array.indexOf("특정값") !== -1);

한줄로 바꿀수있다.

```
<br>
##**Filter**
콜백함수에 지정된 조건을 충족하는 배열의 요소를 반환한다.<br>

filter(callback)<br>
- arr.filter(callback[args]) 형태
- 배열에 조건을 주고, 만족하지 못하는 원소들을 걸러낸다.

```javascript
function isTenUp(value){
  return value > 10;
}

var filtered = [11,3,9,130,44].filter(isTenUp);

filtered = [11, 130, 44]
```

##**Map**
파라메타로 전달된 함수를 통해, 각 배열 내부요소를 처리하고 새로운 배열을 반환한다.<br>

```javascript
var numbers=[1,2,3,4,5];

var processed = numbers.map(function(num){
  return num * num;
});

//Arrow Function 사용한 예제
var processed = numbers.map((num) =>{
  return num * num;
})
```
