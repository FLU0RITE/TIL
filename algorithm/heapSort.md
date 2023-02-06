### 힙 정렬이란?

힙에 기초한 우선순위 큐를 사용함으로써, n개의 원소로 이루어진 리스트를 n log n 시간에 정렬할 수 있다.

선택 정렬이나 삽입 정렬과 같은 2차(n^2) 정렬 알고리즘보다 빠르다

```
Alg heapSort(L)

1. H <- empty heap
2. while (!L.isEmpty())    {phase 1}
       k <- L.removeFirst()
        H.insertItem(k)
3. while (!H.isEmpty())    {phase 2}
       k <- H.removeMin()
        L.addLast(k)
4. return
```

배열로 구현한 힙 정렬을 제자리 힙 정렬 알고리즘을 통해 공간 성능을 향상하는 방법이 있다.

간단히 말해, 1기에서 힙생성, 2기에서 힙 정렬을 실행하는데,

1기에서 최대힙을 제자리에서 생성한다.

2기에서 루트에 최대가 저장이 되어있는데, 이것을 맨뒤로 빼주는 작업을 하고 그 부분을 제외한 부분을

다시 최대힙으로 만들어준다.

수도 코드

```
Alg insertItem(k)
    input key k, node last
    output none

1. advanceLast()
2. z <- last
3. Set node z to k
4. expandExternal(z)
5. upHeap(z)
6. return
```
```
Alg upHeap(v)
    input node v
    output none

1. if (isRoot(v))
        return
2. if (key(v) >= key(parent(v)))
        return
3. swapElements(v, parent(v))
4. upHeap(parent(v))
```
```
Alg inPlaceHeapSort(A)
    input array A of n keys
    output sorted array A

1. buildHeap(A)            {phase 1}
2. for i <- n downto 2    {phase 2}
        A[1] <-> A[i]
        downHeap(1, i – 1)
3. return
```
```
Alg buildHeap(A)
    input array A of n keys
    output heap A of size n

1. for i <- 1 to n
        insertItem(A[i])
2. return
```
```
Alg downHeap(i, last)
   input index i of array A representing a maxheap of size last
    output none

1. left <- 2i
2. right <- 2i + 1
3. if (left > last)            {external node}
        return
4. greater <- left
5. if (right <= last)
       if (key(A[right]) > key(A[greater]))
           greater <- right
6. if (key(A[i]) >= key(A[greater]))
        return
7. A[i] <-> A[greater]
8. downHeap(greater, last)
```
힙 정렬의 시간 성능 향상을 위해 상향식 힙생성으로 속도를 높이는 방법이 있다.

“상향식”이라 불리는 이유?

이 버전은 각 재귀호출이 힙인 부트리를 반환하는 방식 때문에 상향식이라 불린다
다시 말해, T의 힙화(heapification)는 외부노드에서 시작하여, 각 재귀호출이 반환함에 따라 트리 위쪽으로 진행
이 때문에 종종 힙화한다(heapify)고 말하기도 한다
1기의 실행 시간은 inertItem 작업을 통해 upheap 작업이 이 안에 포함 되어 n log n 시간이 걸리지만,

모든 키가 미리 주어진다면 n 시간에 수행하는 상향식 생성 방식이 가능한 것이다.

재귀적 (recursive) 
```
Alg buildHeap(L)
    input list L storing n keys
    output heap T storing the keys in L

1. T <- convertToCompleteBinaryTree(L)
2. rBuildHeap(T.root())
3. return T

Alg rBuildHeap(v)            {recursive}
    input node v
    output a heap with root v

1. if (isInternal(v))
        rBuildHeap(leftChild(v))
        rBuildHeap(rightChild(v))
        downHeap(v)
2. return
```
비재귀적
```
Alg buildHeap(A)
    input array A of n keys
    output heap A of size n

1. for i  n/2 downto 1
        downHeap(i, n)
2. return
```



