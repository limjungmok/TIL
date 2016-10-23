#**삽입소트**

> 두번째 배열 인자부터 시작, 앞의 배열과 비교한다<br>
> for문을 1번, 최악의경우 while을 이용해 한바퀴 돌기때문에 수행시간은 O(n^2)이다.<br>

--------
<br>
```c++
int main(void)
{
    int arr[5]={5,2,4,3,1};

    for(int i = 1; i < 5; i++) { // 총 4번 돌고
        int key = arr[i];        // key 값은 제일 처음 배열값
        int aux = i-1;           // 비교해야 할 aux 는 시작값 바로 왼쪽 값부터 내려간다.

        while(aux >=0 && arr[aux] > key){ // aux의 인덱스가 존재하고, aux번째 배열이 key보다 큰 경우일때까지
            arr[aux + 1] = arr[aux];      // aux+1 구간에다가 지금의 aux를 넣어주고(단순 삽입)
            aux--;                        // 한단계 왼쪽의 aux를 비교하기위해 aux를 감소한다.
        }
        arr[aux+1] = key;                 // 비교가 끝난 후 aux+1번째에는 무조건 key를 넣어준다.
    }

    for(int i=0; i<5; i++) {
        cout<<arr[i]<<" ";
    }

    return 0;
}
```
