Also known as a "process diagram".

Before actual development, we whiteboard by breaking the process into smaller reusable components.

Template

| Component Name | Description | Pre-condition | Outcome | Arguments | State |
| ---- | ---- | ---- | ---- | ---- | ---- |
|  |  |  |  |  |  |


Example with the UiDemo process:

| Component Name | Description | Pre-condition | Outcome | Arguments | State |
| ---- | ---- | ---- | ---- | ---- | ---- |
| UiDemo_Open | Opens UiDemo and logs in | UiDemo is installed at the location specified in the Asset	 | UiDemo is open in the correct state	 | in_CredentialName<br>in_UiDemoAppPath | Initialization<br><br> |
| UiDemo_Close | *✨Elegantly✨* closes UiDemo | UiDemo is open and logged into | UiDemo is closed | N/A | Process Transaction<br>End Process |
| UiDemo_ForceClose | Kills the UiDemo process	 | N/A | UiDemo is closed	 | N/A | Initialization<br>Process Transaction<br>End Process |
| UiDemo_AddTransaction | Adds a transaction, gets the number and clicks Accept	 | UiDemo is open and logged into	 | App ready for new transaction	 | in_CashIn<br>in_OnUsCheck<br>In_NotOnUsCheck<br>out_TransactionNumber | Process Transaction<br><br> |


