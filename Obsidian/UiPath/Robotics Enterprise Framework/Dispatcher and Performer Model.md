

The two main stages of a process involving queues are separated as follows:

1. The stage in which data is read, organized and fed into a queue in Orchestrator is called [[Dispatcher]] or Producer.
2. The stage in which the queue data is processed is called [[Performer]] or Consumer.


Example:

We can use the **Dispatcher and Performer model** in the following manner:

1. **The [[Dispatcher]]** reads rows from the input spreadsheet and adds the data (i.e., name and email) to a queue; each queue item will have both name and email from one spreadsheet row.
2. **The [[Performer]]** retrieves an item from the same queue and does the necessary actions using that data, like replacing template values and sending an email.
