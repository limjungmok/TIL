#**큐**
선입 선출(First in First Out)의 메모리 구조.</br>
동적으로 메모리를 할당하며, 런타임 시점에 크기가 결정된다.</br>
한 쪽에서는 데이터의 입력만, 다른 한 쪽에서는 데이터의 출력만 가능하다.</br>

###**2. 소스코드**

```java
public class Queue {
    // 큐 배열은 front와 rear 그리고 maxSize를 가진다.
    private int front;
    private int rear;
    private int maxSize;
    private Object[] queueArray;

    // 큐 배열 생성
    public Queue(int maxSize){
        this.front = 0; //가장 오래전에 쌓인 데이터
        this.rear = -1;  //가장 최근에 쌓인 데이터
        this.maxSize = maxSize;
        this.queueArray = new Object[maxSize];
    }    

    // 큐가 비어있는지 확인
    public boolean empty(){
        return (front == rear+1);     
    }

    // 큐가 꽉 찼는지 확인
    public boolean full(){
        return (rear == maxSize-1);     // 내가 추가하려는 rear위치가 마지막인지 확인.
    }

    // 큐 rear에 데이터 등록
    public void push(Object item){
        if(full()){
               System.out.println(“꽉참”);          
          }
        queueArray[++rear] = item;     // -1에서부터 하나씩 올려가며 아이템을 추가해준다.
    }

    // 큐에서 front 데이터 조회
    public Object peek(){
        if(empty()){
               System.out.println(“텅빔”);
          }
        return queueArray[front];     //가장 오래전에 입력된 Front 조회
    }

    // 큐에서 front 데이터 제거
    public Object pop(){
        Object item = peek();     //가장 오래전에 입력된 Front 를 지워줘야한다.
        front++;                          // 0에있던거 지웠으니 1을 지울차례다~
        return item;
    }
}
```
