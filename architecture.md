# Architecture

## Overview

The project uses independent n8n workflows connected through a shared Google Sheets job tracker.

```mermaid
flowchart TD
    A[Schedule Trigger] --> B[REST Job API]
    B --> C[Transform and Filter]
    C --> D[Validate Required Fields]
    D --> E[Deduplicate by Job URL]
    E --> F[Google Sheets]
    F --> G[Shortlist Condition]
    G --> H[LLM Job-Fit Evaluation]
    H --> I[Structured Output]
    I --> J[CV/Application Draft]
    J --> K[Human Review]
    K --> L[Outreach Workflow]
    L --> M[Gmail]
    M --> N[Update Tracker]
```

## Design Principles

1. **Modular workflows:** Each business responsibility is separated.
2. **Human review:** Application content and external communication should be reviewed.
3. **Idempotency:** Duplicate checking prevents repeated job records.
4. **Auditability:** The tracker records status and processing progress.
5. **Security:** Secrets remain in n8n credentials or private environment variables.
6. **Extensibility:** Additional job sources and scoring logic can be added later.
