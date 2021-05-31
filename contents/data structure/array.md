# Data Structure


- [Array](#Array)
- [LinkedList](#LinkedList)
- [ArrayList](#ArrayList)

## Array

* 여러 데이터를 하나의 이름으로 그룹핑해서 관리하기 위한 자료구조
* 선언시 크기와 데이터 타입을 지정
* 메모리 공간상에서 연속적으로 이루어져있다
* 논리적 저장 순서와 물리적 저장순서가 일치해 인덱스로 해당 원소에 접근가능

  * 인덱스를 알고있으면 검색시 O(1) -> 인덱스를 통한 검색에 용이
  * random-access가능
* 삽입 삭제시 worst case - O(n)


## LinkedList

* 데이터 검색시 처음 노트부터 순회 -> O(n)
* 메모리 공간상에서 각 노드들이 연속적으로 이루어져있지 않다
* 다음 노드의 위치 정보만 가지고 있음
* 삽입, 삭제시 해당원소를 찾고 삭제해야하므로 O(n)

-> 삽입과 삭제가 많으면 linkedlist

-> 데이터 접근이 많으면 array


## ArrayList
* 배열과 달리 크기를 동적으로 바꿀수 있음
* 초기 설정된 capacity를 넘는 객체가 들어오면 크기를 1.5배로 증가시킴
* 데이터 검색시 용이하지만 삽입과 삭제가 느리다
#### java list collection

list는 collection인터페이스를 확장한 자료형으로 중복된 데이터 입력이 가능하며 순차적이고 다량의 데이터 입력시 주로 사용한다

ex) Vector, ArrayList, LinkedList
