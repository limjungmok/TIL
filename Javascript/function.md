#**함수**
> 함수란, '로직'을 재실행 할 수 있도록 코드의 재사용성을 높여준다
> function 함수명( [인자...[,인자]] ){
>   //코드
>   return 반환값
>}

<br>
---
</br>
```javascript
    // numbering 이라는 함수를 선언하고
    function numbering(){
        var i = 0;

        while(i<10){
            console.log(i + " ");
            i += 3;
        }
    }

    // 함수를 선언하고 numbering이라는 변수에 담는다.
    var numbering = function(){
        var i = 0;

        while(i<10){
            console.log(i + " ");
            i += 3;
        }
    }

    // 함수의 이름도 할당한 변수도 없이 정의+호출 동시에.
    // 이러한 함수를 '익명함수'라 한다.
    // 일회성 함수호출을 위해서 사용함
    (function(){
        var i = 0;

        while(i<10){
            console.log(i + " ");
            i += 3;
        }
    })();
```
