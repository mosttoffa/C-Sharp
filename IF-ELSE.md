## Decision Making Statements In C# 
## IF-ELSE
## NESTED IF-ELSE

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


✅ <b>Loop — What & Why </b> <br>
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
✅ foreach Loop <br>
<pre>
📌 Basic :
foreach(var item in list)
{
    Console.WriteLine(item);
}

📌 Senior-Level Example: API data sync 
foreach (var order in orders)
{
    if (!order.IsSynced)
        SyncToERP(order);
}
⚠️ Performance Notes
foreach slower than for for lists
On large datasets → consider Parallel.ForEach   
</pre>

✅ while & do-while <br>
<pre>
📌 Basic :
while(connection.IsOpen)
{
    ReadMessages();
}

📌 Senior-level: Retry logic (real system)
int retry = 0;
while(retry < 3)
{
    try
    {
        CallAPI();
        break;
    }
    catch
    {
        retry++;
        Task.Delay(1000).Wait();
    }
}

    
</pre>


