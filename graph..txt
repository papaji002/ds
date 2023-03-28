class graph:
	def __init__(self,size):
		self.adjmatrix=[]
		for i in range(size):
			self.adjmatrix.append([0 for i in range(size)])
	def addedge(self,v1,v2):
		if v1==v2:
			print("self connected edge")
		self.adjmatrix[v1][v2]=1
		self.adjmatrix[v1][v2]=1
	def removeedge(self,v1,v2):
		if self.adjmatrix[v1][v2]==0:
			print("no edge exist")
		self.adjmatrix[v1][v2]=0
		self.adjmatrix[v2][v1]=0
	def printmatrix(self):
		for row in self.adjmatrix:
			for val in row:
				#print("{4}".format(row))
				print(row)
			print()

#main
a=graph(5)
a.addedge(0,1)
a.addedge(4,3)
a.addedge(1,2)
a.addedge(2,3)
a.printmatrix()
a.removeedge(2,3)
a.printmatrix()
 
