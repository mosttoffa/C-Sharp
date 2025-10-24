## Type Casting Or Data Type Conversion in C#

🔷 Two Types of Conversion : 1. Implicit Conversion and 2. Explicit Conversion  <br> 
🔸কি কি Ways তে Casting করা যায় তার Example : <b> (int)b , Convert.ToInt32(), .Parse() </b> 
👉 Basic Example: 
<pre> 
  ---
  int a = 20;
  float b = a;  // <b>implicit data type conversion </b>
  ---
  float b = 20.345f;
  // এইভাবে - <b>(int)b </b> 
  int a = (int)b;  // <b>explicit data type conversion </b>
  অথবা, <b>Convert.ToInt32()</b>
  int a = Convert.ToInt32(b); // <b>explicit data type conversion  </b>
</pre>
👉 Another Example: 
<pre>
  ---
  string a = "40";
  string b = "50";
  // <b>Convert.ToInt32() </b>
  int c = Convert.ToInt32(a) + Convert.ToInt32(b);  <b>explicit data type conversion  </b>
  অথবা,  <b>.Parse()</b>
  int c = int.Parse(a) + int.Parse(b);  <b>explicit data type conversion  </b> 
  অথবা, <b>.Parse()</b> 
  float d = float.Parse(a) + float.Parse(b);
  🔸<b>Parse সব সময় String নেয়/return করে, সেটা int বা double যেটাই হোকনা কেনো।  </b>
  
</pre>

🔶 Data Loss হওয়ার chance থাকলে implicit casting করেনা তখন explicit casting করতে হয়।  <br> 
🔷 

