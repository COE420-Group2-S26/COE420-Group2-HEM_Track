# Architectural Style Selection

## Selected Architectural Style
3-Layer Architectural Style (closed layered architecture).

## Main Characteristics
Three layers: Presentation (UI), Application (business logic) and Data (database). The architecture is closed: each layer only uses the layer below, so the UI never reaches the database. The Application layer has four partitions that depend on each other in one direction only, with no cycles. Components communicate only through interfaces.

## Why it is Appropriate for HEM-Track
HEM-Track is a web system (browser, web server, database), which is the standard 3-layer setup. It also follows our Lab 4 DFD: P1 → AccessControl, P2 + P4 → AssetInventory, P3 + P5 → MaintenanceManagement, P6 → Reporting, and D1–D5 → Data layer.

## How it Supports the Design Goals
- **DG-01:** components only share interfaces, so one can change without affecting the others.
- **DG-02:** every application component checks permissions through IAccessControl and logs actions through IAuditLog. Audit records are append-only.
- **DG-03:** only DataStorage writes to the database, and failed alerts are retried using the gateway's DeliveryStatus.

## Advantages
Low coupling, the UI and database can change independently, and parts can be built in parallel.

## Potential Limitations
Each request passes through every layer, which adds overhead. The single database needs backups (NFR-17). The security interfaces add some coupling, and offline use (NFR-11) is not supported.
