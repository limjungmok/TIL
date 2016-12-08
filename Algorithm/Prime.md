#**소수 알고리즘**
1보다 큰 자연수 중에서, 양의 약수가 1과 자기 자신인 숫자를 의미한다.</br>

###**1. 흐름**

2 ~ N 까지 (소수는 2부터다.) 소수를 구하는 알고리즘</br>
수행시간은 for 문이 2개이므로 O(N^2)</br>
2부터 차례로 N 까지 판별을 시작하고</br>
만약 1과 자기 자신이 아닌 어떤 값으로도 나누어 진다면, 소수가 아니다.</br>

###**2. 소스 코드**

```cpp
#include <iostream>
#include <cstring>
using namespace std;

int main(void){
    int n;
    cin>>n;

    for(int i=2; i<n+1; i++){ // 1 ~ n 까지 입력중 소수를 찾기위해서.(소수는 2부터다.)

        int isPrime = true;   // 소수 판별을 위한 Flag

        for(int j=2; j<i; j++){     // 소수를 판별하기위해 1과 자기자신 이외의 어떤 값으로도 나누어지는지 확인
            if(i % j == 0){         // 1과 자기자신을 제외한 수로 나눈 나머지가 0이라면
                isPrime = false;    // 소수가 아니다.
                continue;           // 판별되면 해당 인덱스는 더 이상 볼것이 없다.
            }
        }
        if(isPrime){                // 반복을 완료하고나서도 소수임이 분명하다면
            cout<<i<<" ";           // 출력
        }
    }
}

```
```java
import java.util.Scanner;

public class Prime {
	public static void main(String[] args) {

		Scanner scan = new Scanner(System.in);
		int n = scan.nextInt();
		boolean flag = true;

		for(int i=2; i<n; i++){
			if(n%i ==0){
				flag = false;
				break;
			}
		}

		System.out.println(flag);
	}
}

```
