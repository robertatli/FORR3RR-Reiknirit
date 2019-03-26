### 3. Project Euler Verkefni 67 í C# consoleApp
```c#
  using System;
  using System.Collections.Generic;
  using System.Linq;
  using System.Text;
  using System.Threading.Tasks;
  using System.IO;
  using System.Diagnostics;

  namespace PEProblem67
  {
      class Program
      {
          static void Main(string[] args)
          {
              new Program().Dynamic(); 
          }

          private int[,] readInput(string filename)
          {
              string line;
              string[] linePieces;
              int lines = 0;

              StreamReader r = new StreamReader(filename);
              while ((line = r.ReadLine()) != null) lines++;
              
              int[,] inputTriangle = new int[lines, lines];
              r.BaseStream.Seek(0, SeekOrigin.Begin);

              int j = 0;
              while ((line = r.ReadLine()) != null)
              {
                  linePieces = line.Split(' ');
                  for (int i = 0; i < linePieces.Length; i++)
                  {
                      inputTriangle[j, i] = int.Parse(linePieces[i]);
                  }
                  j++;
              }
              r.Close();
              return inputTriangle;
          }

          public void Dynamic()
          {
              Stopwatch clock = Stopwatch.StartNew();

              string filename = Environment.GetFolderPath(Environment.SpecialFolder.DesktopDirectory) + "\\input.txt"; //hefur fileið af projecteuler siðunni a desktop sem input.txt
              int[,] inputTriangle = readInput(filename);
              int lines = inputTriangle.GetLength(0);
              int[] largestValues = new int[lines];

              for (int i = 0; i < lines; i++) largestValues[i] = inputTriangle[lines - 1, i];

              for (int i = lines - 2; i >= 0; i--)
              {
                  for (int j = 0; j <= i; j++)
                  {
                      largestValues[j] = inputTriangle[i, j] += Math.Max(largestValues[j], largestValues[j + 1]);
                  }
              }
              clock.Stop();
              Console.WriteLine("Stærsta summa talnanna er: {0}", largestValues[0]);
              Console.WriteLine("Lausn tók {0} ms", clock.ElapsedMilliseconds);
              Console.ReadKey();
          }
      }
  }

```
