### 1. 

#### a) Reykniritið raðar tölunum í listanum L frá minnstu tölunni til hæstu.

#### b) Counting Sort

#### c) O(n+k)

### 2.

```python
   listi=[8,5,3,7,1,9,2,6]

   def linear(l,t):
       if len(l)==0:
           return -1
       else:
           tel=-1
           for x in l:
               tel+=1
               if x==t:
                   return "Talan",t,"er í sæti",tel
           return "Talan",t,"er ekki í listanum"

   t=int(input("Sláðu inn tölu til að finna: "))
   print(linear(listi,t))
```

### 3.

```python
   listi=[1,2,3,5,6,7,8,9]
   def b(t,lis,l,h):
       if l<=h:
           m=(h+l)//2
           if t==lis[m]:
               return "Talan",t,"er í sæti",m
           elif t>lis[m]:
               return b(t,lis,m+1,h)
           else:
               return b(t,lis,0,m-1)
       else:
           return "Talan",t,"er ekki í listanum"

   t=int(input("Sláðu inn tölu til að finna: "))
   print(b(t, listi, 0, len(listi)))
```
### 4.

#### a) Það er ein for lykkja í fallinu sem gerir flækjustigið O(n)

#### b) Í hvert skipti sem fallið keyrist er listinn minnkaður um helming þannig þá er flækjustigið O(log(n))

### 5.
```python
   listinn=[2,3,4,5,6,7,8,9,10]
   def rada(lis,t,l,h):
       if len(lis)==0 or lis[-1]<t:
           lis.append(t)
           return True
       elif t<lis[0]:
           lis.insert(0,t)
           return True
       elif t == lis[l] or lis[l]<=t<=lis[l+1]:
           lis.insert(l+1,t)
           return True
       elif t>lis[l]:
           return rada(lis,t,l+1,h)

   t=int(input("Sláðu inn tölu til að bæta við: "))
   print(rada(listinn,t,0,len(listinn)))
   print(listinn)
```

### 6.

```python
   class node:
       def __init__(self,v):
           self.value=v
           self.left=None
           self.right=None

       def insert(self,a):
           if self.value==a:
               return False
           elif self.value>a:
               if self.left:
                   return self.left.insert(a)
               else:
                   self.left=node(a)
                   return True
           else:
               if self.right:
                   return self.right.insert(a)
               else:
                   self.right=node(a)
                   return True
       def find(self,a):
           if self.value==a:
               return True
           elif self.value>a:
               if self.left:
                   return self.left.find(a)
               else:
                   return False
           else:
               if self.right:
                   return self.right.find(a)
               else:
                   return False

   class tree:
       def __init__(self):
           self.root=None

       def insert(self,a):
           if self.root:
               return self.root.insert(a)
           else:
               self.root=node(a)
               return True
       def find(self,a):
           if self.root:
               return self.root.find(a)
           else:
               return False


   t=tree()
   
   print(t.insert(6))
   print(t.insert(2))
   print(t.insert(3))
   print(t.insert(7))
   print(t.find(3))
   print(t.find(4))
   print(t.find(6))
```
