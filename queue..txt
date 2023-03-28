class Queue:
    
    def __init__(self):
        self.items = list()
    def isempty(self):
        return len(self.items)==0
    def enqueue(self,data):
        self.items.append(data)
    def dequeue(self):
        assert not self.isempty(),"EMPTY QUEUE"
        return self.items.pop(0)
myqueue = Queue()
myqueue.enqueue("JAN")
myqueue.enqueue("FEB")
myqueue.enqueue("MAR")
myqueue.enqueue("APR")
print("CHECK QUEUE EMPTY ",myqueue.isempty())
print(myqueue.dequeue())
print(myqueue.dequeue())

print(myqueue.dequeue())
