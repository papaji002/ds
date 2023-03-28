class my_time:
	def __init__(self):
		hh=0
		mm=0
		ss=0

	def set_time(self , h , m , s):
		self.hh=h
		self.mm=m
		self.ss=s

	def get_time(self):
		print("Time: ",self.hh,":",self.mm,":",self.ss)

	def get_hours(self):
		print("Hours: ",self.hh)

	def add_time(self,h,m,s):
		self.hh +=h
		self.mm +=m
		self.ss +=s
#main
obj=my_time()
obj.set_time(13,14,52)
obj.get_time()
obj.get_hours()
obj.add_time(0,2,0)
obj.get_time()