---
title: 계수 정렬 (Counting Sort)
author: Yongjun
date: 2020-03-09 00:00:00 +0900
categories: [algorithm, sort]
tags: [counting, sort]
---

배열 내 모든 값의 중복 횟수를 세서 정렬하는 방법으로 조건부 시간복잡도 O(n)의 정렬 알고리즘 입니다  

0부터 배열 내 가장 큰 값까지 배열 공간을 만든 후 요소 값에 해당하는 인덱스를 증가시키기 때문에 가장 큰 값이 정렬 속도에 크게 영향을 줍니다   
조건에 따라 모든 정렬 알고리즘 중 가장 빠를 수도, 가장 느릴 수도 있습니다  
  
<br>

## 그림 설명 
<style>
.responsive-wrap iframe{ max-width: 100%;}
</style>
<div class="responsive-wrap">
<iframe src="https://docs.google.com/presentation/d/e/2PACX-1vQTajyMsMIC3gtOOFrYYYYTC4lG4NaKWo5vlueTWRDjooM5ZyGOGK4clDzGGovPtTXfGq0tM-fe7VzT/embed?start=false&loop=false&delayms=3000" frameborder="0" width="750" height="450" allowfullscreen="true" mozallowfullscreen="true" webkitallowfullscreen="true">
</iframe>
</div>
<br>

## 코드 (C++)
```c++
vector<int> numbers = {4, 2, 3, 1, 2, 2, 5, 3, 5, 1};
int min = 1; // 가장 작은 값(필요 조건)
int max = 5; // 가장 큰 값(필요 조건)
int countSize = max - min + 1;

vector<int> countArray(countSize);
    
for (int i = 0; i < numbers.size(); i++)
{
    int index = numbers[i] - min;
    countArray[index]++;
}
```
