
## Architecture
- [[Initialization State (REF)]]
- [[Get Transaction Data State (REF)]]
- [[Process Transaction State (REF)]]
- [[End Process State (REF)]]


![[REFrameworkArchitecture.png]]


![[REFrameworkArchitecture2.png]]


Two ways of implementation:
1. With queues
	- The first way focuses on building a project using the REFramework with Orchestrator Queues.
	- For example, this can mean taking the transaction data from the queue and entering it into our UiDemo application.
2. Without queues
	- The second way is instead of using queue items, we use transaction items of a different type such as rows from an Excel file (DataRow), emails (MailMessage), or paths to files (String).




Configuration steps:
1. Prerequisites
	- Make sure the [[robot]] is connected to [[Orchestrator]]
	- Create the queue used in the [[Process]]
	- Set the [[Retry value]]
2. Configuration in UiPath Studio
	- Create a new process with the [[REFramework]] template
	- customize the[[ configuration file]] according to the business process requirements
3. (If without queues)
	-  change the data type for the TransactionItem from the default QueueItem to the one required for the process.
4. Applications used: Open/Close/Kill process
	- Close the [[Application]] required by the [[Process]] and if closing isn't possible, then kill the applications
	- open the [[Application]] required by the [[Process]]
5. Business process: [[Transaction]] data and [[Process]]
	-  


Best Practice:
- The name of the project should have the department name, the name of the template in use, and the name of the process "Department"-"Template"-"Process"
	- i.e. Academy-REF-UiDemo





- The **UiDemo_AddTransactions.xaml** workflow enters transaction data into UiDemo, gets the transaction number and clicks Accept. It is invoked in the 'Process' file.
- Whenever **Get Transaction Item** or **Set Transaction Status** fail as the error handling for these two  workflows catches the System.Exception type, the retry scope prevents the following scenarios:
    - **For the Get Transaction Item**
        - If Orchestrator queues are used, the transaction retrieval is handled by the **Get Transaction Item** activity, which is included by default, so it is not necessary to make any modifications to **GetTransactionData.xaml** workflow.
        - To increase the number of retries, we must update the **R****etryNumberGetTransactionItem** Constant in the Configuration file.
    - **For the Set Transaction Status**
        - After the **Process.xaml** workflow has been executed, the **SetTransactionStatus.xaml** workflow is called, which sets the status of the transaction according to the result of the processing step.
        - The status of an Orchestrator queue item is automatically updated by the **Set Transaction Status** activity if the process' data source is an Orchestrator queue.
        - An issue was resolved in which a queue item was marked as "**Successful**" when a process was killed:
            - In the Finally block, **Framework/SetTransactionStatus.xaml** was no longer invoked.
            - An invocation of **Framework\SetTransactionStatus.xaml** (surrounded by a **Try Catch** activity) was added after the invocation of **Framework\Process.xaml**, for the successful cases, in the same **Try** block.
            - On the **Catch** section, an invocation of **Framework\SetTransactionStatus.xaml** (surrounded by a Try Catch activity) was added for each type of exception (System Exception or Business Rule Exception).
        - To increase the number of retries, we must update the **RetryNumberGetTransactionItem** Constant in the Configuration file.


**REFramework without Queue Items Checklist:**

![[REFramework without Queue Items Checklist 1.pdf]]

