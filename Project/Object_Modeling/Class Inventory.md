#### **Individual Class Inventory**



Member A - Zeerak -

|**Class ID**|**Class Name**|**Purpose/Responsibility**|**Related Use Case(s)**|**Contributor**|
|-|-|-|-|-|
| C01 | Equipment | Stores core medical device details (ID, serial number, model, status, location) and manages operational availability. | UC-03, UC-05, UC-14, UC-21 | Zeerak Kamil |
| C02 | Document | Manages uploaded files including equipment manuals, service contracts, warranties, and calibration certificates. | UC-08, UC-18, UC-20 | Zeerak Kamil |
| C03 | SparePart | Tracks spare parts stock levels, unit costs, minimum reorder thresholds, and parts deducted per repair job. | UC-19 | Zeerak Kamil |
| C04 | LocationHistory | Records each change of an equipment item's location (previous/new location, who moved it, and when) so location history can be viewed. | UC-07 | Zeerak Kamil |



Member B - Aaditya N -

|**Class ID**|**Class Name**|**Purpose/Responsibility**|**Related Use Case(s)**|**Contributor**|
|-|-|-|-|-|
|C05|User|<br />Base account entity handling authentication credentials, contact details, role <br />permissions, and active status.<br /><br />|UC-06, UC-11|Aaditya Agarwal|
|C06|Technician|<br />Inherits from User; represents specialized maintenance personnel who perform repair jobs and update asset locations.<br />|UC-07|Aaditya Agarwal|
|C07|AuditLog|Implements an immutable, tamper-evident log capturing user actions (create, update, delete) with timestamps|UC-01|Aaditya Agarwal|
|C08|Role|Defines a named role and its permissions; each User is assigned exactly one Role.|UC-06|Aaditya Agarwal|







Member C - Adithya B -



|**Class ID**|**Class Name**|**Purpose/Responsibility**|**Related Use Case(s)**|**Contributor**|
|-|-|-|-|-|
|C09|MaintenanceSchedule|<br />Manages recurring preventive maintenance rules, frequency intervals, and automatic due date calculations.<br />|UC-02|Adithya Vagheeswar|
|C10|WorkOrder|<br />Manages corrective and preventive maintenance jobs, technician assignments, downtime tracking, and repair costs.<br />|UC-10, UC-12, UC-17|Adithya Vagheeswar|
|C11|Vendor|<br />Represents external service vendors who can be assigned to corrective work orders, with contact and service details.<br />|UC-12|Adithya Vagheeswar|
|C12|Checklist|<br />Holds the maintenance checklist items for a work order and tracks their completion.<br />|UC-09|Adithya Vagheeswar|







Member D - Azim -

