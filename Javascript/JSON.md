#**강좌 5편. 컴포넌트의 State와 Props**
> Key - Vaue 쌍으로 이루어진 데이터 Object를 전달하기 위해 인간이 읽을 수 있는 텍스트를 사용하는 개방형 표준 포맷<br>
> [ ] : 배열<br>
> { } : 객체<br>
> JSON.stringify(Object) 를 이용해 <b>배열 -> JSON 문자열</b>로 변환<br>
> 단순한 문자열 객체를 Json 형태의 문자열로 변환해 사용한다.
> JSON.parse(JsonText)   를 이용해 <b>JSON 문자열 -> JSON Object</b>로 변환<br>
> Json 문자열을 parse 함으로써 객체처럼 자유롭게 사용할 수 있다.
---

```javascript

var arr = ['a','b','c'];            // typeof arr      : Object
var json_str = JSON.stringify(arr); // typeof json_str : string
var json_obj = JSON.parse(json_str) // typeof json_obj : Object

```

---

####Refer

MDN : https://msdn.microsoft.com/ko-kr/library/cc836466(v=vs.94).aspx
