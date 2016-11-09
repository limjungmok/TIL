#**Chapter1**
> React는 자바스크립트와 (XML)을 이용해 조합형 UI 인터페이스를 구축하는 라이브러리(=엔진이라고도 불림)다.
> UI를 Component로 분리하는 개념을 사용, 재사용성을 높인다.




##**특징**

1. 편리한 **반응형 렌더링**
  - SPA는 사용자 상호작용 Data를 가져오고, **DOM 의 일부만** 업데이트한다.
  - **반응형 렌더링**을 통해 React는 데이터 변경을 감지, Virtual DOM을 이용한다.
  - React는 기존 UI 상태 vs 원하는 UI 상태를 비교,
  - 추상화한 Virtual DOM을 이용해 경량 처리(필요부분만 렌더링)한다.


2. 순수 자바스크립트를 이용한 **컴포넌트 기반** 개발
  - Component는 작게 유지, 서로 조합가능하며, 작은 Component를 이용해 복잡하게 만들수있다.
  - 기존 UI에 이용되던 HTML 언어가 아닌 'Javascript'만을 이용한다.
  - MarkUp, CSS, Javascript간의 분리를 Support.

3. 문서 모델의 유연한 추상화


```Javascript
//컴포넌트를 mapping 하면서 리턴할 때
var cards = this.props.cards.map((card, i) => {
        return <Card id = {card.id}
                    title = {card.title}
                    description = {card.description}
                    tasks = {card.tasks}
                    key = {i}
                    />
    });


//단순한 HTML 태그를 mapping 하면서 리턴할 때
let tasks = this.props.tasks.map((task, i) => (
        <li className="checklist__task" id={i}>
            <input type = "checkbox" defaultChecked = {task.done} />
            {task.name}
            <a href="#" className="checklist__task--remove"/>
        </li>
    ));


```
