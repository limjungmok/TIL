#**Document Object Model(DOM)**
HTML과 XML 문서에 대한 API이며,<br>
DOM은 문서를 '노드의 계층 구조 Tree' 형태로 표현하며<br>
개발자는 DOM API를 통해 노드를 조작할 수 있다.<br>
IE, Chrome, Safari, FireFox, Opera 는 최신 DOM 을 구현했다.<br>


###**Node 타입**

nodeName, nodeValue, nodeType 프로퍼티를 통해 노드의 정보를 제공한다.<br>


###**Document**

자바스크립트는 문서 Node를 Document 타입으로 표현한다.(노드계층 구조의 Root)<br>
Document 객체는 window의 프로퍼티이며, 전역에서 접근가능하다.<br>
브라우저 내의 모든 HTML 페이지는 HTMLDocuemnt의 인스턴스이고,<br>
HTMLDocument 는 Document를 상속한다.<br>

보통 DOM 관련해서 자주 하는일은 '특정 요소, 그룹'에 대한 참조를 얻는 일이다.<br>
getElementById(객체 하나), getElementsByTagName(객체 그룹)을 통해 기능을 제공한다.<br>
(id속성과 대소문자 구분하여 완벽하게 일치해야한다.)<br>

<br>
```javascript
<div id="myDiv">Some text</div>

var div = document.getElementById("myDiv");
//div에 대한 참조를 가져온다.

<img src="1.jpg" name="myImage">
<img src="2.jpg">
<img src="3.jpg">

var images = document.getElementsByTagName("img");
// img 객체의 집합을 구성하는 HTMLCollection을 반환한다.
var myImage = images["myImage"];
// 원하는 index의 key값을 통해 value 접근 가능
```
<br>
