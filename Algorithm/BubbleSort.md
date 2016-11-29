#**버블소트**
가장 기본적으로 둘씩 짝지어서 비교, 정렬<br>
for문을 2번 이용하기때문에 수행시간은 O(n^2)이다.<br>

###**흐름**

초기값 </br>
5 2 4 3 1</br>
</br>
첫번째 반복</br>
2 4 3 1 5</br>
</br>
두 번째 반복</br>
2 4 1 3 5</br>
</br>
세 번째 반복</br>
2 1 3 4 5</br>
</br>
네 번째 반복</br>
1 2 3 4 5</br>
</br>

> 총 배열의 크기 -1 만큼 순회한다.</br>
> 동시에 (0,1) (1,2) (2,3) (n-1-(i-1), n-1-(i)) 까지 비교해간다.</br>
</br>

```c++
#include <iostream>
using namespace std;

void swap(int *a, int *b){
    int temp;
    temp = *a;
    *a = *b;
    *b = temp;
}


int main(void){
    int arr[5] = {5,2,4,3,1};

    for(int i=0; i<4; i++){
        for(int j=0; j<4-i; j++){
            if(arr[j] > arr[j+1]){
                swap(arr[j], arr[j+1]);
            }
        }
    }

    for(int i=0; i<5; i++){
        cout<<arr[i]<<" ";
    }
    return 0;
}
```
