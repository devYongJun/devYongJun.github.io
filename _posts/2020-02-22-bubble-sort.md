---
title: 거품 정렬 (Bubble Sort)
author: Yongjun
date: 2020-02-22 11:33:00 +0900
categories: [algorithm, sort]
tags: [bubble, sort]
---

두 인접한 원소를 검사하여 정렬하는 방법으로 시간복잡도 O(n²)의 비효율적인 정렬 알고리즘입니다  

정렬속도가 느리지만 코드가 단순하고 쉬워서 정렬 알고리즘을 처음 접하는 사람이 공부하기 좋습니다  
<br>

## 그림 설명 
<style>
.responsive-wrap iframe{ max-width: 100%;}
</style>
<div class="responsive-wrap">
<iframe src="https://docs.google.com/presentation/d/e/2PACX-1vTuuuffF5TkuPamEejpFhm7z_9J_GxjRu29K2eD5qAOQkCOoxojw0dmKt0enpYUWiHUeADQnZW9WLsm/embed?start=false&loop=false&delayms=3000" frameborder="0" width="750" height="450" allowfullscreen="true" mozallowfullscreen="true" webkitallowfullscreen="true"></iframe>
</div>
<br>

## 코드 (C++)
```c++
vector<int> numbers({5, 1, 7, 3, 4});
int size = (int)numbers.size();

for (int i = 0; i < size - 1; i++)
{
    for (int j = 0; j < size - i - 1; j++)
    {
        if (numbers[j] > numbers[j + 1])
        {
            int temp = numbers[j];
            numbers[j] = numbers[j + 1];
            numbers[j + 1] = temp;
        }
    }
}
```
