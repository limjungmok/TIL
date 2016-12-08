#**팰린드롬 알고리즘**
문자열을 거꾸로 해도 같은 문자열인지 판별하는 알고리즘.</br>


###**1. 흐름**
1. arr = "aaabbbaaa" 형태로 문자열 길이는 9다.
2. 홀수/짝수와 관계없이, 문자열 길이의 1/2만 돌면서 비교하면 값을 구할 수 있다.

###**2. 소스코드**

```cpp
#include <iostream>
#include <cstring>
using namespace std;

int main(void){

    string arr="aaabbbaaa";
    string ret="같다";
    int arrLength= arr.length();

    for(int i=0; i< arrLength/2; i++){
        if(arr[i] != arr[arrLength - (i+1)]){
            ret="다르다";
            break;
        }
    }
    cout<<ret<<endl;

    return 0;
}
```

```java

public class Palindrome {

	public static void main(String[] args) {

		String str = "abcba";
		boolean flag = true;	//초기에 true로 설정 해 놓은 뒤

		for(int i=0; i<str.length(); i++){
			if(str.charAt(i) != str.charAt(str.length() - (i+1))){
				flag = false;	//만약 한 번 이라도 대칭 문자가 다르면, false로 하고 break;
				break;
			}
		}

		if(flag == true){
			System.out.println("앞뒤가 같다.");
		}else{
			System.out.println("앞뒤가 다르다,");
		}
	}
}
```
