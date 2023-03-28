class Node:
	def __init__(self,data):
		self.left=None
		self.data=data
		self.right=None
#to insert a node
	
	def insert(self,data):
		if self.data:
			if data<self.data:
				if self.left is None:
					self.left=Node(data)
				else:
					self.left.insert(data)
			else:
				if self.right is None:
					self.right=Node(data)
				else:
					self.right.insert(data)
		else:
			self.data=data

	def PrintTree(self):
		if self.left:
			self.left.PrintTree()
		print(self.data)
		if self.right:
			self.right.PrintTree()



	def preordertraversal(self,root):
		res=[]
		if root:
			res=self.inordertraversal(root.left)
			res.append(root.data)
			res+=self.inordertraversal(root.right)
		return res

	def inordertraversal(self,root):
		res=[]
		if root:
			res=self.postordertraversal(root.left)
			res.append(root.data)
			res+=self.inordertraversal(root.right)
		return res

	def postordertraversal(self,root):
		res=[]
		if root:
			res=self.postordertraversal(root.left)
			res+=self.postordertraversal(root.right)
			res.append(root.data)
		return res

	def findval(self,val):
		if val<self.data:
			if self.left is None:
				return str(val)+"NOT FOUND"
			return self.left.findval(val)
		else:
			if val>self.data:
				if self.right is None:
					return str(val)+"NOT FOUND"
				return self.right.findval(val)
		return str(self.data)+"IS FOUND"
	
			
			
	

a=Node(50)
a.insert(2)
a.insert(3)
a.insert(4)
a.insert(5)
a.PrintTree()
print(a.preordertraversal(a))		
print(a.inordertraversal(a))	
print(a.postordertraversal(a))	
print(a.findval(4))
print(a.findval(8))