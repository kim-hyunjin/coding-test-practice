# 완전탐색 정리

1. 무식하게 모든 경우의 수를 다 살펴봐도 시간초과 나지 않을지 확인
2. 될 거 같으면 완전탐색으로 문제를 푼다

-   안될 거 같으면 더 효율적인 알고리즘을 찾아보자 (greedy, DP, Binary Search...)

# 탐욕법 정리

1. 무식하게 모든 경우의 수를 다 살펴봐도 시간초과 나지 않을지 확인
2. 될 거 같으면 완전탐색으로 문제를 푼다

-   안될 거 같으면 더 효율적인 알고리즘을 찾아보자 (greedy, DP, Binary Search...)

3. greedy는 반례가 없을까 신중하게 고려하자

# 그래프 구현

-   인접행렬 - 메모리를 더 많이 사용(V^2), 조회가 더 빠름 O(1).
-   인접리스트 - 메모리를 더 적게 사용(V + E), 조회가 더 느림 O(N). 간선이 적을 때 유용

# DFS (Depth First Search)

-   스택 or 재귀를 사용해서 구현

# BFS (Breadth First Search)

-   큐를 이용해서 구현

# DFS & BFS

## 공통점

-   완전탐색의 장점을 가진다(모든 노드를 탐색하므로 항상 답을 찾을 수 있다.)

## 차이점

-   탐색 순서가 다르다
-   최단거리 구하기 문제는 bfs가 보통 유리하다

# 백트래킹 Backtracking 퇴각검색

-   기본적으로 모든 경우를 탐색하며 DFS/BFS와 방식은 유사하다.
-   가지치기를 통해 탐색 경우의 수를 줄인다는 차이가 있다.
    -   최악의 경우, 모든 경우를 다 살펴보게 될 수도 있지만 가능한 덜 보겠다는 전략
    -   '가망이 없으면 가지 않는다'

# 이진탐색

-   탐색 전에 반드시 정렬되어 있어야 한다.
-   살펴보는 범위를 절반 씩 줄여나가면서 답을 찾는다.

# 파라메트릭 서치

-   **최적화 문제**를 **결정 문제**로 바꿔서 이진탐색으로 푸는 방법이다.
    -   최적화 문제: 문제 상황을 만족하는 변수의 **최솟값, 최댓값**을 구하는 문제
    -   결정 문제: YES / NO 문제

# 동적계획법 Dynamic Programming

-   문제를 쪼개서 작은 문제의 답을 구하고, 그걸로 더 큰 문제의 답을 구하는 걸 반복(분할정복과 비슷한 느낌)

## DP 구현방식 2가지

-   Top-down : 재귀, 메모이제이션(Memoization)
    -   메모이제이션: 부분 문제들의 답을 반복해서 구하지 않도록 cache에 저장해두고 다음 계산에 사용
    -   필요한 부분 문제들만 구한다. Lazy-Evaluation
    -   장점: 직관적이라 코드 가독성이 좋다.
    -   단점: 재귀함수 호출을 많이 해서 느릴 수 있다.
-   Bottom-up: 반복문, 타뷸레이션(Tabulation)
    -   타뷸레이션: 부분 문제들의 답을 미리 다 구해둔다. Eager-Evaluation
    -   테이블을 채워나간다라는 의미
    -   시간과 메모리를 좀 더 아낄 수도 있다.
    -   DP 테이블 채워 나가는 순서를 알아야 한다.

## 정리

-   동적계획법은 문제를 쪼개서 **작은 문제**부터 구해가며 원래 문제의 답을 구하는 방식
-   메모이제이션
-   점화식 찾고 테이블만 잘 정의하면 풀리는 문제들이 많다.(그 점화식 찾기가 어렵다는 것이 함정...)
