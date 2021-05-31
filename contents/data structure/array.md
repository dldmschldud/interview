# Data Structure


- [Array](#Array)
- [List](#List)
- [LinkedList](#LinkedList)
- [ArrayList](#ArrayList)


## Array & List
* 공통점 - 순서가 있는 요소들의 컬렉션
* 차이점 - 배열만 인덱스를 가진다
* 배열을 위해 할당된 메모리 공간은 연속적
* 배열의 모든 요소는 같은 크기를 가짐->첫번째 요소의 위치를 알면 다른 요소의 위치 계산 가능
* 리스트 요소의 메모리 주소는 연속적일수 있고 아닐수 있다
* 파이썬의 리스트 요소들은 메모리상의 연속적인 위치에 할당되며 인덱스를 사용한 접근이 가능하다 (array와 list중 array와 유사)
 * 파이썬에서 리스트와 튜플로 배열 구현가능


## Array

* 여러 데이터를 하나의 이름으로 그룹핑해서 관리하기 위한 자료구조
* 선언시 크기와 데이터 타입을 지정
* 메모리 공간상에서 연속적으로 이루어져있다
* 논리적 저장 순서와 물리적 저장순서가 일치해 인덱스로 해당 원소에 접근가능

  * 인덱스를 알고있으면 검색시 O(1) -> 인덱스를 통한 검색에 용이
  * random-access가능
* 삽입 삭제시 worst case - O(n)

## List

리스트구현

1) 배열을 이용한 구현 
* 검색 - O(1)
* 삽입/삭제 worst case - O(n)

2) 연결리스트를 이용한 구현
* 검색 - o(n)
* 삽입/삭제 - O(1) -> 하지만 삽입 위치, 삭제할 원소를 찾는데 O(n)


-> 삽입과 삭제가 많으면 linkedlist

-> 데이터 접근이 많으면 array

## LinkedList

연결리스트

* 노드의 집합
* 단순 연결리스트, 원형 연결리스트, 이중 연결리스트
*
* 데이터 검색시 처음 노트부터 순회 -> O(n)
* 메모리 공간상에서 각 노드들이 연속적으로 이루어져있지 않다
* 다음 노드의 위치 정보만 가지고 있음
* 삽입, 삭제시 해당원소를 찾고 삭제해야하므로 O(n)


## ArrayList
* 배열과 달리 크기를 동적으로 바꿀수 있음
* 초기 설정된 capacity를 넘는 객체가 들어오면 크기를 1.5배로 증가시킴
* 데이터 검색시 용이하지만 삽입과 삭제가 느리다
#### java list collection

list는 collection인터페이스를 확장한 자료형으로 중복된 데이터 입력이 가능하며 순차적이고 다량의 데이터 입력시 주로 사용한다

ex) Vector, ArrayList, LinkedList


참고

https://velog.io/@adam2/Array%EC%99%80-List%EA%B7%B8%EB%A6%AC%EA%B3%A0-Java-List#:~:text=%ED%95%98%EB%8A%94%20%EA%B2%83%EC%9D%B4%20%EC%A2%8B%EB%8B%A4.-,%EB%B0%B0%EC%97%B4%EA%B3%BC%20ArrayList%EC%9D%98%20%EC%B0%A8%EC%9D%B4,element%EB%A7%8C%20%EB%8B%B4%EC%9D%84%20%EC%88%98%20%EC%9E%88%EB%8B%A4.

https://github.com/JaeYeopHan/Interview_Question_for_Beginner/tree/master/DataStructure#array-vs-linked-list

https://velog.io/@choonghee-lee/%EB%B2%88%EC%97%AD-Array-vs.-List-vs.-Python-List#:~:text=%EB%91%98%EC%9D%98%20%EA%B0%80%EC%9E%A5%20%EA%B7%B9%EB%AA%85%ED%95%9C%20%EC%B0%A8%EC%9D%B4%EC%A0%90,%EB%A6%AC%EC%8A%A4%ED%8A%B8%EB%8A%94%20%EA%B7%B8%EB%A0%87%EC%A7%80%20%EC%95%8A%EB%8B%A4%EB%8A%94%20%EA%B2%83%EC%9D%B4%EB%8B%A4.&text=%EB%B0%B0%EC%97%B4%EC%9D%B4%20%EC%83%9D%EC%84%B1%EB%90%A0%20%EB%95%8C,%EC%9D%84%20%EB%A9%94%EB%AA%A8%EB%A6%AC%EC%97%90%20%ED%95%A0%EB%8B%B9%ED%95%B4%EC%A4%80%EB%8B%A4.
