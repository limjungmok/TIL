#**선택 정렬**

> 첫번째 배열 인자를 시작으로, 뒤에있는 배열값을 모두 비교하여 min 숫자를 저장해놓음.<br>
> for문을 2번 이용하기 때문에 수행시간은 O(N^2)<br>

--------
<br>
```c++
int arr[5]={5,2,4,3,1};

    for(int i=0; i < 5; i++) { // 총 5번 도는데
        int min=i;             // 배열의 첫번째 값을 min 으로 지정해논다.

        for(int j=i+1; j<5; j++){
            if(arr[min] > arr[j]){
                min = j;       // min 값을 누적해 놓음.
            }
        }

        swap(arr[min], arr[i]);// min 이었던 첫번째 원소와 Swap
    }

    for(int i=0; i<5; i++) {
        cout<<arr[i]<<" ";
    }

    return 0;
```
