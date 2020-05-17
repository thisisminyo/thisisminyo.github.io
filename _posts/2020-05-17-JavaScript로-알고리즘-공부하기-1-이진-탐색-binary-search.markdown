---
layout: post
title: "[JavaScript로 알고리즘 공부하기] 1. 이진 탐색 binary search"
categories: jekyll
---

_이 포스트의 내용은 도서 [Hello Coding 그림으로 개념을 이해하는 알고리즘](https://book.naver.com/bookdb/book_detail.nhn?bid=11823284)의 내용을 기반으로 하여 작성하였습니다_



## 이진 탐색 (bianry search)

n개의 원소를 가진 리스트를 탐색할때
- 단순탐색 : 최대 n번
- 이진탐색 : log<sub>2</sub> n번

n이 100일 경우 
- 단순탐색 : 최대 100번
- 이진탐색 : 최대 7번

**이진탐색은 리스트의 원소들이 정렬된 경우에만 사용 가능하다**

정렬된 요소들을 탐색하여 위아래로 움직이기 때문에...




# 이진탐색 프로그램 만들기

`
binarySearch = (list, item) => {
    let low = 0;
    let high = list.length - 1;

    while (low <= high) {
        let mid = parseInt((low + high) / 2); // need integer number of mid value
        let guess = list[mid];
        
        if (guess == item) {  return mid; } // return index of value of item 
        
        if (guess > item) {
            high = mid - 1;
        } else {
            low = mid + 1;
        }
    }
    return -1; // can't find item in this array
};

//sample list
list = [1, 2, 3, 4, 5, 6, 7, 8, 9, 10];

//test
console.log(binarySearch(list, 6)); // 5
console.log(binarySearch(list, 2)); // 1
console.log(binarySearch(list, 0)); // -1
console.log(binarySearch(list, 11)); // -1
`

책에 나온 파이썬 예제를 이용하여 자바스크립트 버전으로 작성 해보았다.






