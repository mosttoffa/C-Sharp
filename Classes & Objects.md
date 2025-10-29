## OOP (Object Oriented Programming) 
🧱 <b>Class কী? </b> <br> 
➡️ The Blueprint of Object. Class হলো একটি blueprint (নকশা) যেটার সাহায্যে তুমি object তৈরি করো। <br> 
  > Definition: A class is a user-defined data type that contains fields, properties, methods, constructors, events, etc. It defines how an object will behave and what data it will hold.
> Memory Concept: Class নিজে মেমোরিতে থাকে না। যখন তুমি new keyword ব্যবহার করো, তখন CLR (Common Language Runtime) heap memory তে object allocate করে। For Example: Car হলো শুধু blueprint (নকশা)। এখন instance তৈরি না করলে এর memory allocate হয় না।

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
 > “Every instance is an object, but when we say instance — we mean the relationship between the object and its class.”

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

🔧 <b>Constructor — </b> Object Initialize করার Systematic উপায় <br> 
🔹 Constructor হলো class-এর ভিতরে একটা বিশেষ method, যেটি object তৈরি হওয়ার সময় automatically call হয়।
<pre>
public class Car
{
    public string Brand;
    public int Speed;

    public Car(string brand, int speed)
    {
        Brand = brand;
        Speed = speed;
    }
}
ব্যবহার: 
  Car car1 = new Car("BMW", 200);
🔹 এখানে constructor:
    Object তৈরি হওয়ার সময় mandatory initialization enforce করে।
    Memory allocate হওয়ার পরই চলে।
</pre>


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

⚙️ <b>Static vs Instance Members </b> 
 * Instance Member	: Object তৈরি করতে হয় ব্যবহার করার আগে
 * Static Member	: Class এর সাথে সরাসরি যুক্ত থাকে, object লাগে না <br> 

🧭 <b>this Keyword — Refers to Current Instance </b> 
<pre>
public class Student
{
    public string Name;
    public Student(string Name)
    {
        this.Name = Name; // 'this' current object কে নির্দেশ করছে
    }
}

</pre>


🔷 Type: Class and Objects are Reference Type <br> 

✅<b>Object is an Instance of a class. <b> <br>
✅ <b>How Objects Exist in Memory: </b> 
 * Reference types (class) → heap এ store হয়
 * Value types (struct, int, bool) → stack এ store হয়
 * Object create হলে CLR “Managed Heap” এ যায়
 * GC (Garbage Collector) periodically unused object clean করে
✅  <b> Memory Behavior (CLR) </b>
 * Stack memory allocation = LIFO (Last In, First Out)
 * Heap memory = managed by Garbage Collector (GC)
 * Reference type destroyed only when no reference points to it
 * Value type destroyed automatically after scope ends
 * Structs embedded in class → stored inside the heap along with class object

✅ <b>Object Composition vs Inheritance </b> 
 * Inheritance: “is-a” relation (Car : Vehicle)
 * Composition: “has-a” relation (Car has Engine)

✅ <b>Anonymous Object (Quick Instance)</b>
<pre>
var product = new { Name = "Laptop", Price = 80000 };
Console.WriteLine(product.Name);
</pre>

🧠 <b>Memory Concept: Stack vs Heap (CLR view) </b>
✅ <b>Stack Memory</b> <br>
 * Short-lived storage (used for local variables, method calls)
 * Automatically managed — cleared when function returns
 * Fast allocation and deallocation

✅ <b>Heap Memory </b> 
 * Used for dynamic objects (like class, array, etc.)
 * Managed by Garbage Collector (GC)
 * Slower, but flexible and persists beyond method calls








