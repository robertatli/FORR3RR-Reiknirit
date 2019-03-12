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
      from itertools import combinations as comb
      from string import ascii_lowercase as low
      from time import perf_counter


      def average(l):
          return sum(l)/len(l)
 ```
 #### a)
 
 ```python
      def find_pivot(l):
      pos = [0, len(l)//2, -1]
      pivot_list = [l[pos[0]], l[pos[1]], l[pos[2]]]
      l_len = len(l[0])
      return pos[pivot_list.index(min(pivot_list[0][:l_len], pivot_list[1][:l_len], pivot_list[2][:l_len]))]
 ```
 
  #### b)
 
 ```python
       def qsort(l):
          if len(l) <= 1:
              return l
          pi = find_pivot(l)
          l[-1], l[pi] = l[pi], l[-1]
          p = l[-1]
          i = -1
          for j, elem in enumerate(l[:-1]):
              if elem == p or min(elem, p) == elem:
                  i += 1
                  l[i], l[j] = l[j], l[i]
          l[i+1], l[-1] = l[-1], l[i+1]
          return qsort(l[:i+1]) + [l[i+1]] + qsort(l[i+2:])


      l = list(map("".join, list(comb(low, 5))))[::-1]
      start = perf_counter()
      l = qsort(l)
      print(perf_counter() - start)
      print(l)
 ```
 

