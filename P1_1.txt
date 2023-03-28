class mynumber:
	def __init__(self,y):
		self.number=y
	def ispositive(self):
		if self.number>0:
			print("is positve")
		else:
			print("is negative")
	def isodd(self):
		if self.number%2==0:
			print("is a even number")
		else:
			print("is a odd number")
	def square(self):
		return(self.number*self.number)
	def factorial(self):
		fact=1
		i=self.number
		while i>=1:
			fact=fact*i
			i=i-1
		return fact

#main
obj=mynumber(5)
obj.ispositive()
obj.isodd()
print(obj.square())
print(obj.factorial())
			