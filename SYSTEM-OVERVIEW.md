# System Overview

+-------------------+           HTTP            +------------------+
|      Web App      |  <-------------------->   |    Backend API   |
|    (e.g. Next.js) |                           |    (e.g. NestJS) |
+---------+---------+                           +---------+--------+
          |   reads (ABIs)                                |
          |                                               |  RPC (read/write)
          v                                               v
+---------+------------------------------+      +---------+------------------+
|        Contracts (on-chain)           |      |    Node Provider / RPC     |
|  ABIs published by `contracts`        |      | (local devnet / testnet)   |
+---------------------------------------+      +----------------------------+

- **web-app** prefers **read-only** on-chain calls where possible; all **writes** go via **backend-api**.
- **backend-api** enforces domain logic, security, and transaction orchestration.
- **contracts** publishes ABIs and deployed addresses. Clients consume ABIs via releases or artefacts.
- **deploy** composes images and environment config for local/staging/prod.
