# Class Distribution

| ID | Component Name | Responsibilities | Included Classes |
|---|---|---|---|
| CO1 | HEMTrackUI (Presentation layer) | Web screens for all users, input and barcode/QR scanning. | None |
| CO2 | AssetInventory (Application layer) | Equipment registration, QR codes, search, status and location, documents and spare parts. | Equipment, LocationHistory, Document, SparePart |
| CO3 | MaintenanceManagement (Application layer) | Schedules, work orders, technician/vendor assignment, checklists, downtime and cost, and alerts. | WorkOrder, MaintenanceSchedule, Checklist, Vendor, Technician, Alert |
| CO4 | AccessControl (Application layer) | User accounts, roles, login with 2FA, permission checks and the audit log. | User, Role, AuditLog |
| CO5 | Reporting (Application layer) | Cost, downtime, compliance and audit reports. | Report |
| CO6 | DataStorage (Data layer) | The only component that reads and writes the database. | None |
