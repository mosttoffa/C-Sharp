## Type Casting Or Data Type Conversion in C#

🔷 Two Types of Conversion : 1. Implicit Conversion and 2. Explicit Conversion  <br> 
👉 Basic Example: 
<pre> 
  ---
  int a = 20;
  float b = a;  // implicit data type conversion 
  ---
  float b = 20.345f;
  int a = (int)b;  // explicit data type conversion 
  অথবা, 
  int a = Convert.ToInt32(b); // explicit data type conversion  
</pre>


🔶 Data Loss হওয়ার chance থাকলে implicit casting করেনা তখন explicit casting করতে হয়।  <br> 
🔷 

