힙이란?

힙순서 

최소힙 - 자신의 부모는 항상 자신보다 작거나 같다.

최대힙 - 자신의 부모는 항상 자신보다 크거나 같다.

완전이진트리

왼쪽부터 채워져 있는 이진트리다.

이 두 가지를 만족하면 힙이다.

 

힙의 높이란?

n개의 키를 저장한 힙의 높이는 log n이다.

 

힙을 이용하여 우선순위 큐를 구현할 수 있다.


![다운로드](https://user-images.githubusercontent.com/102038962/216555613-b85e911e-5a4a-419a-87cd-f42b22fc72a4.png)

마지막 노드의 오른쪽에 추가하고 싶은 수를 넣는다.

![다운로드](https://user-images.githubusercontent.com/102038962/216915128-44f8c3d5-4834-419b-b780-9a59364cb801.png)

upheap알고리즘으로 1의 순서에 맞는 위치로 바꿔준다.

힙의 높이가 log n이므로 log n의 수행시간이 걸린다.

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
우선순위 큐인 힙에서 제일 작은 수를 빼는 법

1. 루트 키를 마지막 노드 키로 대체

2. 마지막 노드 삭제

3. 다운힙으로 순서 복구

#### Downheap pseudo code
```
Alg downHeap(v)
 
1. if (isExternal(leftChild(v)) & isExternal(rightChild(v)))
        return
2. smaller <- leftChild(v)     {internal node}
3. if (isInternal(rightChild(v)))
        if (key(rightChild(v)) < key(smaller))
           smaller <- rightChild(v)
4. if (key(v) <= key(smaller))
        return
5. swapElements(v, smaller)
6. downHeap(smaller)
```
![캡처](https://user-images.githubusercontent.com/102038962/216915386-4ab5d082-1755-4290-b736-967dc0b6f16e.PNG)






