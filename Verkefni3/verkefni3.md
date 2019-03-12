1.
![Tower](https://github.com/robertatli/FORR3RR-Reiknirit/blob/master/Verkefni3/tower.png)

2. 2^n-1 því að fjoldi færlsna eykst í margfeldi af n ef þú ætlar að færa milli beggja súlnanna.

3. a) reykniritið keyrir n sinnum, Bubblesort
   b) reykniritið keyrir n^2 sinnum, Selection Sor
   c) reykniritið keyrir log(n) sinnum, Quicksort
4. Þetta gerir það sama nema bara með tölur.
```c#
public static IEnumerable<IEnumerable<T>> Combinations<T>(this IEnumerable<T> elements, int k)
{
  return k == 0 ? new[] { new T[0] } :
    elements.SelectMany((e, i) =>
      elements.Skip(i + 1).Combinations(k - 1).Select(c => (new[] {e}).Concat(c)));
}
```
