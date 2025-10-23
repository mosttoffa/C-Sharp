##   Exception 

✅ <b>Exception Handling </b> <br> 
✅ <b>Exception Handling কীভাবে কাজ করে? </b> <br>
C# এ Exception Handling-এর প্রধান ৩টি অংশ: try block, catch block, finally block 

🔹 <b>1. try Block – সন্দেহজনক কোড রাখা হয় </b>
<pre>
try 

{

int a = 10, b = 0; 
int c = a / b; // এখানে exception হবে
}
 </pre> 
🔸 try ব্লকে রাখা হয় সেই কোড যা error বা exception ঘটাতে পারে।

🔹 <b>2. Exception ঘটলে CLR (Common Language Runtime) সেটা ধরে C# এ যখন কোনো runtime exception হয় (যেমন 0 দিয়ে ভাগ), তখন CLR: </b>
 * একটি Exception object তৈরি করে
 * সেই exception কে উপরের দিকে পাঠাতে থাকে (Stack Unwinding)
 * খোঁজে কোনো catch block আছে কি না

🔹 <b>3. catch Block – Exception ধরার জায়গা </b> 
<pre> 
catch (DivideByZeroException ex)

{

Console.WriteLine("Quotient not possible : " + ex.Message);
}
</pre>
🔸 catch ব্লক সেই কোড , যেখানে CLR exception পাঠায়। চাইলে এখানে exception handle করে ব্যবহারকারীর জন্য সুন্দর মেসেজ পাঠানো যায় ।

🔹 <b>4. finally Block – সবশেষে যেটা চলবেই </b>
<pre>
finally

{

Console.WriteLine("Operation complete.");
}
 </pre>
🔸 finally block সবসময় চলবে – exception হোক বা না হোক। 

🔸 সাধারণত এখানে resource cleanup (file/database connection বন্ধ করা) করা হয়। 

🔁 <b>Flow Chart </b> 
<pre> 
try → exception? → yes → catch → finally → resource cleanup
</pre>
উদাহরণ:
<pre> 
try

{

string name = null;
Console.WriteLine(name.Length); // NullReferenceException
} catch (NullReferenceException ex)

{

Console.WriteLine("wrong : " + ex.Message);
}

finally

{

Console.WriteLine("Resource  Clean !");
}
</pre>
🔍<b> InnerException কীভাবে কাজ করে? </b>  <br> 
InnerException C# এর Exception class এর একটি property, যা একটি exception এর ভেতরে আরেকটি আসল exception কে ধরে রাখে। <br> 

এটি তখনই দরকার হয়, যখন কোনো বড় বা complex error ঘটলে, আমরা সেই মূল ভুল (root cause) বা আসল exception জানার চেষ্টা করি।  <br>   

✅ <b>কেন InnerException দরকার? </b> <br> 
👉 ধরুন আপনি একটি ফাইল read করছেন, কিন্তু সে ফাইলটি পাওয়া যাচ্ছে না। এর কারণে একটি FileNotFoundException হবে। আপনি যদি এর ওপর আরেকটি custom exception throw করেন, তাহলে সেই মূল exception যেন হারিয়ে না যায়—এই জন্য InnerException ব্যবহার করা হয়। <br> 

উদারন :
<pre> 
try

{

try
{
    // main  exception
     int x = int.Parse("abc"); // FormatException

}

catch (FormatException ex)
{

    // উপরের exception ধরে নতুন exception তৈরি করা হল 
    throw new ApplicationException("wong  data format ।", ex);

}
}

catch (ApplicationException ex)

{

Console.WriteLine("Main Exception: " + ex.Message);
Console.WriteLine("Root Cause (InnerException): " + ex.InnerException.Message);
}
</pre>
✅ <b>Common Built-in Exception Classes in C# </b> <br>
<b>Exception Class Hierarchy : </b><br> 

📌 System.Exception সব exception ক্লাসের মূল ভিত্তি (base class)। base class এর মাধ্যমে সকল exception গুলো তৈরি হয়। <br>

⚙️ System.SystemException <br> 
Exception Class এবং ব্যাখ্যা  <br> 
১.ArgumentException => method-এ invalid argument দিলে যেমনঃ Path.GetFileName("*illegal?name"); <br>
২.ArgumentNullException => null argument দিলে যেমনঃ File.ReadAllText(null);  <br> 
৩.ArgumentOutOfRangeException => সীমার বাইরে argument দিলে যেমনঃ list[100] যখন list-এ এত item নেই অথ্যাৎ list[101] যদি এক্সেস করতে চাই তখন এরর দিবে । 

✅ <b>৪.ArithmeticException </b> 

└── DivideByZeroException => int x = 10 / 0; শূন্য দিয়ে ভাগ করলে

└── OverflowException => সীমা ছাড়িয়ে গেলে

৫.IndexOutOfRangeException => Array বা list এর সীমার বাইরে গেলে যেমনঃ int[] arr = new int[3]; var item = arr[5];

৬. NullReferenceException => অথাৎ null object থেকে access করলে যেমনঃ string name = null; var length = name.Length;

৭.InvalidCastException => অথাৎ অবৈধ cast করলে যেমনঃ object obj = "abc"; int i = (int)obj;

৮.FormatException => ভুল format হলে (যেমন: int.Parse("abc"))

৯.StackOverflowException => infinite recursion

১০.OutOfMemoryException => অনেক বড় data load করার সময় পর্যাপ্ত মেমোরি না থাকলে

১১.InvalidOperationException => object-এর ভুল অবস্থা থেকে call করলে

১২.ObjectDisposedException => dispose হয়ে যাওয়া object ব্যবহার করলে

📂 <b>System.IO.IOException </b> <br>
ফাইল, ডিরেক্টরি এবং ড্রাইভ সংক্রান্ত Input/Output exception।

১.IOException => সাধারন IO ত্রুটি

২.FileNotFoundException => ফাইল খুঁজে না পেলে

৩.DirectoryNotFoundException =>ডিরেক্টরি না পেলে

৪.PathTooLongException => পাথ অনেক বড় হলে

৫.DriveNotFoundException => নির্দিষ্ট ড্রাইভ না পেলে

৬.EndOfStreamException => stream-এর শেষ পৌঁছে গেলে

🔒 <b>Security and Access Exceptions </b> <br>
UnauthorizedAccessException => অনুমতি ছাড়া resource access SecurityException => security policy লঙ্ঘন হলে

⏱ <b>Async & Threading Exceptions </b>

১.OperationCanceledException => async কাজ cancel হলে

২.TaskCanceledException => Task cancel হলে

৩.ThreadAbortException => থ্রেড জোরপূর্বক বন্ধ হলে

৪.SynchronizationLockException => ভুল ভাবে lock ব্যবহারে

🧩 <b>Other Notable Exceptions </b> 
১.KeyNotFoundException => Dictionary-তে key না পেলে

২.NotImplementedException => method implement না করলে

৩.NotSupportedException => unsupported কাজের চেষ্টা

৪.PlatformNotSupportedException => current OS/platform support না করলে

৫.TimeoutException => নির্ধারিত সময় অতিক্রম হলে

৬.ApplicationException => custom application-level exception base (not recommended)
<br> 
🔄 <b>Dispose() কী? </b>  <br>
✅ সংজ্ঞা (Definition):

Dispose() হলো একটি method, যা unmanaged resources (যেমন: file handles, database connections, network sockets ইত্যাদি) release করার জন্য ব্যবহৃত হয়। <br> 

এটি IDisposable ইন্টারফেসের অংশ — যার মূল উদ্দেশ্য হলো মেমোরি বা রিসোর্স লিক প্রতিরোধ করা।

✅ <b>Managed resource =></b> string, int, arrays => .NET CLR (Garbage Collector)

✅ <b>Unmanaged resources =></b> File handles, DB connections, Win32 API resources,network sockets => Dispose() দিয়ে release করতে হবে ।

📦 <b>IDisposable Interface: </b> 
<pre>
public interface IDisposable {

//  Performs application-defined tasks associated with freeing, 
releasing, or resetting  
//unmanaged resources.

void Dispose();
}
 </pre>
যে ক্লাসটি IDisposable ইন্টারফেস implement করে, সেটি Dispose() method define করে unmanaged resource free করতে পারে। <br> 

উদাহরণ:
<pre>
public class MyResource:IDisposable

{

 private FileStream file;

 public MyResource()

 {

     file = new FileStream("data.txt", FileMode.OpenOrCreate);

 }

 public void Dispose()

 {
    
     file.Dispose();
     Console.WriteLine("File resource released.");

 }
}
 </pre>
🔐 <b>Using using Statement: </b> 
<pre> 
using (var reader = new StreamReader("data.txt"))

{

string line = reader.ReadLine();
}

// এখানে reader.Dispose() অটোমেটিক কল হয়ে যাবে
</pre>
➡️ <b>using ব্লক শেষ হলে Dispose() নিজে থেকেই call হয়ে যায়, কোনো resource leak হয় না। </b>  <br> 
Object এর lifecycle শেষে (explicitly বা using দিয়ে) চলে. 

<br> <br> <br> <br> 


--------------------------------------------------------------------------------------------------------------------------------------


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

✅ <b>কখন use করবে </b> 
<pre>
 পরিস্থিতি	            |     Exception Handling দরকার?	       |        কারণ
------------------------------------------------------------------------------------------------------------
User Input	          |         ✅ হ্যাঁ	                       |   Invalid data (format, null, etc.)
File Handling	       |         ✅ হ্যাঁ	                       |   File না পাওয়া, permission denied
Database Query	      |         ✅ হ্যাঁ	                       |   DB connection fail, timeout, invalid data
Network Request	     |         ✅ হ্যাঁ	                       |   Connection lost, API unavailable
Calculation	         |         ⚠️ মাঝে মাঝে	                 |   Divide by zero, overflow
UI Event Handler	    |         ✅	                           |   Prevent app crash on user action
Background service	  |         ✅	                           |   Prevent service crash and log error
 </pre>

🔷 <b>Common Built-in Exception Classes </b> 
<pre>
Exception	               | ঘটে কেন	             | উদাহরণ
------------------------------------------------------------------------------------------
DivideByZeroException	   | শূন্য দিয়ে ভাগ	        | int x = 10 / 0;
NullReferenceException	  | null object access	  | string s = null; s.Length;
IndexOutOfRangeException	| array limit cross	   | arr[5] যখন arr এ ৩টা element
FormatException	         | invalid format	      | int.Parse("abc");
FileNotFoundException	   | ফাইল না পাওয়া	       | File.ReadAllText("missing.txt");
InvalidCastException	    | ভুল type cast	       | (int)"hello";
ArgumentNullException	   | null argument	       | File.ReadAllText(null);
OverflowException	       | numeric overflow	    | checked { int x = int.MaxValue + 1; }
InvalidOperationException| invalid state	       | e.g., closed connection use
TimeoutException	        | সময় শেষ	            | long DB query
OutOfMemoryException	    | মেমোরি ফুরিয়ে গেছে	   | বড় object তৈরি
StackOverflowException	  | infinite recursion	  | function self call
KeyNotFoundException	    | Dictionary key নেই	  | dict["xyz"];
 </pre>






