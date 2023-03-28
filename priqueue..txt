class priority_queue(object):
	def __init__(self):
		self.item=[]
		self.priority=[]
	def __str__(self):
		return "".join([str(i) for i in self.item])
	def isempty(self):
		return len(self.item)==0
	def enqueue(self,x,p):
		self.item.append(x)
		self.priority.append(p)                                                                                   #  \_(^_^)_/
	def dequeue(self):
		try:
			max=0
			for i in range(len(self.item)):
				if self.priority[i]<self.priority[max]:
					max=i
			item=self.item[max]
			del self.item[max]
			return item
		except IndexError:
			print()
			exit()
#Main
myqueue=priority_queue()
myqueue.enqueue("GPA",3)
myqueue.enqueue("LAPTOP",1)
myqueue.enqueue("Part time job",2)
print(myqueue)
while not myqueue.isempty():
	print(myqueue.dequeue())
