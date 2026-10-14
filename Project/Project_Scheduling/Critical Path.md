**Critical Path:**

T1 → T2 → T3 → T4 → T6 → T7 → T8



**Activities forming the critical path:**



|ID|Task|Duration (days)|
|-|-|-|
|T1|Requirements \& Database Design|5|
|T2|Develop Process 1.0 (Manage Users \& Access)|5|
|T3|Develop Process 2.0 (Manage Equipment)|6|
|T4|Develop Process 3.0 (Manage Maintenance)|8|
|T6|Develop Processes 5.0 \& 6.0 (Alerts, Reports \& Audit Logs)|6|
|T7|System integration \& testing|7|
|T8|Deployment preparation|3|





**Project duration:** 40 days



**Explanation:**

After T3, the project splits into T4 and T5, and T6 can't start until both finish. T4 finishes on day 24 and T5 on day 23, so T6 waits for T4 and starts on day 25. Using Slack = LS − ES, tasks T1, T2, T3, T4, T6, T7 and T8 all have 0 slack, so any delay in them delays the whole project. T5 has 1 day of slack, so it isn't critical. The project duration is EF(T8) = 40 days, which matches the sum of the critical path durations.



