#### **Integration Notes**



Member A -



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

Member C -



Member D -

