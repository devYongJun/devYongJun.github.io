---
title: 병합 정렬 (Merge Sort)
author: Yongjun
date: 2020-03-04 00:00:00 +0900
categories: [algorithm, sort]
tags: [merge, sort]
---

배열 길이가 1이하가 될때까지 계속 반씩 나누고, 나뉜배열을 다시 병합하며 정렬하는 방법으로 시간복잡도 O(n log n)의 정렬 알고리즘 입니다  

천재 폰 노이만이 개발한 분할정복 알고리즘으로 최악의 경우에도 시간복잡도 O(n log n)을 보장합니다
<br>

## 그림 설명 
<style>
.responsive-wrap iframe{ max-width: 100%;}
</style>
<div class="responsive-wrap">
<iframe src="https://docs.google.com/presentation/d/e/2PACX-1vTIwXODl7MUEMeUDbQn8Mc3aP9lQ4DwWGi1CXUxm3ssrGPfS92t40kkbReT2Mao9KehShaKW-lZkoJ8/embed?start=false&loop=false&delayms=3000" frameborder="0" width="750" height="450" allowfullscreen="true" mozallowfullscreen="true" webkitallowfullscreen="true">
</iframe>
</div>
<br>

## 코드 (C++)
```c++
void Merge(vector<int>& numbers, vector<int>& temp, int start, int mid, int end)
{
    for (int i = start; i <= end; i++)
    {
        temp[i] = numbers[i];
    }
    int left = start;
    int right = mid + 1;
    int index = start;

    while (left <= mid && right <= end)
    {
        if (temp[left] <= temp[right])
        {
            numbers[index] = temp[left];
            left++;
        }
        else
        {
            numbers[index] = temp[right];
            right++;
        }
        index++;
    }
    for (int i = left; i <= mid; i++)
    {
        numbers[index] = temp[i];
        index++;
    }
}
```
```c++
void MergeSortRecursive(vector<int>& numbers, vector<int>& temp, int start, int end)
{
    if (start >= end)
    {
        return;
    }
    int mid = (start + end) / 2;
    MergeSortRecursive(numbers, temp, start, mid);
    MergeSortRecursive(numbers, temp, mid + 1, end);
    Merge(numbers, temp, start, mid, end);
}
```
```c++
vector<int> numbers = {2, 1, 7, 4, 6, 9, 5, 3};
int size = (int)numbers.size();
vector<int> temp(size);

MergeSortRecursive(numbers, temp, 0, size - 1);
```
