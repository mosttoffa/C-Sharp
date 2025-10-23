## Garbage Collector (GC) In C#

✅ <b>Garbage Collector (GC) কী? </b> <br> 
Garbage Collector হলো .NET CLR (Common Language Runtime)-এর একটা built-in memory manager।  <br> 
এটার কাজ হলো — <br> 
“Automatically detect and free up memory that is no longer used by the program.” <br> 
অর্থাৎ, যখন তোমার প্রোগ্রামে কোনো object আর দরকার নেই, GC সেই object এর memory automatically reclaim করে নেয়, যাতে memory leak না হয়।  <br> 

🔷 <b> কেন Garbage Collector দরকার? </b> 

 * Developer memory management থেকে মুক্ত
 * Memory leak বা dangling pointer-এর ঝুঁকি কমে যায়
 * প্রোগ্রাম stable এবং efficient হয়

🔷 <b>Garbage Collector কিভাবে কাজ করে ? </b> <br> 
C#-এর garbage collector মূলত নিচের ৩-ধাপের classic algorithm-এর উপর ভিত্তি করে কাজ করে, যেটাকে বলা হয়
> Mark–and–Sweep–Compact Algorithm (Generational GC version)


 

