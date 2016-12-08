#**최대공약수 최소공배수**
두 입력값을 나눌 수 있는 **최대 공약수**</br>
두 입력값의 공통된 배수 중 최소값인 **최소 공배수**</br>

###**1. 흐름**

입력값 12 80</br>

1. 12, 80 두 값이 들어가면 최대공약수를 먼저 계산한다.
2. gcd(12,80) -> gcd(80, 12) -> gcd(12, 8) -> gcd(8, 4) -> gcd(4, 0) -> 최대공약수 : 4
3. lcm(12, 80, 4) -> 12*80/4 -> 960 / 4 -> 최소공배수 : 240
</br>

###**2. 소스코드**

```cpp
#include <iostream>
#include <cstring>
using namespace std;

int gcd(int a, int b){

    if(b == 0){
        return a;
    }else{
        return gcd(b, a%b);
    }
}

int lcm(int a, int b, int gcd){

    return (a*b)/gcd;
}

int main(void){

    int a,b;
    cin>>a>>b;
    cout<<"최대공약수 : "<<gcd(a,b)<<endl;
    cout<<"최소공배수 : "<<lcm(a,b,gcd(a,b))<<endl;
    return 0;
}

```
```java

public class GCD_LCM {

	public static int gcd(int a, int b){
		if(b==0){
			return a;
		}else{
			return gcd(b, a%b);
		}
	}
	
	public static int lcm(int a, int b, int gcd){
		return (a*b)/gcd;
	}

	public static void main(String[] args) {

		int a = 30;
		int b = 14;

		System.out.println(gcd(a,b));
		System.out.println(lcm(a,b,gcd(a,b)));
	}
}
```
