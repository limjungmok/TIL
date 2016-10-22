#**Form Tag**
> Post방식으로 서버에 값을 push(갱신)할 때 사용한다.

```javascript
<form action = "요청주소" method="POST"/>
     ID : <input type ="text" name = "id"/>
     PWD : <input type = "password" name = "pwd"/>
     <input type="hidden" name="hide" value="hide_value"/>
     <input type = "submit"/>
</form>
```

-> http:// naver.com ? <b>id</b>=aaa&<b>pwd</b>=1234

서버쪽에서는 각각의 이름으로 값이 전달된다.

params[:id] = aaa
params[:pwd] = 1234

<b>Key 값</b>을 이용해 input <b>태그의 value</b>를 참조할 수 있다.

* 참고로 hidden type을 지정하면 UI 없이 value를 전달 할 수 있다.
