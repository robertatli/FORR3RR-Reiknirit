# Skilaverkefni 2
1. (2%) Hvað er sauðakóði (pseuodocode) og til hvers er hann notaður?

    * Sauðakóði er nokkurs konar millistig almenns ritmáls og forritunarmáls og er því óháð því forritunarmáli sem reikniritið verður útfært í. Það auðveldar útfærslu reikniritsins í hinum ýmsu forritunarmálum, enda er sauðakóðinn auðskiljanlegur öllum forriturum óháð forritunarbakgrunn þeirra.
    
2. (3%) Skrifaðu forrit í sauðakóða sem umreytir tugakerfistölu í tvíundarkerfistölu. Hér er ekki
verið að biðja um keyranlegt forrit

    * Byður notanda um að slá inn tölu
    
    * tekur inn tölu sem notandinn slær inn
      
    * breytir tölunni í binary
      
    * skrifar út töluna í binary
    
      Dæmi í c#
      
      ```c#
      int value = 9;
      string binary = Convert.ToString(value, 2);
      Console.Write(binary);
      Console.ReadKey();
      return;
      ```
3. (2%) Skoðaðu rununa 1, 4, 9, 16, 25, 36, .... Eins og þú sérð er þetta í raun n
2 þar sem n er stak
í menginu náttúrulegar tölur N = {1, 2, 3, 4,...}. Skrifaðu endurkvæma fallið summa(m) sem
reiknar ∑ 𝑛
𝑚 2
𝑛=1
og skilar summunni. Dæmi: Ef m er 5 þá ætti fallið summa(5) að reikna og
skila 12 + 22 + 32+ 4
2 +52 = 55.

      ```c#
       static void Main(string[] args)
        {

            Console.Write("Skrifaðu inn tölu:");
            double m = Convert.ToDouble(Console.ReadLine());
            double utkoma = Summa(m);
            Console.WriteLine("Útreikningur: ");
            for (int i = 1; i < m; i++)
            {
                Console.Write(i + "^2 + ");
            }
            Console.Write(m + "^2 ");
            Console.Write("= " + utkoma);
            Console.ReadKey();
            return;
        }
        public static int Summa(double m)
        {
            if (m == 1)
            {
                return 1;
            }
            else
            {
                double utkoma = Math.Pow(m, 2) + Summa(m-1);
                return Convert.ToInt32(utkoma);
            }
        }
      ```

4. (4%) Skoðaðu vel rununa 1, 3, 6, 10, 15, 21, .... Finndu út mynstur rununnar og skrifaðu
endurkvæma fallið runa(m) sem skrifar m fyrstu stök rununnar á skjáinn. Dæmi: runa(5)
mundi skrifa 1 3 6 10 15 á skjá.

      ```c#

      ```

5. (2%) Skrifaðu endurkvæma fallið þversumma(n) sem tekur færibreytuna n. Fallið skilar til
baka þversummu n. Dæmi: þversumma tölunnar 12 er 3 eða 1+2=3. Þversumma tölunnar
1206 er 9 eða 1+2+0+6=9. Fallið skilar aðeins einni tölu.

      ```c#

      ```

6. (2% ) Skrifaðu endurkvæma fallið samnefnari(n,m) sem tekur tvær heiltölufæribreytur n og
m. Fallið á siðan að finna hæstu tölu sem gengur bæði upp í n og m. Dæmi,
samnefnari(8,12) mundi skila 4 þar sem það er hæsta tala sem gengur bæði upp í 8 og
12. samnefnari(3,13) mundi skila 1 þar sem 1 er hæsta tala sem gengur bæði upp í 3 og
13. samnefnari(12,60) mundi skila 12 þar sem 12 er hæsta tala sem gengur bæði upp í 12
og 60. Fallið skal vera endurkvæmt. 
