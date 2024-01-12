Processes the data.

The possible outcomes:
1. If no exception occurs, the outcome is success and the automation and loops back to the [[Get Data State (REF)
3. If a **Business Rule Exception** occurs, we need to perform a few specific actions, and afterward the execution loops back to the [[Get Transaction Data State (REF)]] state.
4. A **System Exception** triggers the execution of a necessary set of steps to recover from the error. Therefore, all applications are closed, and the execution loops back to the  [[Initialization State (REF)]]  to restart them.

Invoked workflows:
1. Process.xaml
2. SetTransactionStatus.xaml
	- RetryCurrentTransaction.xaml
	- TakeScreenshot.xaml
	- CloseAllApplications.xaml
	- KillAllProcesses.xaml


