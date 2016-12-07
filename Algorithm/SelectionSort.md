#**선택 정렬**

0번째 배열을 최소값으로 설정 한 뒤, 뒤에 따라오는 모든 배열과 비교를 시작한다.</br>
자신보다 작은 배열값을 만날 때 마다 최소값을 갱신하고,</br>
다음 순서로 넘어가기 전에 루프를 시작했던 인덱스와 최소값 인덱스를 swap 한다.</br>
for문을 2번 이용하기 때문에 수행시간은 O(N^2)<br>
* 단, 이미 정렬이 되어있는 배열의 경우 한 번씩밖에 비교하지 않기때문에 수행시간 O(N)<br>


###**1. 흐름**

초기값 </br>
5 2 4 3 1</br>
</br>

첫번째 반복</br>
5 2 4 3 1 - 최소값 2</br>
5 2 4 3 1 - 최소값 2</br>
5 2 4 3 1 - 최소값 2</br>
5 2 4 3 1 - 최소값 1</br>
1 2 4 3 5
</br>

두 번째 반복</br>
1 2 4 3 5 - 최소값 4</br>
1 2 4 3 5 - 최소값 3</br>
1 2 4 3 5 - 최소값 3</br>
1 2 3 4 5
</br>

세 번째 반복</br>
1 2 3 4 5 - 최소값 4</br>
1 2 3 4 5
</br>

네 번째 반복</br>
1 2 3 4 5 - 최소값 5</br>
1 2 3 4 5
</br>

> 반복을 총 배열의 크기만큼 회전한다.</br>
> 한 번 반복할 때 마다 내부에서 배열을 모두 검사하고,</br>
> 최소값을 갱신 해 나간다.
<br>

###**2. 소스코드**
```c++
#include <iostream>
using namespace std;

void swap(int * a, int * b){
    int temp;
    temp = * a;
    * a = * b;
    * b = temp;
}

int main(void){
    int arr[5] = {5, 2, 4, 3, 1};

    for(int i = 0 ; i < 5 ; i++){
        int min = i;
        for(int j = i+1 ; j< 5; j++){
            if(arr[min] > arr[j]){
                min = j;
            }
        }
        swap(arr[i], arr[min]);
    }

    for(int i=0; i<5; i++){
        cout<<arr[i]<<" ";
    }
    return 0;
}
```

```java

public class SelectionSort {

	public static void Selection(int arr[]){
		int length = arr.length;

		for(int i = 0; i < length; i++){
			int min = i;

			for(int j = i + 1; j < length; j++){
				if(arr[min] > arr[j]){
					min = j;
				}
			}

			int temp = arr[min];
			arr[min] = arr[i];
			arr[i] = temp;
		}
	}

	public static void main(String[] args) {

		int arr[] = {5,2,4,3,1};

		for(int i=0; i < arr.length; i++){
			System.out.print(arr[i]+" ");
		}
		System.out.println();

		Selection(arr);

		for(int i=0; i < arr.length; i++){
			System.out.print(arr[i]+" ");
		}
	}

}

```
