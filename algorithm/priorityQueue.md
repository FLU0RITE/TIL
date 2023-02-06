### 우선순위 큐

우선순위 큐 이용한 정렬

비교 가능한 원소 집합을 정렬하는데 우선순위 큐를 이용할 수 있다.

1. 연속적인 insertItem(e, e) 작업을 통해 원소들을 하나씩 삽입 (key = e로 전제)

2. 연속적인 removeMin() 작업을 통해 원소들을 정렬 순서로 삭제

실행시간: 우선순위 큐의 구현에 따라 다르다.

#### 우선순위 정렬 pseudo code

Alg PQ-Sort(L)
    input list L
    output sorted list L
```
1. P <- empty priority queue
2. while (!L.isEmpty())
       e <- L.removeFirst()
        P.insertItem(e)
3. while (!P.isEmpty())
       e <- P.removeMin()
        L.addLast(e)
4. return
```

우선순위 큐의 항목들을 리스트에 임의 순서로 저장

insertItem: O(1) 시간 소요 – 항목을 리스트의 맨 앞 또는 맨 뒤에 삽입할 수 있으므로

removeMin: O(n) 시간 소요 – 최소 키를 찾기 위해 전체 리스트를 순회해야 하므로



우선순위 큐의 항목들을 리스트에 키 정렬 순서로 저장 

insertItem: O(n) 시간 소요 – 항목을 삽입할 곳을 찾아야 하므로

removeMin: O(1) 시간 소요 – 최소 키가 리스트의 맨 앞에 있으므로

선택 정렬(selection-sort)은 PQ-Sort의 일종으로서 우선순위 큐가 무순리스트로 구현된다

selection-sort의 실행시간

 - n회의 insertItem 원소들을 우선순위 큐에 삽입하는데 O(n) 시간 소요

 - n회의 removeMin 원소들을 우선순위 큐로부터 정렬 순서로 삭제 다음에 비례하는 시간 소요

    n + (n - 1) + (n - 2) + … + 2 + 1

전체 실행시간: O(n^2)



삽입 정렬(insertion-sort)은 PQ-Sort의 일종으로서 우선순위 큐가 순서리스트로 구현된다

insertion-sort의 실행시간

 - n회의 insertItem 원소들을 우선순위 큐에 삽입하는데 다음에 비례하는 시간 소요

    1 + 2 + … + (n - 2) + (n - 1) + n

 - n회의 removeMin 작업을 사용하여 원소들을 우선순위 큐로부터 정렬 순서로 삭제하는데 O(n) 시간 소요

전체 실행시간: O(n^2)

#### 제자리 선택 정렬 알고리즘 pseudo code

```
Alg inPlaceSelectionSort(A)
    input array A of n keys
    output sorted array A

1. for pass <- 0 to n – 2 // pass는 인덱스
       minLoc <- pass // 제일 작은 수가 저장된 로케이션에 인덱스 pass를 넣음(초기의 pass는 0)
        for j <- (pass + 1) to n – 1 // 제일 작은 수라고 넣은 수의 다음부터 n-1 까지
            if (A[j] < A[minLoc]) // 만약 제일 작은 수보다 작은 수가 발견되면
               minLoc <- j // 로케이션 바꿈(제일 작은 수가 들어감)
        A[pass] <-> A[minLoc] // 로케이션의 수와 패스의 수를 바꿈(결국 제일 작은 수가 왼쪽에 감)
2. return
// 제일 처음 작동 될 때 제일 작은 수가 왼쪽에 위치함
```

#### 제자리 삽입 정렬 알고리즘 pseudo code
```
Alg inPlaceInsertionSort(A)
    input array A of n keys
    output sorted array A

1. for pass <- 1 to n – 1 // pass는 왼쪽에서 두번째부터 시작
       save <- A[pass] // 세이브에 해당 pass 인덱스인 값을 저장
       j <- pass – 1 // j는 pass의 왼쪽 인덱스부터
        while ((j >= 0) & (A[j] > save)) // j가 0보다 크고, 그 해당값이 세이브보다 크면
            A[j + 1] <- A[j] // 해당 조건을 만족시 왼쪽에서 오른쪽으로 저장
           j <- j – 1 // 인덱스 하나 내림
        A[j + 1] <- save // 세이브에 있던 수를 마지막으로 옮긴 위치에 저장
2. return
// 왼쪽에 오른쪽보다 항상 작은 수가 저장됨
```

#### 공통점

 - 전체적으로 O(n^2) 시간

 - 내부 반복문: O(n) 선형 탐색

 - 외부 반복문: O(n) 패스

 - 제자리 버전은 O(1) 공간 소요

 - 구현이 단순

 - 작은 n에 대해 유용



#### 초기 리스트가 완전히 또는 거의 정렬된 경우

 - in-place insertion-sort가 더 빠르다

 - 내부 반복문이 O(1) 시간 소요, 따라서 전체적으로 O(n) 시간에 수행되므로

A[j + 1] <- A[j], swapElements 작업이 비싼 경우

 - in-place selection-sort가 더 빠르다

 - swapElements 작업이 패스마다 O(1) 시간 수행되는데,

    in-place insertion-sort에서는 동일 작업이 패스마다 최악의 경우 O(n) 시간 수행
