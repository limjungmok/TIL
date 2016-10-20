#**강좌 5편. 컴포넌트의 State와 Props**
> Props는 컴포넌트에서 사용할 데이터 중, 변동되지 않을 데이터를 처리할때 사용한다.<br>
> 상위 컴포넌트에서 하위 컴포넌트를 호출할때 props를 이용해 데이터를 전달한다.<br>
<br>
> State는 변동이 가능한 데이터를 처리할 때 사용한다.<br>
> State를 사용하는 컴포넌트의 갯수를 최소화 하는것이 중요하고, 최대한 container 컴포넌트에서 바꾸는게 효율적이다.
> Props를 이용해 하위컴포넌트에서 상위컴포넌트의 바인딩된 함수를 받아서 실행해준다.<br>

---

```javascript
[App.js]
import React from 'react';
import Contact from './Contact';
import RandomNumber from './RandomNumber';

class App extends React.Component {
    constructor(props){
      super(props);

      this.state = {
        value : Math.round(Math.random() * 100)
      };
      this._updateValue = this._updateValue.bind(this);
    }

    // state 변경을 위한 함수
    _updateValue(randomValue){
      this.setState({
        value : randomValue
      });
    }

    render(){
        return (
            // props로 number, onUpdate 2개를 넘긴다.
            // number로 넘긴 props는 추후 변동이 예상되므로 state를 이용하는것이고
            // onUpdate로 넘긴 props에서는 값을 업데이트할 바인딩된 함수를 넘긴다.
            <RandomNumber number = {this.state.value}
                          onUpdate = {this._updateValue}/>
        );
    }
}
export default App;
```

```javascript
[RandomNumber.js]
import React from 'react';

export default class RandomNumber extends React.Component{
  constructor(props){
    super(props);

    this._update = this._update.bind(this);//onClick 핸들러를 위해 이벤트객체 바인딩
  }

  _update(){
    let value = Math.round(Math.random()*100); // 새롭게 랜덤 숫자를 생성해서
    // App 컴포넌트에서 바인딩해놓은 onUpdate라는 함수를 props로 받으면서, 동시에 매개변수를 이용해 호출한다.
    // 즉, 컴포넌트가 중복될때 상위 container 컴포넌트에서 setState를 실행하고,(값의 실질적 처리는 루트에서)
    // 단순히 자식 컴포넌트들은 props로 함수를 받아서 호출만 한다.
    this.props.onUpdate(value);
  }

  render(){
    return(
        <div>
          <h1>RANDOM NUMBER : {this.props.number} </h1>
          <button onClick = {this._update}>Click</button>
        </div>
    );
  }
}


```

---

####Refer

Velopert [React.JS] 강좌 5 : https://velopert.com/921
