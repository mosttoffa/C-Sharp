## Decision Making Statements In C# 

✅ <b>If-Else — What & Why </b> <br> 
📌 <b>Definition</b> <br>
Decision making control structure/Decision Making Statements — program কোন condition এ কোন action নেবে সেটা ঠিক করে। <br>
📌 <b>Why Used :</b> Business logic control, Validation, Workflow rules, Access control (RBAC), Feature switches (feature flags), Error handling decision. <br>
📌 Example 
<pre>
📌<b> Basic Example: </b>
if(age >= 18)
    Console.WriteLine("Adult");
else
    Console.WriteLine("Minor");
📌 <b></b>Senior-Level Real Example:</b>
if (user.IsAdmin)
{
    ShowAdminDashboard();
}
else if (user.IsManager)
{
    ShowManagerPanel();
}
else if (user.IsCustomer)
{
    ShowCustomerPortal();
}
else
{
    throw new UnauthorizedAccessException("Unknown user role");
}

</pre>


✅ <b>Loop — What & Why </b>
📌 Definition<br>
Repeating code until a condition meets. <br>
📌 <b>Why Used :</b> Process lists/collections, Batch jobs, Data transform, Retry mechanism, API pagination, Bulk DB updates. <br>
🔷 for Loop : 
<pre>
 📌 Basic :
for(int i = 0; i < 5; i++)
{
    Console.WriteLine(i);
}
 📌Senior-level Example: batch processing
 // Processing records in batches to avoid memory pressure
for(int i = 0; i < records.Count; i += 100)
{
    var batch = records.Skip(i).Take(100);
    ProcessBatch(batch);
}
  
</pre>




