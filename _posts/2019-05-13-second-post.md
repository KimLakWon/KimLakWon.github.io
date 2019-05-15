---
title: "자료구조 개념 정리"
date: 2019-05-13 00:43:28 -0400
categories: jekyll update
---

# 자료구조

## 1. Course overview
 **1) 자료구조는 왜 중요할까?**
  - 데이터를 어떻게 표현할 지, 어떻게 조작을 할 수 있을 지, 알기 위해서 자료구조를 알아야 합니다.
  - 특히, 알고리즘은 여러가지 데이터의 표현과 조작을 필요로 합니다.  
  
 **2) 알고리즘 vs 자료구조**
  - 알고리즘 : 문제를 해결하는 방법 (ex. 낚시)
  - 자료구조 : 정보를 저장하는 방법 (ex. 낚시채, 그물망 ...)  
  
 **3) 알고리즘 + 자료구조는 ?**
  - 알고리즘 + 자료구조 = 프로그램
  - Niklaus Wirth가 한 말이다. (1984 튜링 어워드)  

## 2. Introduction
 **1) 알고리즘**
  - 알고리즘은 음식 레시피와 같다. (어떻게 어떻게 하면 음식이 완성됨!)
  - 알고리즘은 유한개의 지시문(Instruction) 모음이다.
  - 알고리즘은 정의할 수 있어야하며, 효율적이어야한다.  
 **2) 데이터 타입**
  - 실제 세계에서 어떤것을 표현하기 위한 데이터의 모음
  - 각 프로그래밍 언어들은 기본적인 데이터 타입을 제공한다. (int, char, float ...)  
 **3) 자료구조**
  - 자료구조는 데이터의 논리적 구성이다.
  - C언어는 기본적으로 데이터를 묶어주는 메커니즘인 structure와 array를 제공한다.  
 **4) ADT (Abstract Data Type, 추상 데이터 타입)**
  - 데이터 값의 정의와 표현이 분리되어있다.  
  - 데이터 연산의 정의와 구현이 분리되어있다.  
  - 캡슐화(encapsulation)와 정보은닉(information hiding)을 위한 것이다. (OOP의 특징 중 하나)  
  * 캡슐화 : 실제 구현 내용을 외부에 감춤으로써 정보 은닉 개념을 지킬 수 있게 한다.  
  * 정보은닉 : 외부에서 객체의 내부를 들여다볼 수 없다는 개념. (생각을 알고 싶다면 요청해서 넘겨받아야한다.)  
  * 캡슐화 vs 정보은닉 : 정보은닉은 '개념', 캡슐화는 '그 개념을 행한 것'이라 보면 된다.  
  * 정보은닉의 장점  
   (1) 역할 분리 : 사용자와 제공자의 역할을 명확히 분리해준다.  
   (2) 사용 용이 : 인터페이스를 통해 사용자가 쉽게 사용할 수 있다.  
   (3) 변경 용이 : 외부는 변하지 않으므로, 내부의 자료구조 변경이 용이하다.  
   (4) 독립성 : 다른 모듈과 관계가 적어 모듈의 독립성을 높여준다.  
   (5) 확장성 증가 : 데이터와 알고리즘 변경이 쉬워, 기능을 추가하기도 쉽다.  
  - ADT의 3가지 연산 : Creator, Transformers, Observers  
  - 주요 ADT의 예 : List, Stack, Queue, Tree, Graph, etc.  
  - 언어와 ADT : OOP(ex. C++, Java)는 제공해주지만, C와 같은 언어는 ADT를 구현할 명확한 메커니즘이 없다.  
    그렇다고 구현을 못한다는건 아니다.  
 **5) Search**
 - 선형 탐색 (Linear Search = Sequential Search)  
   장점 : 이해하기 쉽다.. 구현하기 쉽다..  
   단점 : 느리다.. O(N)  
 - 이진 탐색 (Binary Search)  
   장점 : 빠르다.. O(logN)  
   단점 : 정렬이 되어있어야한다. (but 정렬도 O(logN)이므로 결국 O(logN)임.)  
  * 알고리즘 책 추천 : The Art of Computer Programming, DONALD E.KNUTH (1974, 튜링 어워드)  

## 3. Performance Analysis
 **1) 왜 알고리즘을 분석해야 할까?**
  - 성능을 분석해서 알고리즘을 비교하려고
  - 확실한 보증을 제공해서 버그를 피하려고
  - 이론적 기반을 이해하여 더 좋은 성능을 제공하려고  
 **2) 성능을 측정하는 방법 - Time Complexity**
  - 실제 시간? 시간은 불안정하다.  
    왜냐하면 Input data, 컴퓨터, 언어, 컴파일러 등에 의존적이기 때문이다.
  - 수학적 모델을 사용하자 ( sum of cost * frequency for all operations)
  - 하지만 정확하게 계산할 필요는 없다. 우리가 알 필요가 있는 것은 정확한 측정이 아니라 최악의 측정이다.
  - 점근 근사법(Asymptotic Complexity)를 이용하여 근사치를 구하자.  
   (1) Big Oh : upper bound, 가장 큰 계수.  
   (2) Big Omega : lower bound  
   (3) Big Theta : more precise  
   (4) Little oh : tight  
   => 주로 worse case인 빅오를 사용하여 측정한다.  
 **3) 빠른 컴퓨터 VS 빠른 알고리즘**
  - 컴퓨터는 무어의 법칙 때문에 조금씩 좋아지지만,
    알고리즘은 아예 polynomial이냐 exponential이냐에 따라 확실한 차이가 있기에,  
    알고리즘 승.  
 **4) PRIMES is in P**
  - 이 문제는 O(n^12)로 풀 수 있고, 현재 나와있는 최고는 O(n^6)이라 한다.
 **5) 점근 근사법의 단점**
  - 계수와 인풋 사이즈에 따라 달라진다. (n이 작은 수 일 때, 100000n이 n^2보다 항상 좋다고 할 수 없음)
  - 연산마다 메모리 접근 시간이 다름... (특히 하드웨어와 통하는 연산은 훨씬 오래..)  
 **6) 공간 복잡성 (Space Complexity)**
  - 메모리와 연관
  - 데이터 오브젝트의 수로 계산한다.  

## 4. 리스트
 **1) Linear List : 원소에 순서를 가진 자료 구조**
 **2) Linear List operations**
  - Lengh( ) : 자료 길이
  - Retrieve( Index ) : 데이터 검색
  - IndexOf( Element ) : 인덱스 검색
  - Delete( Index ) : 데이터 삭제
  - Insert( Index, Element ) : 데이터 삽입  
 **3) Static List : array라고 부름.**
  - index로 직접 접근할 수 있다.
  - capacity를 가진다.
  - insert, delete, resize가 느리다. (O(N))  
 **4) Dynamic List : Linked List라고 부름.**
  - 포인터로 구현한다.
  - 여러 형태가 있다. (단일연결, 이중연결, 정렬, 비정렬..)
  - 각 아이템은 값과 다음 아이템의 주소를 가진다.

## 5. 배열
 **1) 특징**
  - 메모리에 연속적으로 같은 사이즈로 이루어져있다.  
 **2) 속도**
  - 접근 : 항상 O(1)
  - Add : 끝은 O(1) 이지만, 앞쪽은 O(N)
  - Remove : 끝은 O(1) 이지만, 앞쪽은 O(N)  
 **3) 응용 - Sparse Matrix : 0이 아닌것 보다 0이 많은 행렬**
  => (row, column, value) 리스트를 이용하면 많은 memory를 아낄 수 있음.
  => ex. Daigonal, Lower Triangular 등.
 ※ N차 배열에 접근하기 위한 메모리는?

## 6. 스택 (Stack)
 **1) 개념**
  - 쌓아올림. Top, Bottom
  - LIFO (Last In First Out)
  - 연산 : IsEmpty, IsFull, Top, Push, Pop  
 **2) Dynamic**
  - 얼마나 쌓을지 모르기 때문에 포인터를 저장한다.
  - 더블링(Doubling) : 꽉 찰 때마다 배열을 2배씩 할당한다.  
  => Complexity : push가 꽉 찰때만 O(2^k), 꽉 안찼을 때는 O(n)  
  => C++에서는 vector, Java에서는 ArrayList, Python에서는 list가 있다.  
 **3) 응용 - Parentheses Matching**
  - 왼쪽부터 오른쪽까지 ( 가 나오면 스택에 넣고, ) 가 나오면 스택에서 뺀다.  
 **4) 응용 - Rat in a Maze**
  - 4가지 방향(오른쪽, 아래, 왼쪽, 위)의 순서를 정하고 미로를 탈출한다.  
 **5) 응용 - Method Invocation and Return**
  - 함수도 모두 스택으로 관리 된다.  
 **6) Recursion (순환)**
  - 스택은 주로 순환을 위해 사용된다.
  - Fibonacci, Towers of Hanoi ...

## 7. 큐 (Queue)
 **1) 개념**
  - 컨베이어 벨트, front, rear
  - FIFO (First-In, First Out)
  - 연산 : IsFullQ, IsEmptyQ, AddQ, DeleteQ  
 **2) 배열을 이용한 큐**
  - Add는 O(1)이지만, Delete는 O(N)이다.
  - Circular Array를 이용하면, Delete도 O(1)이다.  
 **3) 응용 : Lee's Wire Router**
  - Stack에서 쥐 미로찾기의 shortest path 알고리즘..

## 8. 링크드 리스트 (Linked List)
 **1) 개념**
  - 포인터를 이용하여 서로 연결한 리스트
  - first에는 첫 아이템의 주소가 들어있다.
  - 마지막 아이템의 주소에는 NULL이 들어있다.
  - 연산 : get, delete, insert  
 ※ 링크드 리스트 조작은 코딩 인터뷰 단골 문제.  
     ex) Reverse(Invert), Concatenate, Length...  
 **2) Header Node**
  - 헤더 노드를 따로 만들면, insert/delete때 편리하다.  
 **3) 응용 - Polynomials**
  - 다차원 방정식을 리스트로 나타낼 수 있다.
  - 다차원 방정식 2개 더하는 것 : O(m+n) // m,n은 각 방정식 항의 개수  
 **4) 이중 원형 리스트 (Dobly Linked Circular List)**
   - worse case의 복잡도가 절반으로 줄어든다.
   - 여기에 Header Node까지 포함하면 더 좋음.
   - Empty의 경우 구현 주의.  
 **5) 리스트 VS 배열**
  - 다뤄야 할 사이즈를 알고 있다 : 배열  
    다뤄야 할 사이즈를 모른다 : 리스트  
  - 주로 읽기와 업데이트를 한다 : 배열  
    주로 삽입과 삭제를 한다 : 리스트  

## 9. 수학적 표현
 **1) 3가지 요소 : Operators(연산자), Operands(피연산자), Delimiters(구획문자)**
 **2) 연산자의 Degree : Binary ( a+b 이런거), Unary ( +g 이런거 )**
 **3) Infix Form 와 Postfix Form**
  - Infix Form : a+b  // Parse가 어려움
  - Postfix Form : ab+ // Unary 연산자들은 @나 ?로 바꿔서 표현  
 * Infix = (a+b)*(c-d)/(e+f)  
   Postfix = ab+cd-*ef+/  
 => postfix로 바꾸면 Stack에 넣어서 계산하기 쉬움.  
 **4) Infix to Postfix Confersion**
  - 피연산자는 바로 output으로 넣음.
  - 연산자는 일단 stack에 넣음
  - 근데 stack에 넣을때 만약 우선순위가 더 높거나 같은 애가 있으면 걔는 빼고 넣음
  - 다 읽었으면 stack에서 다 빼서 output에 넣음.
  - )가 있으면 괄호 안에 있는거 다 처리해야됨.
  - 우선순위 : *,/  > +,-  > (  
**5) Prefix Form**
  - Infix Form = a+b  
    Postfix Form = ab+  
    Prefix Form = +ab  
**6) Infix to Prefix Conversion**
  - 일단 postfix로 바꾼다
  - 뒤집는다.  
 **7) Binary Tree Form**
  - 트리로 만들면 보기 좋고, 효율적이다.

## 10. 트리 (Tree)
 **1) Linear List vs Tree**
  - Linear List : 일련의 데이터에 쓰기 유용하다.
  - Tree : 계층적인 데이터에 쓰기 유용하다. (ex. 회사의 사원도, 컴퓨터의 파일)  
 **2) 트리의 특징과 용어**
  - 커넥티드 그래프이다.
  - 사이클이 없는 그래프이다.
  - 맨 위는 root, 맨 아래는 leaves 다.
  - 트리는 서브 트리로 이루어져있다.
  - root는 레벨1 (또는 0)이다. 그 밑은 레벨 2, 3, 4 ...
  - 레벨 = height = depth
  - Node Degree : 자식의 수, Tree Degree : 트리에서 Max Node Degree
  - 같은 레벨의 노드는 형제(sibling), 그 노드부터 root까지는 선조(ancestor), 그것의 서브트리에 속하는 노드는 자손(descendant)  
 **3) 가장 안좋은 트리**
  - 한쪽으로 쭉 기울어진 트리..
  - 노드가 최소인 트리
  - 노드의 수와 높이가 같은 트리  
 **4) 트리의 성질**
  - root를 제외한 모든 노드는 정확히 하나의 부모를 갖고 있다.
  - n개의 노드를 가진 트리는 n-1개의 간선(edge)이 있다.
  - 각 노드에서 root까지는 정확히 1개의 path가 있다.  
 **5) 이진 트리 (Binary Tree)**
  - 노드가 n개 일 때, 총 n+1개의 leaves가 있다.
  - 깊이가 k일 때, 최대 2^k - 1 개의 노드가 있을 수 있다.
  - Full binary tree : 각각의 노드가 leaf 거나 2개의 자식을 갖는 경우
  - Complete binary tree : 왼쪽부터 쭉 차있는 경우  
 **6) Representation**
  - Array로 하면 불필요한 공간이 많아지고 삽입/삭제가 어려우므로 링크드 리스트로 만든다.
  - data, leftChild, rightChild를 갖는 노드를 연결한다.  
 **7) Traversal**
  - VLR(Preorder), LVR(Inorder), LRV(Postorder), Level order 이렇게 4가지 방식이 있다. (V:Visit, L:Left, R:Right)
  - 응용 : 트리 복사하기, ★높이 구하기, 노드의 개수 구하기
  - 순환 함수를 잘 이용하자.
  - 하지만 순환 함수를 사용하면 메모리가 많이 필요하고 속도가 느리다.
    Iterative하게 Stack을 이용해서 구현할 수도 있다.
  - Complexities : time - O(N)  // N : 노드,    space - O(n) // n : 최고 높이
  - Level order : 큐를 이용해서 구함.  
 **8) Binary Tree Construction**
  - 자식이 한 개일 때, 왼쪽인지 오른쪽인지 잘 구별해야함.
  - preoder, postoroder, inorder, level order를 이용해서 잘 구별하자. (퀴즈 푸는 것 처럼..)

## 11. BST (Binary Search Tree)
 **1) Search tree (검색 트리)**
  - 보통 검색 트리는 딕셔너리를 구현하기 위해 사용된다.
  - 리스트와 해쉬 테이블보다 성능이 좋다.  
 **2) BST의 특징**
  - 원래 트리는 비어있을 수 없지만, BST는 비어있어도 된다.
  - 각각의 노드는 (Key, Value) 쌍으로 되어있다.
  - 자신의 왼쪽 서브트리의 Key들은 자신보다 작거나 같아야하며, 오른쪽은 크거나 같아야 한다.  
 **3) 연산자**
  - IsEmpty : O(1)
  - Search, Insert, Delete : 최악 O(n), 보통 O(log n = Height)
  - 다른건 다 쉽지만, Degree 2 Node를 Delete하는게 좀 어려움.
    이거는 자기랑 가장 비슷한 작은 걸 올려놓으면 됨.  
 **4) Indexed Binary Search Tree**
  - 여기서 Index라는건 자기의 왼쪽 서브트리의 노드의 수를 적어놓는 것을 의미함.
  - 그러면 Rank를 구할 수 있고, Search, Insert 등을 Index로 할 수 있음.
    ex. 5번째 큰 애를 찾아라.  10번째에 m을 넣어라
  - Rank 구할 때 오른쪽 자식으로 가면 Index를 더하면 됨. 그리고 마지막에 자기 자신을 더함.
  - 업데이트가 되면 쭉 올라가면서 내가 왼쪽 자식인 선조들만 1을 증가시키면 됨.

## 12. Graph (그래프)
 **1) 그래프의 특징**
  - V는 정점(노드) 집합, E는 간선(링크, edge) 집합.
  - Undirected와 Directed가 있음  
 **2) Undirected 그래프의 특징**
  - n개의 정점이 있으면 그 쌍은 n(n-1)개임, 그러나 undirected이므로 2로 나눠서 n(n-1)/2임
  - complete가 아닌 이상 항상 n(n-1)/2 이하임  
 **3) Directed 그래프의 특징**
  - n(n-1)이하임  
 **4) Vertex Degree**
  - 몇 개가 연결되어 있는가.
  - In-Degree : 나에게 들어오는 것은 몇 개인가?
  - Out-Degree : 내가 나가는 것은 몇 개인가?  
 **5) 응용 : Graph Coloring**
  - 인접한 노드끼리는 다른 색을 칠하는 것, 최소 몇 개를 칠해야 할까?
  - 평탄성(Planarity) : edge들끼리 서로 교차하지 않는 것.
  - Kuratowski's Theorem에 의하면 K5, K3,3 두 형태의 그래프 중 어느 하나라도 포함 하지 않고 있으면   
    평탄성이 유지된다.  
  - 결국 저렇게 바꿔서 하면 된다.. (?)  
 **6) 그래프의 여러가지 문제들**
  - Path Problems : 어떤 길로 가야 좋을까
  - Connected Components : 갈 수 있는 요소들을 Connected 되어있다한다.
  - Spanning tree : 그래프의 모든 노드를 포함하는 트리  
   => MST (Minimum Cost Spanning Tree)  
 **7) Adjacency Matrix**
  - 그래프를 행렬로 표현해보자.
  - 대각선은 모두 0이고, 연결되어있는 것들은 1로 표현하자.
  - Undirected graph는 대칭임.
  - 공간 : N^2, find degree : O(N)  
 **8) Adjacency List**
  - 그래프를 리스트로 표현해보자.
  - 모든 노드에 대해 배열을 만들고, 각 노드에 연결된 것들만 리스트로 추가
  - 공간 : N+e 또는 N+2e  
 **9) Graph Search Methods**
  - 그래프를 탐색해보자.
  - DFS(Depth-First Search) :  계속 파고들음, 인접행렬 : O(n^2), 인접리스트 : O(n+e)  
    이걸로 Connected 된 요소들을 알 수 있다.
  - BFS(Breadth-First Search) : 레벨별로 큐를 이용해서, O(n + e)
  - DFS와 BFS는 복잡도는 똑같고 결과도 같다.

## 13. MST(Minimum Spanning Tree)
 **1) MST?**
  - 그래프에 Cost(Weight)가 있고, 모든 노드를 들리지만 가장 적은 Cost로 들리는 트리
  - 필요없는 나뭇가지를 쳐내듯한다고 해서 Spaning Tree  
 **2) Kruskal's Method**
  - 처음에 노드만 있고 엣지는 없는 걸로 시작함.
  - 가장 적은 Cost부터 연결하기 시작.
  - 이 때, 사이클이 생긴다면 연결하지 않음. (이미 더 좋은 길이 있다는 소리임)
  - n-1개의 엣지를 연결했다면 멈춤.
  - 모든 cost가 다를때 MST는 유니크함
  - O(nlogn + eloge)  
 **3) Prim's Method**
  - 크루스칼처럼 노드만 있고 엣지는 없는 걸로 시작함.
  - 한개의 노드를 추가시키고 그 노드랑 연결된 것 중에 cost가 제일 낮은거 연결.
  - 그 연결된 노드도 추가시키고 가장 cost 낮은거 연결...
  - N-1개의 엣지를 연결했다면 멈춤.
  - 배열 : O(n^2),  바이너리 힙 : O(elogn), 피보나치 힙 : O(e+nlogn)
  - 즉, 피보나치 힙 프림 > 바이너리 힙 프림 > 크루스칼 > 배열 프림  
 **4) Sollin's Method**
  - 모든 노드를 각각 그룹으로 설정한 뒤
  - 가장 cost가 낮은것들을 다 연결한뒤 그룹핑을 다시 함.
  - 결국 1개의 그룹이 될 때까지 계속 하면 됨.
  - 병렬 컴퓨팅에 유리함.

## 14. 소팅 (Sorting)
 **1) Selection Sort (선택 정렬)**
  - 가장 가까운 곳에 꽂아 넣음.
  - O(n^2)  
 **2) Quick Sort (퀵정렬)**
  - pivot을 설정해서 계속 분할하면 됨.
  - pivot은 맨 왼쪽, 중간, 맨 오른쪽 이렇게 3개 골라가지고 Median을 pivot으로 설정하면 됨.
  - 쉽게 새로 메모리 설정해서 하는 것도 가능하지만, In-Place도 가능함. (양쪽에 화살표 찍고 Swap을 이용해서)
  - O(nlogn)  
 **3) Merge Sort (병합 정렬)**
  - 반 씩 쪼갠 뒤 정렬하며 합친다.
  - 각 레벨은 O(n) 만큼이 필요하고, 레벨은 logn개 임.
  - O(nlogn) 
  - Natural Merge Sort라고 자를때 정렬된것만큼은 묶고 자르는것도있음..  
 **4) Merge Sort VS Quick Sort**
  - Space : 퀵은 O(1), 머지는 O(n)
  - Time : 퀵은 평균 O(nlogn), 머지는 항상 O(nlogn)
  - 언어 : 퀵은 C/C++, 머지는 Java   (왜냐하면 머지소트가 비교 연산이 적은데, 자바는 비교 연산이 비싸서 적은걸 선호함)  
 **5) 그 외 정렬**
  - Bubble Sort, Insertion Sort, Shell Sort...

## 15. 해쉬 (Hash)
 **1) Dictionary**
  - pair는 다른 key를 갖는다. pair = (key, element)
  - 연산자 : Search, Delete, Insert   
 **2) Hash Tables**
  - Search, Insert, Delete : 최악 O(size) -> 최선 O(1)
  - 배열은 table이라 부르며, 배열의 각 포지션을 bucket이라 부른다.
  - 해쉬 함수 f는 키 k를 위한 home bucket이다.  
 **3) Problem**
  - 이미 자리가 점유되어있는데 또 들어가야한다면? => collision  
  => 최소화하기 이해 노력해야한다.  
  - index의 범위를 넘는 곳에 들어가야한다면? => overflow  
  => 새로운 공간을 마련해 주어야 한다.  
 **4) 좋은 해쉬 함수**
  - 나머지를 사용 + 나누는 수는 소수(prime number)를 사용한다.  
 **5) Linear Probing**
  - 넣어줄 자리가 없을 때 다음 bucket에 넣는다.
  - 평균적으로 최대 75%는 차지 않도록 해야 성능이 좋다.  
 **6) Quadratic Probing**
  - 넣어줄 자리가 없을 때 좌우의 2의 제곱 순으로 간격을 띄워서 채운다.  
 **7) Rehasing**
  - 넣어줄 자리가 없을 때 또 다른 새로운 해쉬 함수를 사용한다.  
 **8) Sorted Chains**
  - 배열 + 링크드 리스트..  같은 bucket에 넣어야할 경우 링크를 달아서 노드를 추가한다.
  - 성능 : 사이즈가 a일때, search나 insert는 1+(a/2)  

## 16. 우선순위 큐 (Priority Queue)
 **1) 특징**
  - Binary heap을 사용한다.
  - empty, size, top은 O(1)만에 가능
  - insert, remove는 O(logn)만에 가능 // n은 size
  - Complete Binary Tree
  - 배열에 넣을 때 index 1부터 넣는다. (노드의 고유번호 값과 일치시키려고)  
 **2) 힙소트**
  - 하나씩 빼서 정렬하면 그게 힙소트
  - 우선순위 큐(max/min heap) 만드는거 O(n) 
  - 빼는거 O(logn), n번 해야되니까 O(nlogn)
  - 즉, O(nlogn)으로 merge,quick이랑 같다.
  - In-place로 할 수 있음. (배열 끝으로 계속 보내면 됨) -> 공간복잡도 : O(1)  
 **3) Heapify**
  - 힙이 되도록 하는 것. (맨 위에 max/min을 올려놓는것)
  - 바꿀 자식이 없을 때 까지 계속 밑으로 내려감.  
 **4) 응용 : Machine Scheduling**
  - 여러개의 기계를 가장 효율좋게 돌리는 문제 -> NP-hard
  - LPT schedules로 하면 최적은 아니더라도, 합리적인 스케쥴링이 가능함.
  - O(nlogn + mn)
  - PQ를 사용하면 O(nlog(mn))

## 17. AVL Tree
 **1) ABL**
  - Georgy Adelson-Velsky and Landis' tree (그래서 AVL..)
  - Self-balancing binary tree (계속 밸런싱을 맞춤)  
 **2) Operation**
  - BST는 삽입/삭제가 보통 O(log n), 그리고 최악의 경우(밸런스가 한쪽으로 치우쳐져있을 경우)에 
    O(n)이 되는데
  - AVL은 최악의 경우에도 O(log n)을 보장함.
  - 심지어 그 좋다는 Hash Table도 O(log n)을 보장하지 못하는데... ( 다틀렸을때 O(n)임..)  
 **3) Balance Factors**
  - 양쪽 서브 트리의 높이 차이에 대한 정보
  - 각 노드에 -1 , 0 , 1을 심는다.  
 **4) Rotation**
  - RR, LR, RL, LL이 존재한다.  
 **5) but...**
  - RB Tree 만큼 효율이 좋지 않아서 딱히 안쓰인다고...  

