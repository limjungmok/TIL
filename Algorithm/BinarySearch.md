#**이진 탐색**
찾으려는 값을 배열의 중간값을 기준으로 잘게 쪼개서 순회한다.</br>
중간값을 기준으로 절반으로 쪼개는 과정을 반복하기 때문에 수행시간은 O(logN)이다.</br>
####* 단, 이진탐색을 할 때는 반드시 정렬 된 배열이어야 한다</br>


###**1. 흐름**

초기 배열 : 1, 2, 3, 4, 5, 6, 7, 8</br>
찾는 숫자 : 10</br>
</br>

####1)</br>
low : 1
high : 8
중간값 : 5</br>
10 > 6</br>
low 를 중간값 + 1 번째 인덱스로 이동</br>

####2)</br>
low : 6</br>
high : 8</br>
중간값 : 7</br>
10 > 7</br>
low를 중간값 + 1 번째 인덱스로 이동</br>

####3)</br>
low : 8</br>
high : 8</br>
중간값 : 8</br>
10 > 8</br>
low를 중간값 +1 번째 인덱스로 이동</br>

####4)</br>
low : 배열 초과</br>
high : 8</br>
if(low <= high) 조건에 걸리고, return -1 을 반환한다.</br>

결과 : -1 (존재하지 않는다.)</br>

###**2. 소스 코드**
```cpp
#include <iostream>
#include <cstring>
using namespace std;

int binarySearch(int arr[], int size, int findData){

    int low = 0;
    int high = size-1;
    int mid;

    while(low <= high){
        mid = (low+high) / 2;           // 중간 값의 인덱스를 추출
        if(findData > arr[mid]){        // 비교값과 중간 인덱스의 값을 비교
            low = mid+1;                // 만약 비교하는 값이 중간값보다 크다면, 기준을 올리고
        }else if (findData < arr[mid]){
            high = mid-1;               // 중간값보다 작다면 기준을 내린다.
        }else{
            return mid;                 // 그것도 아니면 찾는 데이터를 얻는다.
        }
    }
    return -1;                          // 값을 찾지 ㅁ
}

int main(void){

    int arr[8]={1, 2, 3, 4, 5, 6, 7, 8};
    int index = binarySearch(arr, 8, 10);
    if(index > -1) cout<<"arr 배열의 "<<index<<"번째 인덱스에 찾는 데이터가 있습니다.";
    else cout<<"배열에 찾는 데이터가 없음";
}
```
