#**Canvas**

HTML 요소로, JS를 사용하여 그림을 그리는데 사용된다.<br>
(Canvas자체가 그래픽을 구현하는것이 아닌, 그래픽을 위한 영역을 만든다.)<br>
그래프, 사진합성, 간단한 애니메이션을 만드는데 사용된다.<br>
최근버전의 주요 브라우저들은 모두 지원하고있다.(IE9 부터 HTML5를 지원하고 개선중...)<br>
<br>
```HTML
//img 태그와 비슷하지만, src 와 alt속성을 갖지 않는다.
<canvas id="tutorial" width="150" height="150"/>

var canvas = document.getElementById('tutorial');

//지원여부를 확인할 수 있다.(체크)
if (canvas.getContext){
  var ctx = canvas.getContext('2d');
  // drawing code here
} else {
  // canvas-unsupported code here
}


```
