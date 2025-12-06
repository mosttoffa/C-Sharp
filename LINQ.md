## LINQ in C#
# LINQ - Language Integrated Query 
 - Filter করার সুযোগ দেয় 
 - IEnumerable Type, IQuerable Type, List Type  

যাদের উপর Loop চালানো যায় তাদের Enumerable বলে । <br> 
LINQ Apply করতে হলে তাকে IEnumerable বা IQuerable এর Inheritance হতে হবে ।  <br> 

LING ২ ভাবে use করা যায়ঃ 
1. Method Structure 
2. Query Structure
<br> 
1. Method Structure : <br> 
   - Where Clause এর ভিতরে Lambda Expression নেয়
   - Where Return করে ১টা IEnumerable  .ToList();
