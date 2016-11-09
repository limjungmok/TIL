#**컴포넌트 매핑**
하위 컴포넌트에 상위 컴포넌트의 State를 매핑해야하는 경우가 있다.<br>
상위 컴포넌트의 State를 하위 컴포넌트에서 반복적으로 보여줄 경우,<br>
콜백함수를 이용해 컴포넌트 + props를 리턴하면 된다.<br>

```javascript
//하위 컴포넌트
class ContactInfo extends React.Component {

  render() {
    return (
      <div>{this.props.contactItem.name} {this.props.contactItem.phone}</div>
    );
  }
};

//상위 컴포넌트
class Contact extends React.Component {

  constructor(props){
    super(props);
    //상위컴포넌트에서 하위 컴포넌트로 보낼 배열 객체
    this.state = {
      contactData :
      [
        {name : 'A' , phone : '0'},
        {name : 'B' , phone : '2'},
        {name : 'C' , phone : '3'},
        {name : 'D' , phone : '4'}        
      ]
    };
  }

  render() {
    //렌더링 내부에서 콜백함수를 이용해 반환할 컴포넌트를 만든다.
    //첫번째 인자로 data가 들어가는데
    //data.map 에서의 매개변수인 contact는 contactData의 객체가 하나씩 담기는것이라 생각하자.
    //{name : 'A', phone : '0'} 부터 들어가고, i 는 연산되는 시점의 인덱스를 말한다.
    const mapStateToPropsForContactInfo = (data) =>{
      return data.map((contact, i) =>{
        return <ContactInfo contactItem = {contact} key = {i}/>
      });
    };

    return (
      <div>
        {mapStateToPropsForContactInfo(this.state.contactData)}
      </div>
    );
  }
};


class App extends React.Component {
  render() {
    return (
      <Contact/>
    );
  }
};

ReactDOM.render(
  <App></App>,
  document.getElementById("root")
);
```
