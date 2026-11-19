# Architectural Design Goals

| Goal ID | Design Goal | Description | Related Requirement | Priority | Justification |
|---|---|---|---|---|---|
| DG-01 | Maintainability | Changing one part of the system should not require changing the others. | NFR-12, NFR-15 | High | Bugs must be fixed quickly (NFR-15), rules must be easy to change (NFR-12), and team members build parts in parallel. |
| DG-02 | Security | Only authorized users can act, the UI cannot reach the database, and every action is logged. | FR-01, FR-11, NFR-01, NFR-09, NFR-18 | High | The system holds hospital data and decides whether equipment is safe to use. |
| DG-03 | Reliability | No records are lost, alerts reach staff, and one failing part does not stop the rest. | NFR-02, NFR-10, NFR-13 | Medium | Lost maintenance data could lead to missed maintenance and failed inspections. |
