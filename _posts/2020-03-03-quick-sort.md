---
title: 퀵 정렬 (Quick Sort)
author: Yongjun
date: 2020-03-03 00:00:00 +0800
categories: [algorithm, sort]
tags: [quick, sort]
---

배열의 임의 원소보다 작은 값 배열과 큰 값 배열로 나누고, 나뉜 두 배열에 대해서 재귀적으로 반복하는 방법으로 평균 시간복잡도 O(n log n), 최악 시간복잡도 O(n²)의 정렬 알고리즘 입니다  

분할정복 알고리즘으로 같은 시간복잡도 O(n log n)를 가진 병합 정렬, 힙 정렬과 비교했을때 평균적으로 더 빠른 정렬속도를 기대할 수 있습니다
<br>

## 그림 설명 
<style>
.responsive-wrap iframe{ max-width: 100%;}
</style>
<div class="responsive-wrap">
<iframe src="https://docs.google.com/presentation/d/e/2PACX-1vT3C52uDh5TIJBNjxXSRSmGiBVoUu39IFfXF3LofFKGhWR2a6YF5Tdp2jnj1WEIgQ3wOnicX1unUH2A/embed?start=false&loop=false&delayms=3000" frameborder="0" width="750" height="450" allowfullscreen="true" mozallowfullscreen="true" webkitallowfullscreen="true">
</iframe>
</div>
<br>

## 코드 (C++)
```c++
void QuickSort(vector<int>& numbers, int pivot, int end)
{
    if (pivot >= end)
    {
        return;
    }
    int left = pivot + 1;
    int right = end;

    while (left <= right)
    {
        while (left <= end && numbers[pivot] >= numbers[left])
        {
            left++;
        }
        while (right > pivot&& numbers[pivot] <= numbers[right])
        {
            right--;
        }
        if (left > right)
        {
            int temp = numbers[pivot];
            numbers[pivot] = numbers[right];
            numbers[right] = temp;
        }
        else
        {
            int temp = numbers[left];
            numbers[left] = numbers[right];
            numbers[right] = temp;
        }
    }
    QuickSort(numbers, pivot, right - 1);
    QuickSort(numbers, right + 1, end);
}
```
```c++
vector<int> numbers{5, 3, 2, 9, 1, 6, 8, 7};
    
QuickSort(numbers, 0, (int)numbers.size() - 1);
```
