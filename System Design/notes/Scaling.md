# Scaling (Horizontal and Vertical)

| Horizontal | Vertical | Comment |
| --- | --- | --- |
| Load balancing required | Load balancing not required |  |
| **Resilient** | Single point of failure |  |
| Network Calls | **Interprocess communication** |  |
| Data inconsistency | **Data consistentency** | In term of transaction where operations need to be atomic |
| **Scales well**	| Hardware limit |  |


### Which One is Right For an Application?
  - Performance requirements or performance characteristics of an application.
  - System throughput
  - System response time
  - System availability requirement
  - Is the system fault-tolerant? If so, what is the degree of it?
  - Is the design reliable?
  - What level of consistency do we care about?
  - What’s the scalability goal of the application (you might have some short-term or immediate one’s goal, but what is going to happen in the long run ?)
