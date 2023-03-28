class node:
	def __init__(self,data):
		self.data=data
		self.next=None
class linklist:
	def __init__(self):
		self.head=None
	def prepend(self,data):
		new_node=node(data)
		new_node.next=self.head
		self.head=new_node
#2.append to add new node at the end
	def append(self,new_data):
		new_node=node(new_data)
		if self.head is None:
			self.head=new_node
			return
		last=self.head
		while(last.next):
			last=last.next
		last.next=new_node
#to print display linked list
	def display(self):
		current=self.head
		while current.next:
			print(current.data)
			print(" _______")
			current=current.next

#insert
	def insert(self,prev_node,new_data):
		if prev_node is None:
			print("the given previous node is not present")
			return
		new_node=node(new_data)
		new_node.next=prev_node.next
		prev_node.next=new_node

	def delete_first(self,data):
		temp=self.head
		if temp is not None:
			if temp.data==data:
				self.head=temp.next
				temp=None
				return
		while temp is not None:
			if temp.data==data:
				break
			prev=temp
			temp=temp.next

		if temp==None:
			return
		prev.next=temp.next
		temp=None	
	

	def count(self):
		ctr=0
		current=self.head
		while current:
			ctr=ctr+1
			current=current.next
		print("total count is",ctr)


	def reverse(self):
		prev=None
		current=self.head
		while(current is not None):
			next=current.next
			current.next=prev
			prev=current
			current=next
			self.head=prev

	def sort(self):
		current=self.head
		temp=None
		while current:
			temp=current.next
			while temp is not None:
				if current.data<temp.data:
					prev=current.data
					current.data=temp.data
					temp.data=prev
				temp=temp.next
			current=current.next
	

#main

mylist=linklist()

mylist.prepend("a")
mylist.prepend("b")
mylist.prepend("c")
mylist.prepend("d")
mylist.prepend("e")
mylist.display()

print ("after append")

mylist.append("f")
#mylist.append(None)
mylist.display()
print("after insert")
mylist.insert(mylist.head.next,"1")
mylist.display()
print("Delete")
mylist.delete_first("e")
mylist.display()
mylist.count()
mylist.display()
print("Reverse")
mylist.reverse()
mylist.display()
print("Sort")
mylist.sort()
mylist.display()



