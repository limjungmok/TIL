#**삽입소트**
arr[1] 배열 인자를 시작으로, 한칸 앞의 인자들과 하나씩 비교해가며 자신보다 큰 숫자들을 바꾼다.<br>
for문을 2번 이용하기 때문에 수행시간은 O(N^2)<br>

###**1. 흐름**

초기값 </br>
5 2 4 3 1</br>
</br>

첫번째 반복</br>
2 5 4 3 1(2,5 비교)</br>
</br>

두 번째 반복</br>
2 4 5 3 1(5,4 비교)</br>
2 4 5 3 1(2,4 비교)</br>
</br>

세 번째 반복</br>
2 4 3 5 1(5,3 비교)</br>
2 3 4 5 1(4,3 비교)</br>
2 3 4 5 1(2,3 비교)</br>
</br>

네 번째 반복</br>
2 3 4 1 5(5,1 비교)</br>
2 3 1 4 5(4,1 비교)</br>
2 1 3 4 5(3,1 비교)</br>
1 2 3 4 5(2,1 비교)</br>
</br>

> 총 배열의 크기 -1 만큼 순회한다.</br>
> i 번째 순회때 비교 할 초기값 arr[i]을 Key 에 담아놓고, </br>
> 시작 인덱스의 바로 앞 배열인자와 버블소트 방식으로 역순으로 비교한다.</br>
<br>

###**2. 소스코드**
```c++
#include <iostream>
using namespace std;

int main(void){
    int arr[5] = {5, 2, 4, 3, 1};

    for(int i=1; i<5; i++){          // 초기 1번째 인덱스 값부터 자신의 앞에 모든 배열과 비교한다.
        int key = arr[i];            // 값 자체를 변수에 담아둔다.
        for(int j=i-1; j > -1; j--){ // 버블소트를 역순으로 하는 느낌
            if(arr[j] > key){        // Key 값보다 앞에있는 값이 크다면, 배열 순서를 바꾸어준다.
                arr[j+1] = arr[j];
                arr[j] = key;
            }
        }
    }

    for(int i=0; i<5; i++){
        cout<<arr[i]<<" ";
    }
    return 0;
}
```

```java

public class InsertSort {

	public static void Insert(int arr[]){
		int length = arr.length;

		for(int i = 1; i < length; i++){
			int key = arr[i];

			for(int j = i-1; j > -1; j--){
				if(arr[j] > key){
					arr[j+1] = arr[j];
					arr[j] = key;
				}
			}
		}
	}

	public static void main(String[] args) {

		int arr[] = {5,2,4,3,1};

		for(int i=0; i < arr.length; i++){
			System.out.print(arr[i]+" ");
		}
		System.out.println();

		Insert(arr);

		for(int i=0; i < arr.length; i++){
			System.out.print(arr[i]+" ");
		}
	}
}

```
