A file used in the [[Initialization State (REF)]] to specify any configuration related to the business process. This can be URLs, file paths, credential names, [[Asset]]s, etc.

Sheets in the configuration file:
- Settings sheet
	- Where we can add Credential assets
- Constants sheet
	- Populated with parameters like:
		- MaxConsecutiveSystemExceptions
			- Sets the maximum limit for consecutive system exceptions
		- RetryNumberGetTransactionItem
		- RetryNumberSetTransactionStatus
		- ShouldMarkJobAsFaulted
			- Set to **TRUE** means a job will be marked as faulted when an error occurs in the initializiation state or when e **MaxConsecutiveSystemExceptions** activates
- Assets sheet
	- Contains references to the [[Asset]]s from the [[Orchestrator]]
	- The format is:
		- | Name | Asset | OrchestratorAssetFolder | Description |

