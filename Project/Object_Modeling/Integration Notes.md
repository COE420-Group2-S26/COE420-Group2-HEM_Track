#### **Integration Notes**



Member A (Zeerak Kamil)

Classes: C01 Equipment, C02 Document, C03 SparePart, C04 LocationHistory

Equipment, Document, SparePart and LocationHistory went into the team diagram exactly as in my individual diagram, with no renaming and no duplicates. None of them has a subclass or a superclass.



Relationships



* Equipment has Document (1 to 0..\*): every document belongs to one equipment item, and an item can have many documents (FR-08, UC-08, UC-20).
* Document describes SparePart (0..\* to 0..\*): one document can cover several parts, and a part can appear in several documents.
* Equipment compatible with SparePart (0..\* to 0..\*): a part can fit many equipment items, and an item can accept many parts.
* Equipment has history LocationHistory (1 to 0..\*): each location change is saved as its own record (FR-07, UC-07).
* User uploaded by Document (1 to 0..\*): this is Member B's link, drawn into Document (UC-08, UC-20).
* Technician updates location of Equipment (dependency): the technician triggers the move and Equipment owns the data. This is Member B's link (UC-07).
* Equipment follows MaintenanceSchedule (1 to 0..\*) and Equipment repaired through WorkOrder (1 to 0..\*): these are Member C's links, drawn into Equipment (FR-02, UC-02, UC-10, UC-17).
* SparePart uses parts WorkOrder (0..\* to 0..\*): this is Member C's link (UC-19).
* Alert monitors Equipment warranty and SparePart stock (dependencies): these are Member D's links. Alert only reads the data (FR-17, FR-20, UC-18, UC-19).



Design choices



* Equipment stores only the current location. Past locations go in LocationHistory, so a move never overwrites an old record.
* Document is its own class because an item has many files, each with a type, expiry date and uploader. It stores only equipmentId and uploadedBy as IDs, so access control stays in Member B's classes.
* Compatibility is an association between SparePart and Equipment instead of an attribute, because a part can fit many equipment items.
* SparePart's deductStock takes a workOrderId, so every deduction can be traced to a repair job (FR-20).
* Alert raises the warranty and low-stock alerts and only reads the data. Equipment and SparePart keep the data they own, such as warrantyExpiry and minThreshold.





Member B (Aaditya N)-



Classes: C05 User, C06 Technician, C07 AuditLog, C08 Role

User, Technician, AuditLog and Role went into the team diagram exactly as in my individual diagram, with no renaming and no duplicates. Technician still inherits from User.



Relationships



* Role assigned to User (1 to 0..\*): one role per user, and a role can be shared by many users.
* User performs AuditLog (1 to 0..\*): every action is logged with a user ID (FR-01).
* Technician inherits from User: a technician is a user with extra info like specialization and isAvailable.
* Technician actions logged in AuditLog (1 to 0..\*): already covered by the User link, but we keep it so it's clear technician actions are always audited.
* User uploaded by Document (1 to 0..\*): shows who uploaded each file (UC-08, UC-20).
* Technician updates location of Equipment (dependency): Technician triggers the move and Equipment owns the data (UC-07).
* Technician assigned to WorkOrder (1 to 0..\*): one technician, many jobs (FR-12). Vendors are handled by the Vendor link on WorkOrder.
* Report requested by User (0..\* to 1) and Alert sent to User (0..\* to 1): tie Member D's classes back to users.



Design choices

* AuditLog uses generic entityName and entityId instead of linking to every class, so the diagram stays readable and every DFD process can log to D5.
* Role is its own class because FR-06 says the admin can modify role permissions, and it saves us from making 8 role subclasses.
* Technician is the only subclass of User, since the other roles only differ in permissions, which Role covers.





Member C (Adithya Vagheeswar)-



Classes: C09 MaintenanceSchedule, C10 WorkOrder, C11 Vendor, C12 Checklist

MaintenanceSchedule, WorkOrder, Vendor and Checklist went into the team diagram exactly as in my individual diagram, with no renaming and no duplicates. None of them has a subclass or a superclass.



Relationships



* MaintenanceSchedule generates WorkOrder (0..1 to 0..\*): a preventive work order comes from one schedule, and one schedule produces many work orders over time. The schedule end is 0..1 because corrective work orders have no schedule (FR-02, UC-02).
* WorkOrder performed by Vendor (0..\* to 0..1): a job can optionally be outsourced to one vendor, and a vendor can be used on many jobs (FR-12, UC-12, P3).
* WorkOrder includes Checklist (1 to 0..\*): every checklist belongs to exactly one work order, and a work order can have several (FR-09, UC-09, P3).
* Technician assigned to WorkOrder (1 to 0..\*): one technician, many jobs. This is Member B’s link, drawn into WorkOrder (UC-10, UC-17).
* Equipment follows MaintenanceSchedule (1 to 0..\*): each schedule is for one equipment item, and an item can follow several schedules (FR-02, UC-02).
* Equipment repaired through WorkOrder (1 to 0..\*): the full repair history of an item is kept in its work orders (UC-10, UC-17).
* SparePart uses parts WorkOrder (0..\* to 0..\*): a job can consume several parts, and a part can be used on many jobs (UC-19).
* Alert monitors MaintenanceSchedule due dates (dependency): Alert reads nextDueDate and does not own the data (UC-04).
* Report aggregates WorkOrder cost and downtime (dependency): Report summarises repairCost and downtimeHours without storing them (UC-16).



Design choices



* WorkOrder uses an orderType attribute (Preventive | Corrective) instead of two subclasses. They share all attributes and methods and differ only in whether a schedule exists, so a subclass would not add anything. This also keeps Technician as the only inheritance relationship in the model.
* scheduleId can be empty on a work order, which is why the schedule end of the link is 0..1.
* Vendor is its own class because an outside vendor has its own contact and service details and is reused across many work orders. We store only vendorId on WorkOrder.
* Checklist is its own class because a work order has many checklist items to complete (FR-09). Putting them in WorkOrder would make it too large.
* MaintenanceSchedule supports usage-based as well as calendar-based triggers. usageHoursThreshold, currentUsageHours and isUsageDue() were added for FR-02.
* WorkOrder has a faultDescription attribute so a corrective job records what failed (FR-19, UC-17).
* Cost and downtime are calculated by WorkOrder (calculateTotalCost(), calculateDowntime()). Report only aggregates them, so the numbers have one source.
* WorkOrder links to Technician and Equipment through IDs and associations. It has no direct link to User, so access control stays in Member B’s classes.



Member D (Azim Mohamed) -



Classes: C13 Alert, C14 Report

Alert and Report went into the team diagram exactly as in my individual diagram, with no renaming and no duplicates. Neither of them has a subclass or a superclass.



Relationships



* Alert summarized in Report (0..\* to 0..\*): reports can include alert history, and one alert can appear in many reports. In the team diagram, both classes are instead linked to User and to the data they read, which covers this.
* Alert sent to User (0..\* to 1): every alert has one recipient, and a user can receive many alerts (FR-04, UC-04, UC-18).
* Report requested by User (0..\* to 1): every report is generated by one user, and a user can generate many reports (FR-16, UC-16).
* Alert monitors MaintenanceSchedule due dates (dependency): Alert reads nextDueDate from Member C's class and does not own it (FR-04, UC-04).
* Alert monitors warranty on Equipment and stock on SparePart (dependencies): Alert reads warrantyExpiry and quantityInStock/minThreshold from Member A's classes (FR-17, FR-20, UC-18, UC-19).
* Report aggregates WorkOrder cost and downtime (dependency): Report summarises repairCost and downtimeHours without storing them (FR-16, UC-16).



Design choices



* Alert uses an alertType attribute (maintenance due, warranty expiry, low stock) instead of subclasses, so all alerts share one class and one send() method.
* Alert stores recipientId and Report stores generatedBy so each one can be traced back to a user.
* Report does not store costs or downtime. It reads them from WorkOrder, so the numbers have one source.
* Report supports export as PDF or XLSX, as UC-16 requires.
