#**스택**
후입 선출(First in Last Out)의 메모리 구조.</br>
함수 호출시 생성되는 지역변수, 매개변수가 저장되는 영역이다.</br>
함수 호출이 완료되면 사라지고, 컴파일 시점에 크기가 결정된다.</br>
들어오고, 나가는 역할을 한쪽에서만 수행한다.</br>

###**2. 소스코드**

```java
public class Stack {
    private int top;
    private int maxSize;
    private Object[] stackArray;

    // 배열 스택 생성,  스택의 최대 크기로 생성
    public Stack(int maxSize){
        this.maxSize = maxSize;
        this.stackArray = new Object[maxSize];
        this.top = -1;
    }

    // 스택이 비어있는지 체크
    public boolean empty(){
        return (top == -1);
    }

    // 스택이 꽉찼는지 체크
    public boolean full(){
        return (top == maxSize-1);
    }

    // 스택에 item 입력
    public void push(Object item){
        if(full()){
               System.out.println(“꽉참”);
          }
        stackArray[++top] = item;
    }

    // 스택의 가장 위의 데이터 반환
    public Object peek(){
        if(empty()){
               System.out.println(“텅빔”);
          }
        return stackArray[top];
    }

    // 스택의 가장 위의 데이터 제거
    public Object pop(){
        Object item = peek();
        top--;        
        return item;
    }
}
```
