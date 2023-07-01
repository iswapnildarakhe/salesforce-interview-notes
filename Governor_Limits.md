#### 1. What are Governor Limits and why are they in Salesforce?
- We know that Salesforce works as a Multi-Tenant Environment.
- So, the users should get equal resources and no one should have Monopoly over the Resources.
- And to ensure this Salesforce has enforced a Governor Limits.
- When a governor limit is surpassed or violated, Salesforce shows an error and pauses the process that caused the error.
___
#### 2. List all Governor Limits.
There are types of Governor Limits
1. **Per-Transaction Apex Limits** <br/>
**NOTE** : These limits will reset for per execute() method run of Batch Class

|Functionality|Synchronous Limit|Asynchronous Limit|
|---|---|---|
|1. SOQL's allowed per Transaction|100|200|
|2. Number of Records fetched by 1 SOQL|50,000|50,000|
|3. SOSL's allowed per Transaction|20|20|
|4. Number of Records fetched by 1 SOSL|2,000|2,000|
|5. DML's allowed per Transaction|150|150|
||||
|6. Number of Records Processed by 1 DML|10,000|10,000|
|7. Total stack depth for any Apex invocation that recursively fires triggers due to insert, update, or delete statements|16|16|
|8. Maximum number of methods with the future annotation allowed per Apex invocation|50|0 in batch and future contexts; 50 in queueable context|
|9. Maximum number of Apex jobs added to the queue with System.enqueueJob|50|1|
|10. Total heap size|6MB|12MB|
|11. Maximum CPU time on the Salesforce servers|10,000 milliseconds|60,000 milliseconds|
|12. Maximum execution time for each Apex transaction|10 Minutes|10 Minutes|

2. **Lightning Platform Apex Limits**

| Functionality                                                         | Limits                                     |
| --------------------------------------------------------------------- | ------------------------------------------ |
| 1. Number of Manual Asynchronous Apex runs                            | 200 * number of licence in org OR 2Lakh50K |
| 2. Maximum number of batch Apex jobs queued or active concurrently    | 5                                          |
| 3. Maximum number of batch Apex job start method concurrent execution | 1                                          |

3. **Static Apex Limits**

|Functionality|Limits|
|---|---|
|1.Maximum SOQL query run time before Salesforce cancels the transaction|120 seconds|
|2. Maximum number of Classes and Triggers that you can Deploy at once|7,500|
|3. Apex trigger batch size|Default 200 Maximum 2000|
|4. For loop list batch size|200|
|5. Maximum number of records returned for a Batch Apex query in Database.QueryLocator|50 Million i.e. 500 Lakh|

4. **Size-Specific Apex Limits**

|Functionality|Limits|
|---|---|
|1. Maximum number of characters for a class|1 Million or 10 Lakh|
|2. Maximum number of characters for a trigger|1 Million 10 Lakh|
|3. Maximum amount of code used by all Apex code in an org|6 MB|

____
#### 3. Whats the Difference between Per Apex Invocation and Per Apex Transaction

| Per Apex Invocation                                                           | Per Apex Transaction                                                                                                                                |
| ----------------------------------------------------------------------------- | --------------------------------------------------------------------------------------------------------------------------------------------------- |
| Per Apex Invocation means whenever you run a Apex code or a Trigger is Fired. | Per Apex Transaction means <br/>1. You ran a Apex method but called other methods<br/>2. A apex Trigger triggered another apex Trigger or workflow. |

____
#### 4. What is Heap Size
- Heap size is the memory allocated for running the Apex Code for per Transaction.
- It is the amount of memory allocated to store variables, objects, and other data during the execution of your code.
- For Synchronous it is 6 MB and for Asynchronous it is 12 MB.
___
# Create a Doc that explains the limit and how to bypass them ex: by using Batch Apex you can dml more than 1000 records
____
