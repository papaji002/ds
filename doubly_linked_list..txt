class Node:
    def __init__(self,data=0,p=None,n=None):
        self.data = data
        self.prev =p
        self.next = n
head = None;first = None;temp = None;tail = None;
def add_node(k:int):
    global head,first,temp,tail
    ptr = Node(k)
    if head == None:
        head = ptr
        first = head
        tail = head
    else:
        temp = ptr
        first.next = temp
        temp.prev = first
        first = temp
        tail = temp
def traverse():
    global head,first,temp,tail
    ptr = head
    while ptr!=None:
        print(ptr.data)
        ptr = ptr.next
    print()
def insert_at_begin(k:int):
    global head,first,temp,tail
    ptr = Node(k)
    if head == None:
        first = ptr
        first = head
        tail = head
    else:
        temp = ptr
        temp.next = head
        head.prev = temp
        head = temp
def insert_at_end(k:int):
    global head,first,temp,tail
    ptr = Node(k)
    if head == None:
        first = ptr
        first = head
        tail = head
    else:
        temp = ptr
        temp.prev = tail
        tail.next = temp
        tail = temp
def insert_at_position(k:int,pos:int):
    global head,first,temp,tail
    src = head
    while pos:
        pos = pos-1
        src = src.next
    ptr = Node(k)
    ptr.next = src
    ptr.prev = src.prev
    src.prev.next = ptr
    src.prev = ptr

#MAIN
add_node(14)
add_node(8)
add_node(22)
traverse()
insert_at_begin(7)
traverse()
insert_at_end(17)
traverse()
insert_at_position(19,3)
traverse()

