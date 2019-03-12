1.
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

2. 
2^n-1 því að fjoldi færlsna eykst í margfeldi af n ef þú ætlar að færa milli beggja súlnanna.


3. 
   a) reykniritið keyrir n sinnum, Bubblesort
   b) reykniritið keyrir n^2 sinnum (lykkja sem er innan í lykkju), Selection Sort
   c) reykniritið keyrir raðar eftir fyrsta staf, Quicksort
   
   
4. ```python
      t=string.ascii_lowercase
      y =[]
      def q(n,s="",r = 0):
          if n > 0:
              for x in range(r,len(t)):
                  if n == 1:
                      y.append(s+t[x])
                  r+=1
                  q(n-1,s+t[x],r)

      lengd = int(input("Veldu lengd strengsins: "))
      q(lengd)
      print(y)
```
   a) 26!/(26-n)!*n!
   b) O(2^n)

