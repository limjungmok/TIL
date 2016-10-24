#**Context**
Context란, 즉 실행 정보를 담고있는 객체입니다.<br>
Javascript는 일종의 Call Stack 에 Context 를 담고, 제일 위에 쌓인 Stack이 현재 실행 Context가 되는 것이다.<br>

* 스택에 쌓이는 순서 : 전역 컨텍스트 -> Func2 -> Func1 -> Func1 삭제 -> Func2 삭제
```javascript
console.log("전역 컨텍스트 입니다");

function Func1(){
    console.log("첫 번째 함수입니다.");
};

function Func2(){
    Func1();
    console.log("두 번째 함수입니다.");
};

Func2();

//실행결과
/*
 전역 컨텍스트 입니다
 첫 번째 함수 입니다.
 두 번째 함수 입니다
 */
```

<br>
##**Context 생성**
1. 활성화 객체 : 실행에 필요한 여러 정보들을 담을 객체. (arg, 변수)
2. 유효범위 정보 : 현재 Context의 유효 Scope 를 나타낸다.
3. this 객체 : 현재 Context를 포함하는 객체.

 
