# 삽입정렬 (Insertion Sort)

![](https://img1.daumcdn.net/thumb/R720x0.q80/?scode=mtistory2&fname=http%3A%2F%2Fcfile8.uf.tistory.com%2Fimage%2F99A8193A5C36F7C3263FBF)





### 정의

> 각 숫자를 **적절한 위치**에 삽입 

| 선택정렬, 버블정렬 | 삽입정렬                    |
| ------------------ | --------------------------- |
| 무조건 위치를 변경 | **필요할 때만** 위치를 변경 |

삽입정렬은 삽입할 때, 앞 원소 까지는 이미 정렬이 되어있다고 가정함
### 코드
```c++
#include <iostream>
using namespace std;
int main(){
    int i, j, temp;
    int array[10] = {1, 10, 5, 8, 7, 6, 4, 3, 2, 9};
    for(i = 0;i < 9 ; i++){
        j = i;
        while(j >= 0 && array[j] > array[j+1]){
            temp = array[j];
            array[j] = array[j+1];
            array[j+1] = temp;
            j--;
        }
    }
}
```

간략한 코드 설명

- 해당 index 이전 원소들은 정렬된 상태임

  - 따라서 해당 index 바로 이전 원소와 비교하면됨

    - 조건에 따라 정렬이 끝났으면, **적절한 위치에 삽입**하기 위해 또 앞의 원소들과 비교를 해주며 위치를 

      순차적으로 찾아나간다.

### 시간복잡도

**O(N^2)**