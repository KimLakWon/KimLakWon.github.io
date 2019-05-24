---
title: "알고리즘 개념 정리"
date: 2019-05-16 17:42:28 -0400
categories: jekyll update
---

# 알고리즘

## 1. Introduction

 **1) 알고리즘(Algorithm)**
  - 인풋을 넣으면 아웃풋이 생성되는 일련의 계산 과정

 **2) 여러가지 주제**
  - Sorting Problem (정렬)
  - Knapsack Problem (가방에 어떻게 효율적으로 담을지 문제)
  - Edit Distance (두 문자열의 유사도를 판단하는 알고리즘)
  - MST (Minumum Spaning Tree, 가장 코스트가 적게 트리를 만드는 것
  - Shortest Path (가장 짧은 거리로 이동)
  - Convex Hull (어떻게 가장 효율적으로 모두를 묶을지)

## 2. Review : 자료 구조

 **1) Math**
  - floor : 내림, celiling : 올림, round : 반올림
  - sqrt > log2

 **2) Array**
  - 같은 타입의 value들의 모음으로 이루어진 자료구조

 **3) Stack**
  - LIFO (Last-In-First-Out)
  - 응용 : 괄호 묶는거, HTML 태그 묶는거, 함수 콜 추적, 연산자 undo/redo 다루기, tree/graph traversal

 **4) Queue**
  - FIFO (First-In-First-Out)
  - 원형 큐를 이용하면 관리가 좋음
  - 응용 : 클라이언트-서버 모델(여러개를 동시에 전송해주고..), BFS

 **5) Tree**
  - 자식이 없는 노드 들은 Leaf, 그 외의 노드들은 Internal Node라고 한다.
  - descendants, ancestors, sibling, degree, depth, height등..
  - path : 그 노드들이 이루는 길.. 간선 갯수가 곧 length를 의미함.

## 3. Sorting

 **1) Insertion Sort (삽입 정렬)**
  - 하나씩 비교하면서 내려가는거임.
  - O(n^2)

 **2) Merge Sort (머지 정렬)**
  - Merging : 양 배열에 화살표를 두고 낮은거부터 다른 배열로 옮김 (In-place가 불가능!)
  - 순환함수를 사용하면 쉽게 구현이 가능함. (계속 반으로 쪼개고 올라감)
  - O(nlogn)

 **3) Merge-Insertion Sort**
  - 6개 이하 정도로만 Merge로 나누고 조각들은 Insertion으로 정렬 하자. -> 적을때는 Insertion이 빠름.

## 4. Binary Heaps

 **1) Complete Binary Tree**
  - Push는 걍 해도 Complete가 유지되지만, Pop은 항상 빼고나서 가장 밑의 오른쪽에 있는 노드를 올려보내야
    Complete가 유지된다.

 **2) Array Implementation**
  - 배열 인덱스 0은 비워놓는다. (인덱스를 이용하려고) -> 여기에 사이즈 같은거 넣어도됨.
  - Breadth-first traversal로 채워놓는다. (level별)
  - 부모로 이동하려면 /2, 자식은 *2, *2+1

 **3) Heap Sort**
  - Heapification : O(n), Pop : O(log(n)) 그러므로 O(n) + n * O(log(n)) = O(nlog(n))

## 5. Bubble Sort and QuickSort

 **1) Bubble Sort**
  - 뒤쪽에 하나씩 가장 큰게 보장됨.
  - O(n^2)

 **2) QuickSort**
  - Heap Sort, Merge Sort와 같이 O(nlogn) 정렬
  - Median of three 로 pivot 구하자.
  - 이것도 몇 개 안남았을때는 Insertion sort로 구하자.
  - 최악일떄는 퀵소트가 제일 안좋음.. (계속 최소, 최대를 pivot으로 설정할때 O(n^2)
  - 메모리는 함수를 계속 스택에 축적시켜야하므로 O(logn), 최악은.. O(n)

 **3) Randomized QuickSort**
  - pivot을 랜덤으로 구함.

## 6. Bucket Sort and Radix Sort

 **1) Bucket Sort**
  - 비트 배열을 할당해주고, 그게 있으면 체크를 한다.
  - 마지막에 체크되어있는 것들 쭉 나열하면 정렬이 되어있음.
  - Omega(nlogn) ... ?

 **2) Counting Sort**
  - 비트 대신 Int 배열을 할당해주고, 그게 있으면 +1씩 증가시킴.
  - 결국 좁은 범위에서 같은 숫자들이 여러개가 있을 경우 사용하면 아주 효율적임.
  - 메모리 : O(m) , 시간 : O(m+n) // m은 배열 사이즈, n은 숫자 개수

 **3) Radix Sort**
  - 뒤에 자리수 부터 한자리씩 정렬한다.
  - binary일때 특히 더 좋다.
  - 0은 왼쪽, 1은 오른쪽 부터 채워 넣고, 오른쪽에 있던 것들은 뒤집는다.
  - 메모리 : theta(n) ,  시간 : theta(nlogm)  // m은 배열 사이즈, n은 숫자 개수

## 7. Graphs

 **1) Graph란**
  - 서로 연관된 데이터들을 저장하기 위한 ADT.
 
 **2) path**
  - trivial path : 길이가 0인 path
 
 **3) forest**
  - 포레스트는 사이클을 가지지 않는 그래프를 의미한다.

 **4) Sources and Sinks**
  - Source : in-degree가 없고 out-degree만 있는거
  - Sink : out-degree가 없고 in-degree만 있는거

 **5) DAG (Directd Acyclic Graphs)**
  - 사이클을 가지지 않는 방향 그래프
  - 응용 : 스케쥴링, makefiles, 컴퓨터 파일, OOP 상속, 가비지 콜렉션 등..
  - 토폴로지

 **6) Representation**
  - Binary-Realtion List : 그냥 pair들을 리스트로 갖고 있는거. 효율 최악. 메모리 : O(E)
  - Adjacnecy Matrix : 2차행렬에 표시. 메모리 최악. 메모리 : O(V^2)
  - Adjacency List : 각 인덱스마다 리스트. 효율 최고. 메모리 : O(V+E)

## 8. MST

 **1) Spanning Tree**
  - 항상 유니크하지는 않다.
  - 루트가 어디에 따라 다른 모양인 것 같지만, 어짜피 돌려보면 같은 트리다.

 **2) 응용**
  - 메인보드에 전류 어떻게 효율적으로 나눠줄지
  - 많은 LAN을 연결하는 최고의 방법
  - 무선 네트워크 
  - 너무 긴거 짜르기 등등

 **3) Prim's Algorithm**
  - 한 노드에서 시작해서 펼쳐감.
  - Visited, Distance, Parent 변수가 필요함.
  - 노드 방문을 최소로 하는 특징이 있음.
  - 메모리 : O(V), 시간 : O(V^2)
  - Using Priority Queue : 시간 : O(ElogV)
  - 최악의 경우 : 모든 edge의 cost가 너무 큰 것들만 가진 노드로 시작했을 경우..

 **4) Kruskal's Algorithm**
  - 모든 엣지를 일단 힙에 넣어서 정렬하고 시작함.
  - 사이클이 안나오면다면 통과
  - 끝까지 안해도, V-1개의 Edge가 통과했다면 끝내도 됨.
  - 사이클 탐색 방법 : DFS로 traversal해서 같은게 나오는지 확인하면됨 (비효율적)
  - 일단 O(EV)

## 9. Disjoint Set

 **1) operation**
  - make-set(x) : set을 설정해주는것
  - union-set(x,y) : set을 합치는것
  - find-set(x) : 어떤 set인지 찾는것

 **2) Implementation**
  - array : 쓰레기, 셋 합치려면 우리 셋이 누구인지 다찾아다녀야함.. ( O(N) )
  - tree : 좋음, 셋 합치려면 그냥 하나의 자식으로 넣으면 됨 ( O(h) )
  - 주의할 점은 parent->child가 아니라, child->parent로 연결되어야함. (무슨 그룹인지 알고싶은거니까)
  - 처음에 parent[i] = i로 놓고, parent[i] == i 일 때 까지 올라가면 됨.

 **3) Optimize**
  - 계속 높이가 높아지는 경우... 이산계수마냥..
  - 가장 좋으려면 모든 애들이 루트에 붙어있으면 됨. 그러면 항상 O(1)

 **4) Kruskal's Algorithm using Disjoint Sets**
  - 두 셋이 같은지 체크 : O(logV)
  - 두 셋 합치기 : O(logV)
  - 모든 엣지에 적용 : O(ElogV)
  - Sort : O(ElogE) = O(ElogV)
  - 결국 : O(ElogV)

 **5) 응용 : Maze Generation**
  - 미로 만들기
  - 일단 다 막혀있는 미로를 만들고, 벽에 숫자를 붙여보자.
  - 랜덤으로 골라서 그룹을 합치자, 그리고 같은 그룹은 벽을 뚫자
  - 결국 다 그룹이 1개로 합쳐지면, 미로가 완성됨.
  - 물론 처음이랑 마지막은 미리 뚫었어야함.

## 10. Dijkstra's Algorithm

 **1) Dijkstra's Algorithm**
  - single-source shortest path problem (시작점이 하나일떄 가장 짧게 가는 방법)
  - Prim's Algorithm이랑 비슷하다고 보면 됨. (차이는 그냥 목적의 차이?)

 **2) Implementation**
  - 시작점과 도착점을 알아야함.
  - Visited, Distance, Previous 변수가 필요함. // Previous는 다시 돌아가서 Path를 알려고
  - 아직 방문하지 않은 곳은 distance를 무한대라고 하자..
  - 모두 T가 될 때 까지 ㄱㄱ

 **3) Analysis**
  - 시간 : O(V^2), 메모리 : O(V)
  - PQ이용하면, O(ElogV)
  - Fibonacci heap : O(E+VlogV)

## 11. A* Search Algorithm

 **1) A* Search Algorithm**
  - single-source shortest path problem ( 다익스트라랑 비슷함)
  - heuristic(휴리스틱)을 이용해서 다익스트라보다 더 효율적으로 찾음.

 **2) Optimality**
  - 에이스타라고해서 항상 최적의 해를 찾아주진 못한다. (휴리스틱이 안좋을떄..)
  - 물론 다익스트라와 같은 경로를 찾는다. 다만 빠를 뿐.
  - 다익스트라와 다르게 모든 노드를 노드화시키지 않아도 됨.
  - 게임에서 많이 사용됨.
  - 이보다 더 발전한 형태는 D*알고리즘 (다이나믹 A* 알고리즘).. (요즘 네비게이션에서 사용)

 **3) 응용 : N Puzzle**
  - 퍼즐 맞추는거.
  - 4x4퍼즐을 맞추려면 총 16!개의 경우의수가;; (트리를 만든다고 생각해보면 끔찍하다)
  - A*를 이용하면 된다.
  - 휴리스틱 : EX) 각 자리가 맞으면 +1, 틀리면 +0..

## 12. Floyd-Warshall

 **1) Floyd-Warshall**
  - All-pair Shortest Path (여러 곳에서의 최소 경로)
  - 중간 정점들이 각각 최단이 된다면 이를 이은 경로도 최단이 된다는 개념을 이용
  - 서울 -> 부산 가야되는데, 대전에 가야된다고 표시되어있다면 일단 대전에 가고 본다.
  - boolean graph는 연결이 되어있는지만 판단하는 것.

 **2) Implementation**
  - 간단히 3차 반복문으로 만들 수 있다. -> Theta(V^3)
  - 2차배열을 만든 뒤 그래프의 weight값을 넣는다.
  - 다른 곳을 거쳐 갔을 때 더 좋은지 따져서 테이블 업데이트 시킨다.
  - 또 다른 배열을 만들고 거기에는 노드의 인덱스를 넣는다.
  - 음수 가중치가 사용 가능하다.

## 13. Topological Sort
  
 **1) Definition**
  - DAG(Directed Acyclic Graph)에서 항상 사용이 가능하다.
  - 노드에 In-degree가 0이 되었을 경우에만 뽑아내는 것이 가능
  - 유니크하지 않다.

 **2) 응용 : 옷입는 방법, 일의 순서 정하는 것**

 **3) Implementation**
  - in-degree 표만 있으면 됨. => O(V)
  - 큐를 이용해서 in-degree가 0인것을 넣는다.
  - 큐가 빌때까지 하면 됨.

 **4) Critical Path**
  - In-degree 말고도, Task time과 Critical Time, 그리고 Previous Task도 있어야함.
  - 큐에 넣고, 끝날때마다 Critical Time += Task Time을 시전해줌.
  - 제일 늦게 끝나는걸 기다려줘야함.

## 14. Network Flow

 **1) Duality**
  - Maximum flow problem과 Minimum cut problem은 같은 문제다.
  - 작은것들을 잘라야 많이 흐르니까

 **2) Maximum flow problem**
  - source부터 sink까지 어떤 것을 보낼껀데, 가장 통로가 넓은 곳으로 보내고 싶다.
  - 네트워크에서 많은 패킷을 보내고 싶을 때,
  - 트럭에서 많은 짐을 싣고 보내고 싶을 때,
  - 가장 적게 다리를 부시고 싶을 때

 **3) Flow Network**
  - flow : 지금 흐르는양, capacity : 최대 흐를 수 있는 양
  - f(a,b) : a->b일때 flow, c(a,b) : a->b일때 capacity,    f(a,b) = -f(b,a) 임..
  - 결국 f(source, sink)에서 소스에서 나가는 것과 싱크로 들어오는 값은 항상 같음.

 **4) Multiple Sources Network**
  - 여러개의 출발지점이랑 여러개의 도착지점이 있을 경우
  - 그냥 가상의 출발지점과 가상의 도착지점을 만들어.. 거기까지의 flow는 무한대로설정.

 **5) Residual Networks**
  - Flow를 반대로 쓰고, Capacity - Flow를 거기에 씀
  - 예를들어 4/12 만큼 흐르고 있다면 8만큼 더 흐를 수 있고, -4만큼 더 흐를 수 있다는 걸 의미함.
  - 그래서 반대에 4를 써주는거임.. (마이너스를 써줘야 숨어있는 길도 찾을 수 있기 때문에)
  - augmenting path(소스에서 싱크로 가는 길)를 찾는 과정

 **6) Ford-Fulkerson Method**
  - 임의로 하나 path를 고르자 (DFS든 BFS든)
  - Original Network -> Flow Network -> Residual Network > Flow Network (반복)
  - 더 이상 흐를 곳이 없을 때 까지 반복하면 된다.
  - 시간 : O(EF) // E: 간선 갯수, F : 맥시멈 플로우
  - 실수면, 정수꼴로 바꿔서 해라 (허수면 답없음)
  - 이건 polynomial이 아니라, 운이 안좋으면 성능이 안좋을수도 있음.

 **7) Edmonds-Karp Algorithm**
  - Ford-Fulkerson의 단점을 고치기위해서 BFS를 섞음.
  - 시간 : O(VE^2)

 **8) Maximum Bipartite Matching**
  - 양 쪽에 노드들이 있을 때, 겹치지 않고 많이 연결하려면?
  - multiple max-flow problem이라 생각하면 된다. 


## 15. Greedy Algorithm

 **1) Brute-force**
  - 가장 구현하기 쉽지만, 가장 작동하기 어려운 방식..
  - optimal 해를 찾긴 하지만, 너무 오래걸린다.
  - feasible solution이다. (어느 조건에서도 만족하는 해)

 **2) Greedy**
  - partial solution이다. (부분적)
  - optimal이 아닐 수 있다.
  - Prim, Dijkstra 알고리즘이 Greedy임. (얘네들은 Optimal임)

 **3) 응용 : Making Change**
  - 잔돈 잘 쓰기
  - 큰것부터 걍 써버리면 어쨋든 합리적이니까.
  - optimal 찾을려면 다 해봐야된다.

 **4) 응용 : 0/1 Knapsack Problem**
  - 시간과 수입에 맞춰 효율적으로 잘 선택해야되는것
  - optimal 찾으려면 다 해봐야된다.

 **5) 응용 : Interval Scheduling**
  - 스케쥴 시간 효율적으로 잘 짜는거
  - optimal을 찾으려면 다 해봐야된다.

## 16. Dynamic Programming (다이나믹 프로그래밍)

 **1) Fibonacci Number**
  - 피보나치 수를 구하기 위한 방법은 여러가지가 있다.
  - 순환함수 : 구현은 쉽지만, 50만 넘어가도 1분이 넘게 걸린다;;; (메모리도 폭발)
  - 메모라이제이션 : static 배열에 저장하자, 50넘어가도 0.0000001초... good
  - 순환함수를 Top-down 알고리즘, 메모라이제이션을 Bottom-up 알고리즘이라 한다.

 **2) Dynamic Programming**
  - 최적 해를 구할 수 있다.
  - Top-down 방식 알고리즘이다.

 **3) 응용 : Matrix Chain Multiplication**
  - 여러개의 행렬 곱이 있을 때 (ABCDE...)
  - 곱하는 순서에 따라 연산의 양이 달라진다.
  - 2차 배열로 구한다.

 **4) 응용 : Optimal Polygon Triangulation**
  - 다각형이 있을때 어떻게 삼각형으로 쪼개야 비율이 맞을지 구하는 것.
  - 다각형의 각 변을 숫자로 놓고, 삼각형이 만들어지면 윗 변이 2개니까 2개씩 묶는 행렬 곱 문제라고 생각하면 됨
 
 **5) 응용 : Interval Scheduling, 0/1 Knapsack Problem 등... 엄청 많다.**
