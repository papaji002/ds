class Mystack:
	def __init__(self,n):
		self.items = []
		self.size = n
		self.tos = -1
	def count(self):
		return len(self.items)
	def isempty(self):
		return self.items == []
	def isfull(self):
		return len(self.items) == self.size
	def push(self,data):
		assert len(self.items)<self.size,"STACK OVERFLOW"
		self.tos = self.tos+1
		self.items.append(data)
	def pop(self):
		assert len(self.items)>=0,"STACK UNDERFLOW"
		x = len(self.items)
		x = x-1
		return self.items[x]
		self.tos -=1
	def show(self):
		self.tos = len(self.items)-1
		while self.tos>=0:
			print(self.items[self.tos])
			self.tos = self.tos -1
#MAIN
phones = Mystack(4)
phones.push("IPHONE")
phones.push("SAMSUNG")
phones.push("OPPO")
phones.push("REDMI")
phones.show()
phones.pop()
print(phones.isfull())
print(phones.isempty())