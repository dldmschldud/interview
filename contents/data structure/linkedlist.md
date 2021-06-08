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
    """초기화"""
    self.data=data    #데이터에 대한 참조 :임의의형, 생략할경우 None으로 간주
    self.next=next    #뒤쪽 노드에 대한 참조 :Node형, 생략할경우 Node으로 간주

class LinkedList:
  """연결리스트 클래스"""
  
  def __init__(self)->None:
    """초기화"""
    self.no=0           #연결리스트에 등록된 노드의 개수
    self.head=None      #머리노드(맨 앞에 있는 노드)에 대한 참조
    self.current=None   #현재 주목하고 있는 노드에 대한 참조
    
  def __len(self)->int:
    """연결리스트의 노드 개수를 반환"""
    return self.no

  def add_first(self,data:Any)->None:
    """맨앞에 노드를 삽입"""
    ptr=self.head
    self.head=self.current=Node(data,ptr) 
    self.no+=1


  def add_last(self,data:Any):
    """맨 끝에 노드를 삽입"""
    if self.head is None:
      self.add_first(data)  
    else:
      ptr=self.head
      while ptr.next is not None:   
        ptr=ptr.next
      ptr.next=self.current=Node(data,None)
      self.no+=1

  def remove_first(self)->None:
    """머리 노드를 삭제"""
    if self.head is not None:   #리스트가 비어있지 않으면
      self.head=self.current=self.head.next

    self.no -=1

  def remove_last(self):
    """꼬리 노드를 삭제"""
    if self.head is not None:
      if self.head.next is None:  #리스트의 노드가 하나인경우
        self.remove_first()
      
      else:
        ptr=self.head
        pre=self.head

        while ptr.next is not None:
          pre=ptr
          ptr=ptr.next

        pre.next=None
        self.current=pre
        self.no-=1

  def print(self)->None:
    """모든 노드를 출력"""
    ptr=self.head

    while ptr is not None:
      print(ptr.data)
      ptr=ptr.next
</code>
</pre>


