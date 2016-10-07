#**스택**

> 후입 선출의 구조.
> 가장 마지막 데이터의 위치에 대해서만 삽입/삭제가 발생한다.

--------

####**Stack.java**


```java
class Stack{
	private Integer[] stackArray;
	private int top;

	public Stack(){
		this.stackArray = new Integer[100];
		this.top = -1; //처음에 -1 부터 시작
	}

	void push(int data){
		this.stackArray[++top] = data; // +1을 선수행 후 데이터 추가
	}

	boolean empty(){
		if(this.top == -1){
			return true;   // 스택이 비어있다.True
		}else{
			return false;  // 스택이 비어있지 않다.False
		}
	}

	int peek(){
		if(empty()){
			return -1;
		}else{
			return this.stackArray[this.top];
		}
	}

	int pop(){
		if(empty()){
			return -1;
		}else{
			int data = peek();
			this.top--;
			return data;
		}
	}

	int size(){
		return this.top+1;
	}
}
```
