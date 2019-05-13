---
title: "자료구조 개념 정리"
date: 2019-05-13 00:43:28 -0400
categories: jekyll update
---

# 자료구조

## 1. Course overview
 1) 자료구조는 왜 중요할까?
  - 데이터를 어떻게 표현할 지, 어떻게 조작을 할 수 있을 지, 알기 위해서 자료구조를 알아야 합니다.
  - 특히, 알고리즘은 여러가지 데이터의 표현과 조작을 필요로 합니다.
 2) 알고리즘 vs 자료구조
  - 알고리즘 : 문제를 해결하는 방법 (ex. 낚시)
  - 자료구조 : 정보를 저장하는 방법 (ex. 낚시채, 그물망 ...)
 3) 알고리즘 + 자료구조는 ?
  - 알고리즘 + 자료구조 = 프로그램
  - Niklaus Wirth가 한 말이다. (1984 튜링 어워드)

## 2. Introduction
 1) 알고리즘
  - 알고리즘은 음식 레시피와 같다. (어떻게 어떻게 하면 음식이 완성됨!)
  - 알고리즘은 유한개의 지시문(Instruction) 모음이다.
  - 알고리즘은 정의할 수 있어야하며, 효율적이어야한다.
 2) 데이터 타입
  - 실제 세계에서 어떤것을 표현하기 위한 데이터의 모음
  - 각 프로그래밍 언어들은 기본적인 데이터 타입을 제공한다. (int, char, float ...)
 3) 자료구조
  - 자료구조는 데이터의 논리적 구성이다.
  - C언어는 기본적으로 데이터를 묶어주는 메커니즘인 structure와 array를 제공한다.
 4) ADT (Abstract Data Type, 추상 데이터 타입)
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
 5) Search
 - 선형 탐색 (Linear Search = Sequential Search)
   장점 : 이해하기 쉽다.. 구현하기 쉽다..
   단점 : 느리다.. O(N)
 - 이진 탐색 (Binary Search)
   장점 : 빠르다.. O(logN)
   단점 : 정렬이 되어있어야한다. (but 정렬도 O(logN)이므로 결국 O(logN)임.)
  * 알고리즘 책 추천 : The Art of Computer Programming, DONALD E.KNUTH (1974, 튜링 어워드)

## 3. Performance Analysis
 1) 왜 알고리즘을 분석해야 할까?
  - 성능을 분석해서 알고리즘을 비교하려고
  - 확실한 보증을 제공해서 버그를 피하려고
  - 이론적 기반을 이해하여 더 좋은 성능을 제공하려고
 2) 성능을 측정하는 방법 - Time Complexity
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
 3) 빠른 컴퓨터 VS 빠른 알고리즘
  - 컴퓨터는 무어의 법칙 때문에 조금씩 좋아지지만,
    알고리즘은 아예 polynomial이냐 exponential이냐에 따라 확실한 차이가 있기에,
    알고리즘 승.
 4) PRIMES is in P
  - 이 문제는 O(n^12)로 풀 수 있고, 현재 나와있는 최고는 O(n^6)이라 한다.
 5) 점근 근사법의 단점
  - 계수와 인풋 사이즈에 따라 달라진다. (n이 작은 수 일 때, 100000n이 n^2보다 항상 좋다고 할 수 없음)
  - 연산마다 메모리 접근 시간이 다름... (특히 하드웨어와 통하는 연산은 훨씬 오래..)
 6) 공간 복잡성 (Space Complexity)
  - 메모리와 연관
  - 데이터 오브젝트의 수로 계산한다.

## 4. 리스트
 1) Linear List : 원소에 순서를 가진 자료 구조
 2) Linear List operations
  - Lengh( ) : 자료 길이
  - Retrieve( Index ) : 데이터 검색
  - IndexOf( Element ) : 인덱스 검색
  - Delete( Index ) : 데이터 삭제
  - Insert( Index, Element ) : 데이터 삽입
 3) Static List : array라고 부름.
  - index로 직접 접근할 수 있다.
  - capacity를 가진다.
  - insert, delete, resize가 느리다. (O(N))
 4) Dynamic List : Linked List라고 부름.
  - 포인터로 구현한다.
  - 여러 형태가 있다. (단일연결, 이중연결, 정렬, 비정렬..)
  - 각 아이템은 값과 다음 아이템의 주소를 가진다.

## 5. 배열
 1) 특징
  - 메모리에 연속적으로 같은 사이즈로 이루어져있다.
 2) 속도
  - 접근 : 항상 O(1)
  - Add : 끝은 O(1) 이지만, 앞쪽은 O(N)
  - Remove : 끝은 O(1) 이지만, 앞쪽은 O(N)
 3) 응용 - Sparse Matrix : 0이 아닌것 보다 0이 많은 행렬
  => (row, column, value) 리스트를 이용하면 많은 memory를 아낄 수 있음.
  => ex. Daigonal, Lower Triangular 등.
 ※ N차 배열에 접근하기 위한 메모리는?

## 6. 스택 (Stack)
 1) 개념
  - 쌓아올림. Top, Bottom
  - LIFO (Last In First Out)
  - 연산 : IsEmpty, IsFull, Top, Push, Pop
 2) Dynamic
  - 얼마나 쌓을지 모르기 때문에 포인터를 저장한다.
  - 더블링(Doubling) : 꽉 찰 때마다 배열을 2배씩 할당한다.
  => Complexity : push가 꽉 찰때만 O(2^k), 꽉 안찼을 때는 O(n)
  => C++에서는 vector, Java에서는 ArrayList, Python에서는 list가 있다.
 3) 응용 - Parentheses Matching
  - 왼쪽부터 오른쪽까지 ( 가 나오면 스택에 넣고, ) 가 나오면 스택에서 뺀다.
 4) 응용 - Rat in a Maze
  - 4가지 방향(오른쪽, 아래, 왼쪽, 위)의 순서를 정하고 미로를 탈출한다.
 5) 응용 - Method Invocation and Return
  - 함수도 모두 스택으로 관리 된다.
 6) Recursion (순환)
  - 스택은 주로 순환을 위해 사용된다.
  - Fibonacci, Towers of Hanoi ...

## 7. 큐 (Queue)
 1) 개념
  - 컨베이어 벨트, front, rear
  - FIFO (First-In, First Out)
  - 연산 : IsFullQ, IsEmptyQ, AddQ, DeleteQ
 2) 배열을 이용한 큐
  - Add는 O(1)이지만, Delete는 O(N)이다.
  - Circular Array를 이용하면, Delete도 O(1)이다.
 3) 응용 : Lee's Wire Router
  - Stack에서 쥐 미로찾기의 shortest path 알고리즘..

## 8. 링크드 리스트 (Linked List)
 1) 개념
  - 포인터를 이용하여 서로 연결한 리스트
  - first에는 첫 아이템의 주소가 들어있다.
  - 마지막 아이템의 주소에는 NULL이 들어있다.
  - 연산 : get, delete, insert
 ※ 링크드 리스트 조작은 코딩 인터뷰 단골 문제.
     ex) Reverse(Invert), Concatenate, Length...
 2) Header Node
  - 헤더 노드를 따로 만들면, insert/delete때 편리하다.
 3) 응용 - Polynomials
  - 다차원 방정식을 리스트로 나타낼 수 있다.
  - 다차원 방정식 2개 더하는 것 : O(m+n) // m,n은 각 방정식 항의 개수
 4) 이중 원형 리스트 (Dobly Linked Circular List)
   - worse case의 복잡도가 절반으로 줄어든다.
   - 여기에 Header Node까지 포함하면 더 좋음.
   - Empty의 경우 구현 주의.
 5) 리스트 VS 배열
  - 다뤄야 할 사이즈를 알고 있다 : 배열
    다뤄야 할 사이즈를 모른다 : 리스트
  - 주로 읽기와 업데이트를 한다 : 배열
    주로 삽입과 삭제를 한다 : 리스트

