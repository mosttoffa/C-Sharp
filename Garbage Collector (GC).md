## Garbage Collector (GC) In C#

🧹 Garbage Collector (GC) কিভাবে কাজ করে?
✅ সংজ্ঞা (Definition):

Garbage Collector (GC) হলো .NET Framework বা .NET Runtime-এর একটি built-in memory management system, যা স্বয়ংক্রিয়ভাবে অপ্রয়োজনীয় বা অব্যবহৃত object গুলোকে memory থেকে মুছে ফেলে।

👉 এর মাধ্যমে ম্যানুয়ালি free() বা delete করার দরকার হয় না — যেমন C বা C++ এ করতে হয়।

1️⃣ Object Creation

যখন আমরা একটি নতুন object তৈরি করি :

Person p = new Person();

➡️ তখন তা Heap memory তে সংরক্ষিত হয়।

2️⃣ Object Alive থাকলে GC কিছু করে না

যতক্ষণ পর্যন্ত object টি র reference থাকে, ততক্ষণ GC সেটিকে untouched রাখে।

p.Name = "John"; // এখনও ব্যবহৃত হচ্ছে

3️⃣ Reference না থাকলে GC লক্ষ্য করে

যখন object এর প্রতি কোনো reference আর থাকে না:

p = null; // object unreachable

➡️ তখন GC বুঝতে পারে — এই object আর দরকার নেই তখন GC memory থেকে মুছে ফেলে।

4️⃣ Garbage Collection Trigger হয় GC automatic অথবা manually GC.Collect() দিয়ে শুরু হতে পারে।

➡️ এটি তিনটি generation scan করে:

Generation Object Type Explanation

Gen 0 => Short-lived objects => যেমন: local variables

Gen 1 => Medium-lived => সাময়িক ব্যবহার

Gen 2 => Long-lived => যেমন: static data, cached objects

5️⃣ Mark and Sweep Algorithm

Garbage Collector নিচের কাজগুলো করে:

✅ Mark করে কোন কোন object এখনো accessible।

❌ Sweep করে যেগুলো inaccessible → memory release করে।

6️⃣ Memory Reclaimed অপ্রয়োজনীয় object গুলো সরানো হলে সেই জায়গায় নতুন object রাখা যায়। এভাবে memory leak কমে যায়।

📊 চিত্র (Flow Summary):
Object Created ➡ Referenced ➡ Used ➡ Unused ➡ GC Detects ➡ Finalize ➡ Memory Freed







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

Garbage Collection = ৩টি ধাপে কাজ করে

1️⃣ Mark Phase → কে কে এখনো বেঁচে আছে (alive / reachable object) তা খুঁজে বের করে
2️⃣ Sweep Phase → বাকি মৃত (unreachable) object গুলোর memory ফাঁকা করে
3️⃣ Compact Phase → ফাঁকা জায়গাগুলো সরিয়ে memory contiguous করে
 

