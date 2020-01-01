# 버블정렬 (Bubble Sort)

<img src="https://user-images.githubusercontent.com/34755287/46913139-cb869500-cfc2-11e8-8636-19d7e306c711.gif" style="zoom:80%;" />



### 버블 정렬 정의

> **옆에 있는 값과 비교해서 더 작은 값을 반복적으로 앞에 보내는 알고리즘**

큰 수 부터 정렬(위치 고정)됨

```c++
#include <iostream>
using namespace std;
int main(){
    int i, j, temp;
    int array[10] = {1, 10, 5, 8, 7, 6, 4, 3, 2, 9};
    /*
    ** 9-i 해주는 이유 : 뒤에서 부터 집합의 크기를 하나씩 감소시킴
    */
    for(int i=0; i<10; i++){
        for(int j=0; j<9-i;j++){
            if(array[j] > array[j+1]) {
                temp = array[j];
                array[j] = array[j+1];
                array[j+1] = temp;
            }
        }
    }
    return 0;
}
```

### 버블 정렬 시간 복잡도

n+(n-1)+(n-2)+...+2+1 = n * (n+1) / 2

**O(N^2)**