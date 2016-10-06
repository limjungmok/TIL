#**State**
> 컴포넌트간 동적 데이터를 이용할 때 사용한다<br>
> {this.state.stateName} <br>
> 초기값 설정이 필수이므로, constructor에 this.state = { stateName : 값 }선언해주고,<br>
> 값을 수정할 때는 this.setState({ stateName : 값 }) 이용해 수정할 수 있다.<br>
> 단, 값을 수정하는건 렌더링이 된 이후에 수정이 가능하다.(콜백함수를 통해)<br>
> 즉 constructor는 렌더링 위에 선언하는 것이기때문에, 생성자 내에서 setState 할수없다.
> props나 state 에 접근하기위해 super() 상속을 통해 권한을 React 컴포넌트로부터 인계받는다.<br>

> **React 애플리케이션 개발시, state 사용 컴포넌트를 최소화시켜야한다.**<br>
> ####*Why?* 10개의 컴포넌트에서 state를 사용하는것보다, 각각의 정적 props를 사용하는게 효율적이다.

-----------
<br>
###**State 코드**

```Javascript
//state는 초기값 설정이 필수다
class Counter extends React.Component {
  constructor(props){ // 이 props는 Counter 컴포넌트가 만들어질 때, 전달받을 props
    super(props);     // 상속받은 리액트 컴포넌트. parent의 생성자 메서드를 먼저 실행한다.
                      // super를 통해 상속을 받아야 해당 컴포넌트에서 state, props에 접근할수있다.
    this.state = {
      value : 0
    };

    this.handleClick = this.handleClick.bind(this);
    // 밑에 button onClick 핸들러와 handleClick 메서드를 바인딩해준다.
  }
  
  // 버튼클릭시 호출할 핸들러 메서드
  handleClick(){
    this.setState({
      value:this.state.value + 1
    });
  }

  render() {
    return (
      <div>
        <h2>{this.state.value}</h2> /* state를 렌더링할 때 */
        <button onClick={this.handleClick}>Press Me!</button>
        /* button에 onClick 이벤트와 핸들러를 생성자에서 바인딩해주고 있다.*/
        /* 리엑트 이벤트시스템은, JS 네이티브 이벤트와 같은 인터페이스를 갖고있다.*/
      </div>
    );
  }
};

class App extends React.Component {
  render() {
    return (
      <Counter/>
    );
  }
};

ReactDOM.render(
  <App></App>,
  document.getElementById("root")
);
```
