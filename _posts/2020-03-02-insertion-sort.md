---
title: 삽입 정렬 (Insertion Sort)
author: Yongjun
date: 2020-03-02 00:00:00 +0900
categories: [algorithm, sort]
tags: [insertion, sort]
---

이미 정렬된 배열에 자신의 위치를 찾아 들어가는 방법으로 시간복잡도 O(n²)의 비효율적인 정렬 알고리즘입니다  

같은 시간복잡도를 가진 거품정렬, 선택정렬과 비교했을때 숫자비교횟수가 적어서 조금 더 빠르다고 볼 수도 있지만  
정렬된 배열 속으로 자신의 위치를 찾아들어가며 순차적으로 값을 교환하기 때문에 복사 비용이 클경우 더 느릴 수 있습니다  
<br>

## 그림 설명 
<style>
.responsive-wrap iframe{ max-width: 100%;}
</style>
<div class="responsive-wrap">
<iframe src="https://docs.google.com/presentation/d/e/2PACX-1vQSE5tGmlOk46et7CHrl5wt3fQa-kAwUC1W4cElnJ3CWTXyIA-Ly2ZPhlI5C5wMxF2qgWL46sARLqop/embed?start=false&loop=false&delayms=3000" frameborder="0" width="750" height="450" allowfullscreen="true" mozallowfullscreen="true" webkitallowfullscreen="true">
</iframe>
</div>
<br>

## 코드 (C++)
```c++
vector<int> numbers({3, 1, 7, 4, 6});
int size = (int)numbers.size();

for (int i = 1; i < size; i++)
{
    int index = i;
    while (index > 0 && numbers[index-1] > numbers[index])
    {
        int temp = numbers[index];
        numbers[index] = numbers[index - 1];
        numbers[index - 1] = temp;
        index--;
    }
}
```
