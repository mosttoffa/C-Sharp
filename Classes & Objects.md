## OOP (Object Oriented Programming) 
🧱 <b>Class কী? </b> <br> 
➡️ The Blueprint of Object. Class হলো একটি blueprint (নকশা) যেটার সাহায্যে তুমি object তৈরি করো। <br> 
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

    // Method (behavior)
    public void Speak()
    {
        Console.WriteLine($"{Name} is speaking.");
    }
}

🔹এই Human class একটা template — এখন এর object বানানো যাবে।    
 </pre>


🔷 Type: Class and Objects are Reference Type


