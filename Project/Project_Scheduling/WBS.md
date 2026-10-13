| ID | Task Name | Description | Predecessor(s) | Duration (Days) |  
| :--- | :--- | :--- | :--- | :--- |  
| T1 | Requirements & Database Design | Refine requirements and design the database schemas for all D1-D5 data stores. | — | 5 |  
| T2 | Develop Process 1.0 (Manage Users & Access) | Develop the system that authenticates sessions, manages access roles across the hospital staff, and logs security events | T1 | 5 |  
| T3 | Develop Process 2.0 (Manage Equipment) | Create the part that registers new medical equipment, generates tracking QR codes, manages the asset lifecycle (transfers/disposals), and provides real-time status updates. | T2 | 6 |  
| T4 | Develop Process 3.0 (Manage Maintenance) | Make the process that processes fault reports, dispatches work orders to technicians or external vendors, and tracks repair status, and equipment downtime | T3 | 8 |  
| T5 | Develop Process 4.0 (Manage Documents, Warranties & Spare Parts) | Develop the process that stores critical compliance documentation, tracks spare parts inventory, deducts parts utilized during maintenance jobs, and flags low stock levels | T3 | 7 |  
| T6 | Develop Processes 5.0 & 6.0 (Alerts, Reports & Audit Logs) | Make the process that monitors system records to dispatch email alerts, and aggregates data to generate compliance audits and performance dashboards | T4, T5 | 6 |  
| T7 | System integration & testing | Integrate all HEM-Track processes, resolve data flow bugs, and perform quality assurance and security testing | T6 | 7 |  
| T8 | Deployment preparation | Deploy the HEM-Track system to the hospital environment and prepare documentation for hospital staff rollout | T7 | 3 |   `
