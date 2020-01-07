# 퀵 정렬 (Quick Sort)

### 정의

> 특정한 값(pivot)을 기준으로 큰 숫자와 작은 숫자를 분할하여 정렬

특정한 값을 기준으로 큰 숫자와 작은 숫자를 서로 교환한 뒤, 배열을 반으로 분할

![](https://i.gifer.com/GxWJ.gif)

![](http://mblogthumb3.phinf.naver.net/MjAxNjExMjFfMTkz/MDAxNDc5NzM3MTMxMzU5.Tg4ExU7JKOiX99lM2IMJP0LQDCC3Km1zfVbQQCkikXIg.e2dj4JpTsxIYD5TvEdWWsR27fdiv-srz7dj3wSh0O1wg.PNG.cestlavie_01/quick_partitionA.png?type=w800)


### 코드

```c++
#include <iostream>
using namespace std;

int number = 10;
int data[] = {1, 10, 5, 8, 7, 6, 4, 3, 2, 9};

void show(){
    for(int i = 0; i < number ; i++){
        cout<<data[i]<<" ";
    }
}

void quickSort(int *data, int start, int end){
   // 원소가 1개인 경우
    if(start >= end)
        return;
    int key = start; // key(pivot)은 첫 번째 원소
    int left = start + 1; // 왼쪽부터 하나씩 큰 값을 찾을 때 index
    int right = end; // 끝부터 작은 값을 찾기 위해 오른쪽에서 시작
    int temp;
    
    // 엇갈릴 때 까지 반복
    while(left <= right){
        // 키 값 보다 큰 값을 만날 때 까지
        while(left <= end && data[left] <= data[key]){
            i++;
        }
        // 키 값 보다 작은 값을 만날 때 까지
        while(right > start && data[right] >= data[key]){
            j--;
        }
        
        // 엇갈린 상태일 때, key값과 data[right] 교체
        if(left > right) {
            temp = data[right];
            data[right] = data[key];
            data[key] = temp;
        }
        // 엇갈리지 않았을 때, data[left]와 data[right] 값 교체
        else {
            temp = data[left];
            data[left] = data[right];
            data[right] = temp;
        }
    }
    quickSort(data, start, right-1);
    quickSort(data, right+1, end);
}

int main(){
    quickSort(data,0,number-1);
    show();
    
    return 0;
}
```



### 시간복잡도

> O(N*logN)