## Exception 

✅ <b> Exception কী ? </b> <br> 
Exception মানে “Unexpected error” — যা প্রোগ্রাম চলার সময় হঠাৎ ঘটে এবং normal flow বন্ধ করে দেয়। <br> 

🔷 <b>Exception Handling কেন দরকার? </b> <br> 

✅ <b> Built-in Exception কী ? </b>  <br> 
Built-in Exception মানে — যেগুলো .NET Framework নিজের ভেতরেই define করা আছে (আমাদের define করতে হয় না)। এই Exception গুলো System.Exception class থেকে derive করা। <br>
> Namespace: System, System.IO, System.Net, System.Data, System.Xml


✅ <b> try-catch-finally এর কাজ : </b> <br> 
🔷 <b>try : </b> এখানে risky বা error-prone code রাখা হয়। যেমন: Database connection, File I/O, API call, User input conversion. <br>
🔷 <b>catch : </b> যদি try block এ exception ঘটে, তাহলে control catch এ আসে। এখানে তুমি exception handle করতে পারো (log করা, custom message দেওয়া, retry ইত্যাদি)। <br> 
🔷 <b>finally : </b> finally block সর্বদা execute হয় — error হোক বা না হোক। এখানে clean-up কাজ করা হয়: যেমন file close করা, DB connection dispose করা। <br> 











