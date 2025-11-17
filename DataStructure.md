## C# Data Structure 

C#-এ ডেটা স্ট্রাকচারগুলিকে প্রধানত দু'টি ভাগে ভাগ করা যায়:  <br>
1. নন-জেনেরিক (Non-Generic) এবং
2. জেনেরিক (Generic)। 

এই দু'ধরনের ডেটা স্ট্রাকচারই ডেটা সংরক্ষণ, সাজানো এবং পরিচালনার জন্য ব্যবহৃত হয়, কিন্তু তাদের ব্যবহারের পদ্ধতি, কর্মক্ষমতা (Performance) এবং ডেটা নিরাপত্তা (Type Safety)-তে মৌলিক পার্থক্য রয়েছে। <br> 
১. নন-জেনেরিক কালেকশন (Non-Generic Collections) : <br> 
নন-জেনেরিক কালেকশনগুলি হল C#-এর প্রথম দিককার কালেকশন, যা ডেটা সংরক্ষণ করার জন্য System.Collections নেমস্পেস ব্যবহার করে। <br> 

প্রধান বৈশিষ্ট্য: <br> 

    টাইপ সেফটি নেই (No Type Safety): এই কালেকশনগুলি যেকোনো ধরনের ডেটা (int, string, কাস্টম ক্লাস, ইত্যাদি) সংরক্ষণ করতে পারে, কিন্তু এটি শুধুমাত্র object টাইপ হিসেবে ডেটা সংরক্ষণ করে। <br> 
    বক্সিং এবং আনবক্সিং (Boxing and Unboxing): যখন আপনি একটি ভ্যালু টাইপ (যেমন int) নন-জেনেরিক কালেকশনে যোগ করেন, তখন সেটি বক্সিং প্রক্রিয়ায় object টাইপে রূপান্তরিত হয়ে হিপ মেমরিতে চলে যায়। ডেটা ব্যবহার করার সময় আবার সেটি আনবক্সিং প্রক্রিয়ায় আসল টাইপে ফিরে আসে। <br> 
        সমস্যা: এই প্রক্রিয়াটি মেমরি ব্যবহার বাড়ায় এবং অ্যাপ্লিকেশনকে ধীরগতিসম্পন্ন করে তোলে। <br> 
    রানটাইম ত্রুটি (Runtime Errors): যেহেতু কম্পাইলার ডেটার সঠিক টাইপ যাচাই করে না, তাই ভুল টাইপের ডেটা যোগ করার ফলে রানটাইমে (Runtime) ত্রুটি হতে পারে। <br> 


উদাহরণ: <br> 
```
  কালেকশন ক্লাস                               বর্ণনা
ArrayList              সাইজ পরিবর্তনযোগ্য অ্যারে (Dynamic Array)। এটি যেকোনো টাইপের ডেটা সংরক্ষণ করতে পারে।
Hashtable              কী-ভ্যালু (Key-Value) পেয়ারে ডেটা সংরক্ষণ করে। কী এবং ভ্যালু উভয়ই object হিসেবে সংরক্ষিত হয়।
Stack                  "LIFO (Last-In, First-Out) নীতির উপর ভিত্তি করে ডেটা সংরক্ষণ করে।"
Queue                  "FIFO (First-In, First-Out) নীতির উপর ভিত্তি করে ডেটা সংরক্ষণ করে।"
```

২. জেনেরিক কালেকশন (Generic Collections) :  <br> 
জেনেরিক কালেকশনগুলি আধুনিক C# (সাধারণত .NET 2.0 থেকে) এর অংশ এবং এগুলি System.Collections.Generic নেমস্পেস ব্যবহার করে। ASP.NET সহ যেকোনো আধুনিক C# ডেভেলপমেন্টে এগুলিই বেশি ব্যবহৃত হয়। <br> 

প্রধান বৈশিষ্ট্য: <br> 

    টাইপ সেফটি (Type Safety): কালেকশনটি তৈরি করার সময়ই আপনি নির্দিষ্ট করে দেন যে এটি কোন ধরনের ডেটা সংরক্ষণ করবে (যেমন: List<int>)। কম্পাইলার নিশ্চিত করে যে ভুল টাইপের ডেটা যেন কালেকশনে প্রবেশ করতে না পারে।  <br>
    বক্সিং/আনবক্সিং এড়িয়ে চলা: যেহেতু টাইপটি নির্দিষ্ট করা থাকে, তাই ভ্যালু টাইপগুলি object টাইপে রূপান্তরিত হয় না। এর ফলে কোনো বক্সিং বা আনবক্সিং হয় না। <br> 
        সুবিধা: এটি কর্মক্ষমতা (Performance) বাড়ায় এবং মেমরি ব্যবহার কমায়। <br> 
    কম্পাইলটাইম ত্রুটি (Compile-time Errors): ডেটা টাইপ সংক্রান্ত যেকোনো ত্রুটি রানটাইমের পরিবর্তে কম্পাইল করার সময়ই ধরা পড়ে। <br> 

উদাহরণ: <br> 
```
  কালেকশন ক্লাস                                        বর্ণনা
List<T>                           জেনেরিক ArrayList-এর সমতুল্য। সর্বাধিক ব্যবহৃত কালেকশন। T হলো টাইপ প্লেসহোল্ডার।
"Dictionary<TKey, TValue>"        জেনেরিক Hashtable-এর সমতুল্য। দ্রুত ডেটা অনুসন্ধানের জন্য ব্যবহৃত হয়।
Stack<T>                          জেনেরিক LIFO কালেকশন।
Queue<T>                          জেনেরিক FIFO কালেকশন।
HashSet<T>                        ডেটার ডুপ্লিকেট (Duplicate) এড়িয়ে শুধুমাত্র অনন্য (Unique) আইটেম সংরক্ষণ করার জন্য।
```

🆚 সারসংক্ষেপ: পার্থক্য <br> 
```
  বৈশিষ্ট্য                        নন-জেনেরিক কালেকশন (যেমন: ArrayList)                    জেনেরিক কালেকশন (যেমন: List<int>)
প্রধান টাইপ            object                                                    <T> (নির্দিষ্ট টাইপ)
টাইপ সেফটি            নেই (No Type Safety)                                      আছে (Type Safe)
কর্মক্ষমতা              ধীরগতিসম্পন্ন (Boxing/Unboxing-এর কারণে)                    দ্রুতগতিসম্পন্ন (Boxing/Unboxing হয় না)
ব্যবহৃত নেমস্পেস        System.Collections                                        System.Collections.Generic
ব্যবহারের সুপারিশ       আধুনিক C# প্রোজেক্টে এড়িয়ে চলা উচিত।                         আধুনিক C# প্রোজেক্টে সর্বদা ব্যবহার করা উচিত।
```

🛒 C# জেনেরিক কালেকশন উদাহরণ :<br> 
জেনেরিক কালেকশন List<T> এবং Dictionary<TKey, TValue> ব্যবহার করে C# কোডের একটি উদাহরণ নিচে দেওয়া হলো। <br> 

এই উদাহরণে আমরা Product নামক একটি কাস্টম ক্লাস (Class) তৈরি করব এবং এই ক্লাসকে ডেটা টাইপ হিসেবে জেনেরিক কালেকশনগুলিতে ব্যবহার করব।

```
using System;
using System.Collections.Generic;

// 1. কাস্টম রেফারেন্স টাইপ (Product Class) তৈরি
public class Product
{
    public int Id { get; set; }
    public string Name { get; set; }
    public decimal Price { get; set; }
}

public class CollectionDemo
{
    public static void Main(string[] args)
    {
        Console.OutputEncoding = System.Text.Encoding.UTF8;

        // --- List<T> ব্যবহার (T এখানে Product) ---
        
        Console.WriteLine("## List<Product> ব্যবহার:");
        
        // List<T> তৈরি: এটি Product টাইপের একটি ডাইনামিক অ্যারে
        List<Product> productList = new List<Product>();
        
        // ডেটা যোগ করা (Add Method)
        productList.Add(new Product { Id = 101, Name = "ল্যাপটপ", Price = 55000.00m });
        productList.Add(new Product { Id = 102, Name = "মাউস", Price = 800.00m });
        productList.Add(new Product { Id = 103, Name = "কিবোর্ড", Price = 1200.00m });
        
        // ডেটা অ্যাক্সেস করা এবং লুপ করা
        Console.WriteLine($"মোট প্রোডাক্ট সংখ্যা: {productList.Count}");
        Console.WriteLine("লিস্টের প্রথম প্রোডাক্ট: " + productList[0].Name);

        Console.WriteLine("\n--- সমস্ত প্রোডাক্টের তালিকা (List) ---");
        foreach (var product in productList)
        {
            // কম্পাইলার জানে এটি একটি Product অবজেক্ট, তাই .Name ব্যবহার করা নিরাপদ।
            Console.WriteLine($"ID: {product.Id}, নাম: {product.Name}, দাম: {product.Price} টাকা");
        }

        Console.WriteLine("------------------------------------------");

        // --- Dictionary<TKey, TValue> ব্যবহার (TKey: int, TValue: Product) ---
        
        Console.WriteLine("## Dictionary<int, Product> ব্যবহার:");
        
        // Dictionary তৈরি: এটি Key (int, যেমন: প্রোডাক্ট ID) এবং Value (Product অবজেক্ট) পেয়ারে ডেটা সংরক্ষণ করে।
        Dictionary<int, Product> productDictionary = new Dictionary<int, Product>();
        
        // ডেটা যোগ করা (Add Method)
        productDictionary.Add(101, productList[0]); // ল্যাপটপ
        productDictionary.Add(102, productList[1]); // মাউস
        productDictionary.Add(103, productList[2]); // কিবোর্ড
        
        // Key ব্যবহার করে দ্রুত ডেটা খুঁজে বের করা (খুবই দ্রুত)
        int searchId = 102;
        if (productDictionary.ContainsKey(searchId))
        {
            Product foundProduct = productDictionary[searchId]; // O(1) অর্থাৎ দ্রুত অ্যাক্সেস
            Console.WriteLine($"\nKey {searchId} দ্বারা প্রাপ্ত প্রোডাক্ট: {foundProduct.Name}, দাম: {foundProduct.Price} টাকা");
        }

        Console.WriteLine("\n--- সমস্ত প্রোডাক্টের তালিকা (Dictionary) ---");
        foreach (var kvp in productDictionary) // kvp = KeyValuePair
        {
            // kvp.Key = int এবং kvp.Value = Product
            Console.WriteLine($"Key: {kvp.Key} -> নাম: {kvp.Value.Name}");
        }
    }
}
```

নিশ্চয়ই, জেনেরিক কালেকশন List<T> এবং Dictionary<TKey, TValue> ব্যবহার করে C# কোডের একটি উদাহরণ নিচে দেওয়া হলো।

এই উদাহরণে আমরা Product নামক একটি কাস্টম ক্লাস (Class) তৈরি করব এবং এই ক্লাসকে ডেটা টাইপ হিসেবে জেনেরিক কালেকশনগুলিতে ব্যবহার করব।

🛒 C# জেনেরিক কালেকশন উদাহরণ

C#

using System;
using System.Collections.Generic;

// 1. কাস্টম রেফারেন্স টাইপ (Product Class) তৈরি
public class Product
{
    public int Id { get; set; }
    public string Name { get; set; }
    public decimal Price { get; set; }
}

public class CollectionDemo
{
    public static void Main(string[] args)
    {
        Console.OutputEncoding = System.Text.Encoding.UTF8;

        // --- List<T> ব্যবহার (T এখানে Product) ---
        
        Console.WriteLine("## List<Product> ব্যবহার:");
        
        // List<T> তৈরি: এটি Product টাইপের একটি ডাইনামিক অ্যারে
        List<Product> productList = new List<Product>();
        
        // ডেটা যোগ করা (Add Method)
        productList.Add(new Product { Id = 101, Name = "ল্যাপটপ", Price = 55000.00m });
        productList.Add(new Product { Id = 102, Name = "মাউস", Price = 800.00m });
        productList.Add(new Product { Id = 103, Name = "কিবোর্ড", Price = 1200.00m });
        
        // ডেটা অ্যাক্সেস করা এবং লুপ করা
        Console.WriteLine($"মোট প্রোডাক্ট সংখ্যা: {productList.Count}");
        Console.WriteLine("লিস্টের প্রথম প্রোডাক্ট: " + productList[0].Name);

        Console.WriteLine("\n--- সমস্ত প্রোডাক্টের তালিকা (List) ---");
        foreach (var product in productList)
        {
            // কম্পাইলার জানে এটি একটি Product অবজেক্ট, তাই .Name ব্যবহার করা নিরাপদ।
            Console.WriteLine($"ID: {product.Id}, নাম: {product.Name}, দাম: {product.Price} টাকা");
        }

        Console.WriteLine("------------------------------------------");

        // --- Dictionary<TKey, TValue> ব্যবহার (TKey: int, TValue: Product) ---
        
        Console.WriteLine("## Dictionary<int, Product> ব্যবহার:");
        
        // Dictionary তৈরি: এটি Key (int, যেমন: প্রোডাক্ট ID) এবং Value (Product অবজেক্ট) পেয়ারে ডেটা সংরক্ষণ করে।
        Dictionary<int, Product> productDictionary = new Dictionary<int, Product>();
        
        // ডেটা যোগ করা (Add Method)
        productDictionary.Add(101, productList[0]); // ল্যাপটপ
        productDictionary.Add(102, productList[1]); // মাউস
        productDictionary.Add(103, productList[2]); // কিবোর্ড
        
        // Key ব্যবহার করে দ্রুত ডেটা খুঁজে বের করা (খুবই দ্রুত)
        int searchId = 102;
        if (productDictionary.ContainsKey(searchId))
        {
            Product foundProduct = productDictionary[searchId]; // O(1) অর্থাৎ দ্রুত অ্যাক্সেস
            Console.WriteLine($"\nKey {searchId} দ্বারা প্রাপ্ত প্রোডাক্ট: {foundProduct.Name}, দাম: {foundProduct.Price} টাকা");
        }

        Console.WriteLine("\n--- সমস্ত প্রোডাক্টের তালিকা (Dictionary) ---");
        foreach (var kvp in productDictionary) // kvp = KeyValuePair
        {
            // kvp.Key = int এবং kvp.Value = Product
            Console.WriteLine($"Key: {kvp.Key} -> নাম: {kvp.Value.Name}");
        }
    }
}

💡 এই উদাহরণ থেকে কী শিখলেন? <br> 
    টাইপ সেফটি: আমরা List<Product> এবং Dictionary<int, Product> তৈরি করেছি। এতে নিশ্চিত হলো যে এই কালেকশনগুলিতে ভুল করে অন্য কোনো টাইপের ডেটা (যেমন শুধু int বা string) যোগ করা যাবে না। এটি কম্পাইল করার সময়ই ত্রুটি ধরে ফেলে।
    সহজ ব্যবহার: ডেটা অ্যাক্সেস করার সময় আপনাকে টাইপ কাস্টিং (Type Casting) করতে হচ্ছে না (যেমনটা নন-জেনেরিক ArrayList-এ করতে হতো)। যখন আমরা foreach (var product in productList) লুপ করি, তখন product সরাসরি একটি Product অবজেক্ট হিসেবেই আসে।
    দক্ষতা (Efficiency): Dictionary<TKey, TValue> আমাদেরকে Key ব্যবহার করে অতি দ্রুত (সাধারণত O(1) সময়ে) ডেটা খুঁজে বের করার সুবিধা দেয়, যা ডেটাবেস অ্যাপ্লিকেশনগুলির জন্য খুবই কার্যকর।






কোথায় Generic, কোথায় Non-Generic use হয়? 









