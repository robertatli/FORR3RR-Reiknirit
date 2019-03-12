### 1.
![Tower](https://github.com/robertatli/FORR3RR-Reiknirit/blob/master/Verkefni3/tower.png)
```python
      def hanoi(n,a,b,c):
       if n==1:
           print("færum %s frá %s til %s"%(n,a,b))
       else:
           hanoi(n-1,a,c,b)
           print("færum %s frá %s til %s"%(n,a,b))
           hanoi(n-1,a,b,c)

   hanoi(3,"a","b","c")
```

### 2. 
2^n-1 því að fjoldi færlsna eykst í margfeldi af n ef þú ætlar að færa milli beggja súlnanna.


### 3. 
  #### a) reykniritið keyrir n sinnum, Bubblesort
   
  #### b) reykniritið keyrir n^2 sinnum (lykkja sem er innan í lykkju), Selection Sort
   
  #### c) reykniritið keyrir raðar eftir fyrsta staf, Quicksort
   
   
### 4. 
```python
      import operator as op
      from itertools import combinations as comb
      from functools import reduce
      from string import ascii_lowercase as low
      from time import perf_counter
      
      def ncr(n, m):
          m = min(m, n-m)
          num = reduce(op.mul, range(n, n-m, -1), 1)
          denom = reduce(op.mul, range(1, m+1), 1)
          return num // denom
      m=2
```
  #### a) 26!/(26-n)!*n!
  
  ```python
      start = perf_counter()
      l = ncr(26, m)
      print("length calc:", l, "\ntime:", perf_counter() - start)
  ```
   
  #### b) O(2^n)
  
  ```python
      start = perf_counter()
      l = list(comb(low, m))
      print("comb calc:", l[0], ",", l[1], "...", l[-1], "\ntime:", perf_counter() - start)
  ```
  
 ### 5.
 ```python
      sys.setrecursionlimit(15000)
      listinn.reverse()
      print(listinn)
      tolulisti = ["ad","ab","aa","ag","as","ac"]

      if "abc" > "acb":
          print("abc")
          
      def partiton(l,low,high):
          t = low-1
          for x in range(low,high):
              if l[x] <= l[high]:
                  t+=1
                  l[x], l[t] = l[t], l[x]
          l[t+1], l[high] = l[high], l[t+1]
          return t+1

      def quicksort(l,low,high):
          if low<high:
              ind = partiton(l,low,high)
              quicksort(l,low,ind-1)
              quicksort(l,ind+1,high)

      quicksort(listinn,0,len(listinn)-1)
      print(listinn)
 ```
  #### a)
 
  #### b) O(n2)
 
 ```python
       
 ```
 

