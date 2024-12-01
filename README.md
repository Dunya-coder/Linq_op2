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
* 2-misol
``` Cs
using System; using System.Linq; class Item { 
    public string Name { get; set; } 
    public int ItemNumber { get; set; }     public Item(string n, int inum) 
    { 
        Name = n; 
        ItemNumber = inum; 
    } } 
class InStockStatus { 
    public int ItemNumber { get; set; }     public bool InStock { get; set; }     public InStockStatus(int n, bool b) 
    { 
        ItemNumber = n; 
        InStock = b; 
    } } class Temp { 
    public string Name { get; set; }     public bool InStock { get; set; }     public Temp(string n, bool b) 
    { 
        Name = n; 
        InStock = b; 
    } } 
class JoinDemo 
{ 
    static void Main() 
    { 
        Item[] items = { 
                    new Item("Qaychi", 1424),                     new Item("Pichoq", 7892),                     new Item("Bolg'a", 8534),                     new Item("Qoshiq", 6411) 
                    }; 
        InStockStatus[] statusList = {                     new InStockStatus(1424, true),                     new InStockStatus(7892, false),                     new InStockStatus(8534, true),                     new InStockStatus(6411, true) 
                }; 
        var inStockList = from item in items                           join entry in statusList 
                          on item.ItemNumber equals entry.ItemNumber                           select new Temp(item.Name, entry.InStock); 
        Console.WriteLine("Tovar \t Mavjudligi\n"); 
         
        foreach (Temp t in inStockList) 
            Console.WriteLine("{0}\t{1}", t.Name, t.InStock);     } 
} 
```
Natija:
```Cs
Tovar    Mavjudligi 
Qaychi   True 
Pichoq   False 
Bolg'a   True 
Qoshiq   True 
```
