#**박스 모델링**
"페이지의 모든 엘리먼트는 사각형 박스이다."</br>
CSS는 표준 박스모델을 사용한다.</br>
각 박스는 4개의 경계가 있고, margin, border, padding, content가 존재한다.</br>

###**Box Modeling**
1. 박스는 엘리먼트의 width, height 속성을 정의함으로써 시작한다.
2. padding과 border가 차례대로 width, height를 둘러싼다.()
3. margin이 border를 둘러싼다.
* padding, border는 '박스의 실제 크기'에 포함된다.
* Content의 width : width + (padding * 2) + (border * 2)
* margin은 '박스의 실제 크기'에 포함되지 않는다.(영역의 넓이를 구할때는 margin * 2 를 또 더해주면된다.)



###**Content**
실제 내용을 포함하는 영역이다.</br>
배경, 이미지, 너비와 높이가 설정이 가능하다.</br>

###**Padding**
패딩은 Content의 연장으로 생각하면 쉽다.</br>
패딩을 둘러 싼 Border까지가 경계선이다.(border 내부에 있다.)</br>

###**Border**
보더 영역은 정의된 보더의 크기에 의존적이다.</br>
보더 내부는 padding의 확장된 영역을 포함한다.</br>

border : 6px solid #ccc; // width, style, color 순서대로다.
* 상대적인 값은 em, %
* 절대적인 값은 px, pt, inch, cm

###**Margin**
영역의 너비에는 포함이 되며, 엘리먼트 외부 여백을 의미힌다.</br>
실제로 padding, margin 을 0으로 초기화 해놓음으로써 CSS reset을 이용하는 경우가 있다.</br>

* margin: 20px;             // 상 하 좌 우 20px
* margin: 10px 20px;        // 상 하 10px , 좌 우 20px
* margin: 10px 20px 0 15px; // 상 10 하 0 좌 20 우 15


###**ETC**

해당 속성을 통해, 높이와 너비를 padding에 관계없이 맞출 수 있다.(하지만 뷰에서 밀리는건 어쩔수없음)</br>
아래와 같이 webkit 설정을 해주어야 하고, IE8+ 에서 가능.
```css
* {
  -webkit-box-sizing: border-box;
     -moz-box-sizing: border-box;
          box-sizing: border-box;
}
```

<br>
##**참고**

https://nolboo.kim/blog/2013/07/22/beginners-guide-to-html-and-css-3-slash-10/
http://ko.learnlayout.com/box-sizing.html
