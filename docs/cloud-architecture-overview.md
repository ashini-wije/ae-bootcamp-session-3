# Cloud Architecture Overview

This monorepo contains a React frontend that calls an Express API. The API manages task operations and stores data in an in-memory SQLite database.

```mermaid
flowchart LR
    User[User]
    Frontend[React Frontend\npackages/frontend]
    API[Express API\npackages/backend]
    Store[In-Memory SQLite Store]

    User --> Frontend
    Frontend -->|HTTP /api/tasks| API
    API --> Store
```

## Create TODO Sequence

```mermaid
sequenceDiagram
    actor User
    participant Frontend as React Frontend
    participant API as Express API
    participant Store as In-Memory SQLite Store

    User->>Frontend: Enter task details and submit form
    Frontend->>API: POST /api/tasks
    API->>Store: Insert task record
    Store-->>API: Return created task
    API-->>Frontend: 201 Created + task payload
    Frontend-->>User: Show updated task list
```
