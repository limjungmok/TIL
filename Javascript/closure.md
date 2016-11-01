#**클로저**
외부함수 내에서 선언된 내부함수는, 외부함수의 Context 에 접근할 수 있는 특징을 가진다.<br>
외부함수의 실행이 끝나서 외부함수가 사라지는 시점에도, 내부함수는 외부함수의 변수에 접근할 수 있다.<br>

```javascript

function outer(){          // 외부함수
    var title = 'Hello world';

    function inner(){      // 내부함수
        console.log(title);// 외부함수 내의 지역변수에 접근할수있다.
    }
    inner();
}
outer();
```
<br>

```javascript

function outer(){
    var title = 'Hello world';

    return function(){
        console.log(title);
    }

}

inner = outer(); // outer 함수의 내부함수인 function이 inner에 담긴다.
inner();         // 내부함수에서 title을 호출하는데, 이시점에서는 outer 함수는 소멸되었고
                 // title을 참조하지 못한다고 생각하겠지만 클로저 매커니즘은 이를 지원한다.
                 // 즉, 외부함수의 지역변수를 사용하는 내부함수가 있을경우
                 // 내부함수가 소멸될 때 까지 외부함수가 살아있는 특징이 있다는걸 알수있다.

```
