#**Props**
</br>
> 컴포넌트간 정적 데이터를 넘겨줄때 사용한다.<br>
> {this.props.정적데이터이름} <br>
> {this.props.children} <br>
</br>
> 각 컴포넌트는 모두 'children' props를 소유하고있고,
> 컴포넌트를 호출하는 <컴포넌트>블럭사이의 값</컴포넌트>
> '컴포넌트 블럭' 사이의 값이 children으로 호출된다.


---------

####**props.컴포넌트명**
</br>
> 해당 예제는 App 컴포넌트를 렌더링해주는데, Codelab 컴포넌트를 App 컴포넌트 내에서 호출한다.<br>
> 즉, <App></App> 컴포넌트를 ReactDOM에 렌더링 해주는데,</br>
> HTML에서 속성태그를 넣듯이 해당 컴포넌트에 props 이름을 지정해서 넘겨주는거다.</br>
> 그렇게되면 App 컴포넌트는 정적인 props.render_name 을 받고,</br>
> App 컴포넌트가 Codelab을 렌더링하면서 동시에 name이라는 props에 자신이 받은 render_name을 넘겨준다.</br>
> 가장 하위 Codelab 컴포넌트에서는 App 컴포넌트를 생성하며 전달한 정적 props를 최종으로 넘겨받고,</br>
> JSX 문법을 이용해서 immunable한 값을 렌더링해주는것이다.</br>

> cf) props.children의 경우, 모든 컴포넌트가 갖고있는 프로퍼티값이라 생각하면 쉽다.</br>
> 해당 children 값은 블록 사이의 텍스트를 넘겨받아, 하위 컴포넌트의 JSX 문법 내에서 렌더링해준다.

</br>
```javascript
//JSX형태의 컴포넌트다
class Codelab extends React.Component{
  //모든 컴포넌트가 뭘 보여줄지 render해주는거
  render(){
    return(
      <div>
        <h1>Hello {this.props.name}</h1>
        <div>{this.props.children}</div>
      </div>
    )    
  }
}
//상위 컴포넌트를 하위에서 받아서 사용할수있다.
class App extends React.Component{
 render(){
   return(
    <Codelab name={this.props.render_name}>{this.props.children}</Codelab>
   );
 }
}
//첫번째 인수는 JSX형태의 콤포넌트, 두번째는 이 컴포넌트를 렌더링 해 줄 장소
ReactDOM.render(<App render_name="World">칠드런은 다들고있어요</App>, document.getElementById('root'));
```

-------------

####**Component.defaultProps**
</br>
> props로 넘겨받을 기본값을 셋팅해준다.

</br>

```javascript
App.propTypes = {
  render_name : React.PropTypes.string.(isRequired) // 이건 선택값
};

```

</br>
--------------

####**Refer**
</br>
>React Props Offical Doc : https://facebook.github.io/react/docs/reusable-components-ko-KR.html
