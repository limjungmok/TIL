#**Form Tag**
Post방식으로 서버에 값을 push(갱신)할 때 사용한다.


---

```javascript
<form action = “요청주소” method=“POST">
     ID : <input type =“text” name = “id">
     PWD : <input type = “password” name = “pwd">
     <input type = “submit”>
</form>
```


-> http:// naver.com ? <b>id</b>=aaa&<b>pwd</b>=1234

서버쪽에서는 각각의 이름으로 값이 전달된다.

params[:id] = aaa
params[:pwd] = 1234

Key 값을 이용해 input 태그의 value를 참조할 수 있다.
