#**JSX**
> React에서는 일반적인 Javascript 문법이 아닌 JSX를 사용한다.</br>
> JSX문법을 이용해 컴포넌트에 UI를 렌더링한다.</br>

> JSX는 컴파일 되면서 최적화 -> 빠르다.</br>
> Type-safe 하며 컴파일과정에서 에러감지 가능.
> (아무 연산결과를 보이지 않는것)

---
<br>

####**App.js**
---
```javascript
//JSX형태의 컴포넌트다
class Codelab extends React.Component{
  //모든 컴포넌트가 뭘 보여줄지 render해주는거
  sayHi(){
      alert('hi!');
   }

  render(){
    let text = "Hello";
    //JSX 안에서 Javascript를 표현할 때는 {}로 감싸주면된다.

    return(
      //여러 엘리먼트를 렌더링할 때,
      //반드시 container Element로 감싸줘라(div)를 썻지여기선.
      <div>
        <p>{text} Codelab!</p>
        <button onClick={this.sayHi}>Click!</button>
        {/* JSX 내의 주석은 이렇게 사용하고, if-else 구문 사용할수없다. */}
        <p>{1 === 1 ? 'yes' : 'false'}</p>
      </div>
    )    
  }
}
//상위 컴포넌트를 하위에서 받아서 사용할수있다.
class App extends React.Component{
 render(){
   return(
    <Codelab/>
   );
 }
}
//첫번째 인수는 JSX형태의 콤포넌트, 두번째는 이 컴포넌트를 렌더링 해 줄 장소
ReactDOM.render(<App/>, document.getElementById('root'));
```

</br>

####**index.html**
---
```
<div id="root"></div>
```
</br>


####**Refer**
---

인프런 JSX : https://velopert.com/867
