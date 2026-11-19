# Component Descriptions

| ID | Component | Layer | Responsibilities | Supported Use Cases |
|---|---|---|---|---|
| CO1 | HEMTrackUI | Presentation | Web screens for all users, input and barcode/QR scanning. | All (user interaction) |
| CO2 | AssetInventory | Application | Equipment registration, QR codes, search, status and location, documents and spare parts. | UC-03, UC-05, UC-07, UC-08, UC-14, UC-15, UC-19, UC-20, UC-21 |
| CO3 | MaintenanceManagement | Application | Schedules, work orders, technician/vendor assignment, checklists, downtime and cost, and alerts. | UC-02, UC-04, UC-09, UC-10, UC-12, UC-13, UC-17, UC-18 |
| CO4 | AccessControl | Application | User accounts, roles, login with 2FA, permission checks and the audit log. | UC-06, UC-11 |
| CO5 | Reporting | Application | Cost, downtime, compliance and audit reports. | UC-01, UC-16 |
| CO6 | DataStorage | Data | The only component that reads and writes the database. | All stored data |

## Interfaces

| Component | Provided Interface(s) | Required Interface(s) |
|---|---|---|
| CO1 HEMTrackUI | None | IAssetInventory, IMaintenance, IAccessControl, IReporting |
| CO2 AssetInventory | IAssetInventory | IAccessControl, IAuditLog, IDataAccess |
| CO3 MaintenanceManagement | IMaintenance | IAssetInventory, IAccessControl, IAuditLog, IDataAccess, INotificationGateway |
| CO4 AccessControl | IAccessControl, IAuditLog | IDataAccess |
| CO5 Reporting | IReporting | IAccessControl, IAuditLog, IDataAccess |
| CO6 DataStorage | IDataAccess | None |
| Notification Gateway (external) | INotificationGateway | None |
