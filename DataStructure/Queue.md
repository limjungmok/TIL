#**스택**

> 선입 선출의 구조.<br>
> 한 쪽에서는 데이터의 입력만, 반대편에서는 데이터의 삭제만 발생한다.<br>

--------

```java
class Queue{
	private Integer[] queueArray;
	private int begin;
	private int end;

	public Queue(){
		this.queueArray = new Integer[100];
		this.begin = 0;
		this.end = 0;
	}

	void push(int data){
		this.queueArray[end] = data;
		end++;
	}

	boolean empty(){
		if(this.begin == this.end){
			return true;
		}else{
			return false;
		}
	}

	int getBegin(){
		if(empty()){
			return -1;
		}else{
			return this.queueArray[begin];
		}
	}

	int getEnd(){
		if(empty()){
			return -1;
		}else{
			return this.queueArray[end-1]; //매우중요. 왜냐면 push를 수행하고나서 +1 해주기때문에
		}
	}

	int pop(){
		if(empty()){
			return -1;
		}else{
			int data = getBegin();
			this.begin++;
			return data;
		}
	}

	int size(){
		return (this.end - this.begin);
	}

}
```
