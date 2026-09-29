**Zeerak**

NFR-01
Auditability: All critical actions should be logged in a tamper-evident audit trail for regulatory inspection

NFR-02
Notification Reliability: Alerts and reminders should be delivered with at least 99% reliability to avoid missed maintenance

NFR-03
Localization: The system should support multiple languages/date formats if deployed across regions.

NFR-04
Usability: The interface should be intuitive enough for non-technical hospital staff to use with minimal training

NFR-05
Compatibility: The system should be accessible via desktop and mobile/tablet browsers, and support barcode scanner hardware.



**Adithya**

NFR-06

Availability: The system should be available at any time, given its role in supporting critical hospital operations.

NFR-07

Performance: The system should load dashboards and search results within reasonable time under normal load.

NFR-08

Scalability: The system should support growth in the number of records (exponential).

NFR-09

Security: The system should encrypt data in transit and at rest, and enforce role-based access control.

NFR-10

Data Integrity: The system should prevent loss or corruption of maintenance/calibration records through validation and backups.



**Aaditya**

NFR-11

Offline Mobile Capability: Technicians should be able to login their progress even offline and it can be synced later when back online.

NFR-12

Configurability: Admins should be able to customize things like maintenance schedule rules, alert timing and equipment record fields directly from settings, without needing a developer to change the code each time.

NFR-13

Fault Tolerance: If part of the system goes down, it shouldn't crash everything and the data entered should not be deleted.

NFR-14

Data Migration: System should support importing old equipment maintenance records in bulk when first setting things up.

NFR-15

Support and Maintenance: There should be a set time frame for how fast reported bugs/issues get responded to and fixed, since this is hospital equipment.



**Azim**

NFR-16

Concurrent Users: The system should support at least 100 concurrent users without performance degradation.

NFR-17

Disaster Recovery: The system should have a documented disaster recovery plan with offsite backup storage.

NFR-18

Data Privacy: The system should restrict access to sensitive equipment/patient-adjacent data per hospital privacy policy.

NFR-19

Auditability of Configuration Changes: Any changes to maintenance schedules, thresholds, or user roles should be logged and reversible.

NFR-20

Data Retention and Archival: The system should retain audit logs, maintenance and calibration history, and decommissioned-asset records for a defined minimum period, archive older records without slowing daily use, and keep them retrievable for inspection.




