# 선택정렬(Selection Sort)

![선택정렬](https://img1.daumcdn.net/thumb/R800x0/?scode=mtistory2&fname=https%3A%2F%2Ft1.daumcdn.net%2Fcfile%2Ftistory%2F23259F3458C4E20A11)

> **가장 작은 것을 선택해서 가장 앞으로 보내는 알고리즘**

각 위치에서 마지막 원소까지 본 뒤 가장 작은 원소를 **선택**

### 선택정렬 코드

```c++
#include <iostream>
using namespace std;

int main(){
    
    /* i, j : 배열에 있는 정보 반복적으로 탐색
    ** min : 최솟값
    ** index : 가장 작은 원소가 존재하는 위치
    ** temp : 두 숫자를 바꾸기 위해 사용하는 변수
    */
    int i, j, min, index, temp;  
    int array[10] = {1, 10, 5, 8, 7, 6, 4, 3, 2, 9};
    for(int i=0; i<10; i++){
        min = 9999; // 모든 원소들 보다 더 큰 숫자 why? 항상 최솟값을 선택해야 하기 때문에
        for(int j=0; j<10; j++){
            if(min > array[j]){
                min = array[j];
                index = j;
            }
        }
        /* swaping */ 
        temp = array[i];
        array[i] = array[index];
        array[index] = temp;
    }
    return 0;
}
```



### 선택정렬 시간 복잡도

n+(n-1)+(n-2)+(n-3)+...+2+1 = n * (n+1) / 2

**O(N * N) = O(N^2)**

연산 횟수가 매우 많음 -> 다른 알고리즘과 비교했을 때 비효율적이고 시간이 많이 걸림