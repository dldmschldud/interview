## Python으로 연결리스트(LinkedList)구현하기

### LinkedList
 
노드 : 연결리스트에서 각각의 원소
 * 데이터
 * 링크 : 다음노드를 가리키는(참조하는) 포인터

<pre>
<code>
from __future__ import annotations
from typing import Any

class Node:
  """연결리스트용 노드 클래스"""

  def __init__(self,data:Any=None,next:Node=None):
    self.data=data
    self.next=next

class LinkedList:
  """연결리스트 클래스"""
  
  def __init__(self)->None:
    self.no=0       #연결리스트에 등록된 노드의 개수
    self.head=None  #머리 노드에대한 참조(머리노드가 아님)

  def __len__(self)->int:
    """연결리스트의 노드 개수를 반환"""
    return self.no 

  def add_first(self,data:Any)->None:
    """맨 앞에 노드를 삽입"""

    ptr=self.head
    self.head=Node(data,ptr)   #맨 앞에 삽입된 노드가 삽입전 머리노드를 가리키게함
    self.no+=1

  def add_last(self,data:Any):
    """맨 뒤에 노드를 삽입"""

    #노드가 없을때 
    if self.head is None:
      self.add_first(data)  #맨 앞에 노드를 삽입
    
    else:
      ptr=self.head
      while ptr.next is not None: #삽입할 곳을 찾기
        ptr=ptr.next
      ptr.next=Node(data,None)  #맨 뒤에 노드를 삽입
      self.no+=1


  def remove_first(self)->None:
    """머리 노드를 삭제"""
    if self.head is None:
      print("삭제할 노드가 없습니다")

    else:
      ptr=self.head.next
      self.head=ptr
      self.no-=1

  def remove_last(self):
    """꼬리 노드를 삭제"""

    if self.head is None:
      print("삭제할 노드가 없습니다")

    else:
      if self.head.next is None:
        self.remove_first()
      else:
        ptr=self.head
        pre=ptr

        while ptr.next is not None:
          pre=ptr
          ptr=ptr.next
        pre.next=None
        self.no-=1

  def remove_all(self):
    """모든 노드를 삭제"""
    self.head=None
    self.no=0

  def print_all(self):
    """모든 노드를 출력"""

    ptr=self.head
    print("[ ",end="")
    while ptr is not None:
      print(ptr.data,end= " ")
       
      ptr=ptr.next
    print("]")

  def find(self, data: Any) -> int:
    """노드 검색"""
    count=0
    ptr = self.head
    while ptr is not None:
        if ptr.data == int(data):
            return count
        else:
            count += 1
            ptr = ptr.next
    return -1

lst=LinkedList()

lst.add_first(1)
lst.add_first(2)

lst.print_all()
print(lst.__len__())
lst.remove_all()
lst.print_all()
print(lst.__len__())
lst.add_first(4)
lst.print_all()

a=lst.find(4)
if a>=0:
  print("해당 데이터가",a+1,"번째에 있습니다")
else:
  print("해당 데이터가 없습니다")
</code>
</pre>


