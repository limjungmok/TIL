#**Sort**
> 정렬을 해주는 JS 함수, 유니코드를 기준으로 한다.<br>
> 숫자를 비교하고 싶다면, 매개변수로 compareFunction 콜백함수를 넘겨야한다.<br>
> array.sort(compareFunction)<br>

---

```javascript
var numbers = [4,5,2,3,1];

// sort의 매개변수로 콜백함수를 호출하고, 내부적으로 음수의경우 b가 작다고 판단한다.
numbers.sort(function(a,b){
  return a - b;
});
// [1,2,3,4,5] 출력된다. (오름차순)

// sort의 매개변수로 콜백함수를 호출하고, 내부적으로 음수의경우 a가 작다고 판단한다.
numbers.sort(function(a,b){
  return b - a;
});
// [5,4,3,2,1] 출력된다. (내림차순)

```

####Refer

MDN : https://msdn.microsoft.com/ko-kr/library/4b4fbfhk(v=vs.94).aspx
