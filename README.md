# Linq_op2
where,let,join lar birgalikda dasturlar
So'rovda vaqtinchalik o'zgaruvchi yaratish uchun let operatoridan foydalanish 
let nomi = ifoda  bu yerda nomi ifoda bergan qiymatni qabul qiluvchi identifikatorni bildiradi. Nomining turi ibora turidan kelib chiqadi.
*Kirish ma'lumotlari sifatida so'rovga belgilar satrlari massivi kiritiladi, keyinchalik ular char tipidagi massivlarga aylanadi. Bu maqsadda satrdagi belgilarni o'z ichiga olgan massivni qaytaruvchi ToCharArray() deb nomlangan yana bir satrni qayta ishlash usuli mavjud. Natija chrArray o'zgaruvchisiga tayinlanadi, so'ngra u massivdan alohida belgilarni chiqarish uchun ichki o'rnatilgan from bayonotida ishlatiladi. Nihoyat, so'rovda olingan belgilar tartiblanadi va ulardan olingan ketma-ketlik hosil bo'ladi.  
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
Natija:
``` C#
a a a a a b e g h l m m p t 
```
