#**Filter**
> 배열 내 요소에 대해서, Callback 함수를 호출해 해당하는 값을 가지고 새로운 배열을 생성<br>

---

```javascript
var arr = [12, 5, 8, 130, 44];// 값이 변하지않는다.

filtered = arr.filter(function(value){//콜백함수를 호출해준다.
  return value >= 10;
});
// filtered 는 [12, 130, 44]

```

---

####Refer

MDN : https://developer.mozilla.org/ko/docs/Web/JavaScript/Reference/Global_Objects/Array/filter
