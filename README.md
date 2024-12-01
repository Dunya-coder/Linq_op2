# Linq_op2
where,let,join lar birgalikda dasturlar
So'rovda vaqtinchalik o'zgaruvchi yaratish uchun let operatoridan foydalanish 
let nomi = ifoda  bu yerda nomi ifoda bergan qiymatni qabul qiluvchi identifikatorni bildiradi. Nomining turi ibora turidan kelib chiqadi. 
``` C#
using System;
using System.Linq; 
class LetMisol 
{    
  static void Main()
  { 
    string[] strs = { "alpha", "beta", "gamma" }; 
 
    var chrs = from str in strs 
                let chrArray = str.ToCharArray()
                from ch in chrArray
            orderby ch
      select ch; 
    Console.WriteLine("Berilgan massivdagi belgilarning tartiblangan shakli:"); 
 
    foreach(char с in chrs)
       Console.Write(с + " "); 
        Console.WriteLine(); 
    } 
}
```

