#**퀵소트**
기준되는 Pivot을 정하고(가운데 값)</br>
Pivot을 기준으로 작은 값은 왼쪽으로 옮기고</br>
Pivot을 기준으로 큰 값은 오른쪽으로 옮기는 정렬방식</br>
분할과 정렬을 동시에 진행하는 알고리즘이다.</br>
각 정렬은 배열의 크기 O(N) 만큼 비교 + 분할 된 부분은 병렬적으로 재귀를 수행하기 때문에 Divide & Conquer 특징 O(logN)</br>
최적 수행시간은 O(N * logN)</br>
최악 수행시간은 O(N^2)</br>

###**1. 흐름**

1. 변수 L, R에 각각 인덱스 0, 끝이 담긴다.
2. 피봇으로 중간 배열 값을 선택한다.
3. 왼쪽에 있는 배열값(arr[L])이 피봇보다 작으면 계속, 인덱스를 +1.
4. 오른쪽에 있는 배열 값(arr[R]이 피봇보다 크면 계속, 인덱스를 -1.
5. (3,4)의 재귀가 종료되었을 때(즉 왼쪽에는 피봇보다 큰 값이 나왔고, 오른쪽에는 큰 값이 나왔다.) 두 배열값 swap
6. swap된 배열은 당연히 피봇을 기준으로 왼쪽이 피봇보다 작은값만 존재하고, 오른쪽은 피봇보다 큰 값들만 있다.
7. L++ R-- 을 통해 인덱스를 전진시키고, swap을 반복
8. 재귀를 마치고 내려와서, 0부터 R 인덱스까지 퀵소트를 반복하고
9. L 부터 배열 끝까지 퀵소트를 반복한다.

</br>

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


void quickSort(int arr[], int low, int high){

    int pivot = arr[(low+high)/2];
    int L = low;
    int R = high;

    while(L <= R){
        while(arr[L] < pivot) L++;
        while(arr[R] > pivot) R--;
        if(L<=R){
            swap(arr[L], arr[R]);
            L++;
            R--;
        }

        if(low < R) quickSort(arr, low, R);
        if(high > L) quickSort(arr, L, high);
    }
}

int main(void){
    int arr[7] = {5, 2, 4, 6, 7, 3, 8};

    quickSort(arr, 0, 6);

    for(int i=0; i<7; i++){
        cout<<arr[i]<<" ";
    }
    return 0;
}
```
```java

public class QuickSort {

	public static void quickSort(int arr[], int low, int high){

		int pivot = arr[(low+high)/2];
	    int L = low;
	    int R = high;

	    while(L <= R){
	        while(arr[L] < pivot) L++;
	        while(arr[R] > pivot) R--;
	        if(L<=R){
	        	int temp = arr[L];
	        	arr[L] = arr[R];
	        	arr[R] = temp;
	            L++;
	            R--;
	        }

	        if(low < R) quickSort(arr, low, R);
	        if(high > L) quickSort(arr, L, high);
	    }
	}

	public static void main(String[] args) {

	    int arr[] = {5, 2, 4, 6, 7, 3, 8};

	    System.out.println("quick");
		for(int i=0; i<arr.length; i++){
			System.out.print(arr[i]+" ");
		}
		System.out.println();

		quickSort(arr, 0, arr.length-1);

		for(int i=0; i<arr.length; i++){
			System.out.print(arr[i]+" ");
		}		
	}
}
```
