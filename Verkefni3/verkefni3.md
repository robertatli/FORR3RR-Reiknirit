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

2. 2^n-1 því að fjoldi færlsna eykst í margfeldi af n ef þú ætlar að færa milli beggja súlnanna.


3. a) reykniritið keyrir n sinnum, Bubblesort
   b) reykniritið keyrir n^2 sinnum (lykkja sem er innan í lykkju), Selection Sort
   c) reykniritið keyrir raðar eftir fyrsta staf, Quicksort
   
   
4. 
```python
    26!
__________
(26-n)!*n!
```
![equation](http://www.sciweavers.org/tex2img.php?eq=1%2Bsin%28mc%5E2%29&bc=White&fc=Black&im=jpg&fs=12&ff=arev&edit=)
