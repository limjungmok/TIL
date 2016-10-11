#**이벤트**

> 자바스크립트와 HTML의 상호작용은, 브라우저에서 일어나는 '이벤트'에 의해 처리된다.<br>
> 옵저버 패턴이라 불리는 이벤트는 '리스너'로 추적되고 이벤트가 발생될때만 실행한다.<br>

----
<br>


###**1. 이벤트 버블링**

> 이벤트 흐름상 문서 트리에서 가장 깊은 요소까지 거품이 거슬러 올라가는 느낌이다.<br>
> 아래 예제의 실행순서는<br>
> 1. div<br>
> 2. body<br>
> 3. html<br>
> 4. document<br>
> click 이벤트는 document객체를 만날때까지, DOM 트리를 거슬러 올라간다.<br>
> **IE9, FireFox, Chrome, Safari는 window 객체까지 올라간다.**<br>

<br>

```javascript
<!DOCTYPE html>
<html>
  <body>
    <div id="myDiv">Click Me</div>
  </body>
</html>
```

-----
<br>

###**2. 이벤트 핸들러**

> 이벤트에 응답하여, #####'호출되는 함수 = 이벤트 핸들러(리스너)'라고 한다.<br>
> 즉, click 이벤트의 이벤트 핸들러는 onclick<br>
> load 이벤트의 핸들러는 onload이다.<br>
> 이벤트 핸들러로 실행하는 코드는 전역 스코프에서 실행된다.<br>


```javascript

####DOM 레벨 0 이벤트 핸들러
var btn = document.getElementById("myDiv"); //버튼에 대한 참조를 얻고<br>
btn.onClick = function(){
  alert(this.id);                           // 버블링에 따라 myDiv를 호출한다.
};
btn.onClick = null;                         // click이벤트의 핸들러인 onClick 리스너를 제거한다.

//
####DOM 레벨 2 이벤트 핸들러
btn.addEventListener("click", function(){ // click 이벤트에 핸들러를 추가해줄수있다.(중복추가가능))
  alert(this.id);
}, false);                                //버블링 단계에서 마지막 매개변수 false
btn.addEventListener("click", function(){ // 밑에있는애가 나중에 호출된다.(IE와 반대)
  alert("Hello World!");
}, false);

//
var handler_example = function(){                         //이벤트 핸들러를 하나 만들고
  alert(this.id);
};
btn.addEventListener("click", handler_example, false);    // 핸들러 객체를 추가를 해준다면,
btn.removeEventListener("click", handler_example, false); // 똑같은 핸들러를 삭제해준다.

//
####IE 이벤트 핸들러
** IE에서는 attachEvent, detachEvent 메서드를 구현해놨다. 사용법은 addEvent, removeEvent와 같다.
** 여기서 주의할점은, attachEvent로 설정한 핸들러는 나중에 정의된게 먼저 호출되고
** addEvent로 설정한 핸들러는 처음 정의된게 먼저 호출된다.
```
