


### 1.
```python
from math import *
  class Node:
      def __init__(self, d):
          self.data = d
          self.prv = None
          self.nxt = None

#---------------------------------------bætir aftan a listann
      def append(self,d):
          if self.nxt:
              return self.nxt.append(d)
          else:
              curr = Node(d)
              self.nxt = curr
              curr.prv = self
              return True
#---------------------------------------prentar listann
      def printList(self):
          print(self.data)
          if self.nxt:
              return self.nxt.printList()
#---------------------------------------prentar fra head til enda
      def find(self, d):
          if self.data==d:
              return True
          elif self.nxt:
              return self.nxt.find(d)
          else:
              return False
#---------------------------------------eyðir ákveðnu ur lista
      def delete(self, d):
          if self.data==d:
              self.prv.nxt=self.nxt
              if self.nxt:
                  self.nxt.prv = self.prv
              self.nxt=None
              self.prv=None

              return True
          else:
              return self.nxt.delete(d)



  class DLL: # DLL = Double Linked List
      def __init__(self):
          self.head = None
#--------------------------------------- bætir við frems í listann
      def push(self,d):
          a=Node(d)
          a.nxt=self.head
          self.head.prv=a
          self.head=a
          return True
#---------------------------------------bætir aftast í listann
      def append(self, d):
          if self.head:
              return self.head.append(d)
          else:
              self.head = Node(d)
              return True
#---------------------------------------prentar allann listann
      def printList(self):
          if self.head:
              self.head.printList()
          else:
              print("Empty list!")
#---------------------------------------finnur ákveðið fall
      def find(self, d):
          if self.head:
              return self.head.find(d)
          else:
              return False
#---------------------------------------eyðir ákveðið fall

      def delete(self, d):
          try:
              if self.head is None:
                  return -1
              elif self.head.data == d:
                  self.head = self.head.nxt
                  if self.head:
                      self.head.prv.nxt = None
                      self.head.prv = None
                  return True
              else:
                  return self.head.delete(d)
          except:
              return False

  dbl = DLL()

  print("___appendum___")
  
  print(dbl.append(3))           # 3
  print(dbl.append(8))
  print("___pushum___")# 3 8
  print(dbl.push(2))             # 2 3 8
  print(dbl.push(0))          # 0 2 3 8
  print("___appendum aftur___")
  print(dbl.append(11))        # 0 2 3 8 11
  print("___prentum listann___")
  
  dbl.printList()
  
  print("___deleteum___")
  print(dbl.delete(5))   # 0 2 3 8
  print("___prentum listann aftur___")
  
  dbl.printList()
  
  print("___Leytum í listanum___")
  print(dbl.find(3))      # True
  print(dbl.find(11))     # False
```

### 2.
```python
  class Vigur:
  #-------------------------------------Frumstyllir x og y hnit
      def __init__(self,x,y):
          self.x=x
          self.y=y
  #-------------------------------------Skrifar hnit vigurs
      def prenta(self):
          print("("+str(self.x)+","+str(self.y)+")")

  #-------------------------------------skilar lengd
      def lengd(self):
          c=(self.x**2)+(self.y**2)
          c=sqrt(c)
          return c

  #-------------------------------------skilar hallatölu
      def halli(self):
          h=self.y/self.x
          return h

  #-------------------------------------skilar þvervigri
      def þvervigur(self):
          return Vigur(-self.y,self.x)

  #-------------------------------------skilar stefnuhorni
      def stefnuhorn(self):
          x=self.x
          y=self.y
          if x<0 and y<0:
              return degrees(atan(y/x))-180
          elif x<0 and y>=0:
              return 180+degrees(atan(y/x))
          else:
              return degrees(atan(y/x))

  #-------------------------------------skilar horni milli vigra
      def horn(self,v):
          a=self.x*v.x
          b=self.y*v.y
          a1=sqrt(self.x**2 + self.y**2)
          b1=sqrt(v.x**2 + v.y**2)

          q=degrees(acos((a+b)/(a1*b1)))
          return q

  #-------------------------------------skilar summu vigri
      def summa(self,v):
          return Vigur(self.x+v.x,self.y+v.y)


  print("___Vigrar___")
  
  v1 = Vigur(5,5)
  v1.prenta()
  
  print("Lengd vigurs: ", v1.lengd())
  print("Halli vigurs: ", v1.halli())
  
  vþ = v1.þvervigur()
  
  print("Þvervigur vigurs: " , end=" ")
  
  vþ.prenta()
  
  print("Stefnuhorn vigurs: ", v1.stefnuhorn())
  
  v2 = Vigur(1,-1)
  
  print("Horn milli vigra: " , v2.horn(v1))
  
  v3 = v1.summa(v2)
  
  print("Summa vigurs: " , end=" ")
  
  v3.prenta()
  
```
