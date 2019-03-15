


### 1.
```python
from math import *
  class Node:
      def __init__(self, d):
          self.data = d
          self.prv = None
          self.nxt = None

#---------------------------------------
      def append(self,d):
          if self.nxt:
              return self.nxt.append(d)
          else:
              curr = Node(d)
              self.nxt = curr
              curr.prv = self
              return True
#---------------------------------------
      def printList(self):
          print(self.data)
          if self.nxt:
              return self.nxt.printList()
#---------------------------------------
      def find(self, d):
          if self.data==d:
              return True
          elif self.nxt:
              return self.nxt.find(d)
          else:
              return False
#---------------------------------------
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
#---------------------------------------
      def push(self,d):
          a=Node(d)
          a.nxt=self.head
          self.head.prv=a
          self.head=a
          return True
#---------------------------------------
      def append(self, d):
          if self.head:
              return self.head.append(d)
          else:
              self.head = Node(d)
              return True
#---------------------------------------
      def printList(self):
          if self.head:
              self.head.printList()
          else:
              print("Empty list!")
#---------------------------------------
      def find(self, d):
          if self.head:
              return self.head.find(d)
          else:
              return False
#---------------------------------------

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

  print("--- append ---")
  
  print(dbl.append(5))           # 5
  print(dbl.append(7))
  print("--- push ---")# 5 7
  print(dbl.push(1))             # 1 5 7
  print(dbl.push(0))          # 0 1 5 7
  print("--- append aftur ---")
  print(dbl.append(10))        # 0 1 5 7 10
  print("--- printlist ---")
  
  dbl.printList()
  
  print("--- delete ---")
  print(dbl.delete(5))   # 0 1 5 7
  print("--- printlist aftur ---")
  
  dbl.printList()
  
  print("--- find ---")
  print(dbl.find(5))      # True
  print(dbl.find(10))     # False
```

### 2.
```python
  class Vigur:
  #-------------------------------------
      def __init__(self,x,y):
          self.x=x
          self.y=y
  #-------------------------------------
      def prenta(self):
          print("("+str(self.x)+","+str(self.y)+")")

  #-------------------------------------
      def lengd(self):
          c=(self.x**2)+(self.y**2)
          c=sqrt(c)
          return c

  #-------------------------------------
      def halli(self):
          h=self.y/self.x
          return h

  #-------------------------------------
      def þvervigur(self):
          return Vigur(-self.y,self.x)

  #-------------------------------------
      def stefnuhorn(self):
          x=self.x
          y=self.y
          if x<0 and y<0:
              return degrees(atan(y/x))-180
          elif x<0 and y>=0:
              return 180+degrees(atan(y/x))
          else:
              return degrees(atan(y/x))

  #-------------------------------------
      def horn(self,v):
          a=self.x*v.x
          b=self.y*v.y
          a1=sqrt(self.x**2 + self.y**2)
          b1=sqrt(v.x**2 + v.y**2)

          q=degrees(acos((a+b)/(a1*b1)))
          return q

  #-------------------------------------
      def summa(self,v):
          return Vigur(self.x+v.x,self.y+v.y)


  print("--- Vigrar ---")
  
  v1 = Vigur(4,4)
  v1.prenta()
  
  print("Lengd: ", v1.lengd())
  print("Halli: ", v1.halli())
  
  vþ = v1.þvervigur()
  
  print("Þvervigur: " , end=" ")
  
  vþ.prenta()
  
  print("Stefnuhorn: ", v1.stefnuhorn())
  
  v2 = Vigur(1,-1)
  
  print("Horn milli vigra: " , v2.horn(v1))
  
  v3 = v1.summa(v2)
  
  print("Summa: " , end=" ")
  
  v3.prenta()
  
```
