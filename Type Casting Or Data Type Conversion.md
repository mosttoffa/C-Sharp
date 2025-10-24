## Type Casting Or Data Type Conversion in C#

🔷 Two Types of Conversion : 1. Implicit Conversion and 2. Explicit Conversion  <br> 
👉 Basic Example: 
<pre> 
  ---
  int a = 20;
  float b = a;  // <b>implicit data type conversion </b>
  ---
  float b = 20.345f;
  int a = (int)b;  // <b>explicit data type conversion </b>
  অথবা, 
  int a = Convert.ToInt32(b); // <b>explicit data type conversion  </b>
</pre>
👉 Another Example: 
<pre>
  ---
  string a = "40";
  string b = "50";
  int c = Convert.ToInt32(a) + Convert.ToInt32(b);  <b>explicit data type conversion  </b>
  অথবা, 
  int c = int.Parse(a) + int.Parse(b);  <b>explicit data type conversion  </b> 
  অথবা,
  float d = float.Parse(a) + float.Parse(b);
  <b>Parse সব সময় String নেয়, সেটা int বা double যেটাই হোকনা কেনো।  </b>
  
</pre>

🔶 Data Loss হওয়ার chance থাকলে implicit casting করেনা তখন explicit casting করতে হয়।  <br> 
🔷 

