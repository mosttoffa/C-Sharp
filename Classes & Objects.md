## OOP (Object Oriented Programming) 
🧱 <b>Class কী? </b> <br> 
➡️ The Blueprint of Object. Class হলো একটি blueprint (নকশা) যেটার সাহায্যে তুমি object তৈরি করো। <br> 
  > Definition: A class is a user-defined data type that contains fields, properties, methods, constructors, events, etc. It defines how an object will behave and what data it will hold. <br>
🔷<b>একটা class define করে — </b> 
 * কী কী property (data) থাকবে
 * কী কী method (behavior) থাকবে <br>
🔹 উদাহরণ দিয়ে বললে — একটা “Human” class ভাবো। প্রতিটা মানুষ object, কিন্তু তাদের একটা common structure আছে — name, age, talk(), walk() ইত্যাদি। <br> 
<pre>
public class Human
{
    // Properties (data)
    public string Name { get; set; }
    public int Age { get; set; }
    🔹<b> এইখানে Name, Age হলো Human class এর Property </b>
    // Method (behavior)
    public void Speak()
    {
        Console.WriteLine($"{Name} is speaking.");
    }
}

🔹এই Human class একটা template — এখন এর object বানানো যাবে।    
 </pre>
<p>
🔹 <b>কেন Class ব্যবহার করা হয়?</b> <br> 
Class ব্যবহার করা হয় real-world system বা concept-কে প্রোগ্রামিংয়ের মধ্যে বাস্তবভাবে উপস্থাপন করার জন্য।
এটা আমাদের data (তথ্য) এবং behavior (কাজ করার ধরন) — দুটোকে একসাথে ধরে রাখে।
</p>
<b>👤 Instance কী? </b> <br>

➡️ যখন তুমি কোনো class থেকে একটা object তৈরি করো, তখন সেটাকে বলে instance।

🔹 অর্থাৎ Class হলো নকশা, আর Instance হলো বাস্তব object।
উদাহরণ:
<pre>
Human h1 = new Human();   // Human class-এর একটা instance
h1.Name = "Mostofa";
h1.Age = 25;
h1.Speak();   // Output: Mostofa is speaking.

    🧠 এখানে:
    Human → Class
    h1 → Human-এর একটা instance (object)
    Name ও Age → Class এর properties
    Speak() → Class এর method
</pre>
🧠 <b>কিভাবে Property তে Value Assign হয় </b> <br> 
🔸 Step 1: Object Create করা
<pre>Student s1 = new Student();</pre>
🔸 Step 2: Property তে Value Assign করা
<pre>s1.Name = "Mostofa";</pre>

🧾 <b>Property তে value assign করার ৩টা উপায়: </b> <br> 
1️⃣ Direct Assignment (Object তৈরি হওয়ার পরে):
<pre>
Human h = new Human();
h.Name = "Rakib";
h.Age = 28;
</pre>
2️⃣ Object Initializer (short form):
<pre>
Human h = new Human { Name = "Sadia", Age = 22 };
</pre>
3️⃣ Constructor এর মাধ্যমে:
তুমি চাইলে class তৈরি করার সময়ই property set করতে পারো।
<pre>
public class Human
{
    public string Name { get; set; }
    public int Age { get; set; }

    // Constructor
    public Human(string name, int age)
    {
        Name = name;
        Age = age;
    }
}
<b>ব্যবহার:  </b>
Human h = new Human("Rafi", 30);
Console.WriteLine(h.Name); // Rafi
</pre>
<p>
🎯 Class কেন ব্যবহার করা হয়? : Code Reusability, Encapsulation-Data (property) ও Function (method) একসাথে রাখা যায়, Data Protection- Property কে private/public করে control করা যায়. Maintainability- বড় প্রোজেক্টে কোড manage করা সহজ হয়. Real World Mapping- বাস্তব জগতের entity (Student, Product, Employee) কে কোডে উপস্থাপন করা যায়. 
</p>


🔷 Type: Class and Objects are Reference Type


Object is an Instance of a class.

