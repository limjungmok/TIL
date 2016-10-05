#**React**

> UI를 Javascript의 Class를 이용해 컴포넌트로 분리하고
> 컴포넌트별로 조합해 VirtualDOM을 이용해 필요한 부분만 Rendering해주는 라이브러리(혹자는 엔진이라 말함)

---


####**Basic Architecture**

```Javascript
//컴포넌트를 만든다
class 컴포넌트명 extends React.Component{
  //React 컴포넌트 트리를 리턴, 최종적인 HTML을 그려줌
  render(){
    return(
      // 컴포넌트 내의 div는 실제 DOM 노드가 아니다.
      // Reaact div 컴포넌트의 인스턴스다.
      <div>
        Hello, World!
      </div>

    );
  }
}
//* React는 단방향 통신이기때문에, 순서가 중요하다.


// 최상위 컴포넌트의 인스턴스를 만든다.
// 두번째 매개변수로 전달받은 DOM 엘리먼트에 Markup을 삽입, 프레임워크를 시작한다.
ReactDOM.render(
  <(최상위로 지정할)컴포넌트></컴포넌트>,
  document.getElementById('root')
);
```
