---
title: 선택 정렬 (Selection Sort)
author: Yongjun
date: 2020-02-29 00:00:00 +0900
categories: [algorithm, sort]
tags: [selection, sort]
---

주어진 배열에서 최솟값을 찾아 맨앞의 원소와 교체하는 방법으로 시간복잡도 O(n²)의 비효율적인 정렬 알고리즘입니다  

같은 시간복잡도를 가진 거품정렬과 비교 했을때 선택정렬이 실제로 두 원소를 교환하는 횟수가 더 적기때문에 조금 더 빠릅니다  
<br>

## 그림 설명 
<style>
.responsive-wrap iframe{ max-width: 100%;}
</style>
<div class="responsive-wrap">
<iframe src="https://docs.google.com/presentation/d/e/2PACX-1vRPvWkPjx5LRIjhtwX9iWW7dtRZibhpbRnsKeTxUn1eOXyv6a9EKNp9gIIdGyc_ikbALGF87VOljE0x/embed?start=false&loop=false&delayms=3000" frameborder="0" width="750" height="450" allowfullscreen="true" mozallowfullscreen="true" webkitallowfullscreen="true"></iframe>
</div>
<br>

## 코드 (C++)
```c++
vector<int> numbers({5, 1, 7, 3, 4});
int size = (int)numbers.size();

for (int i = 0; i < size - 1; i++)
{
    int idxMin = i;

    for (int j = i + 1 ; j < size; j++)
    {
        if (numbers[j] < numbers[idxMin])
        {
            idxMin = j;
        }
    }
    int temp = numbers[i];
    numbers[i] = numbers[idxMin];
    numbers[idxMin] = temp;
}
```
