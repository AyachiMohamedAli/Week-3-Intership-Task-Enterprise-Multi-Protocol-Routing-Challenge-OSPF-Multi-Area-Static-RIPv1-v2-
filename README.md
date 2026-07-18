# Week 3 — Enterprise Multi-Protocol Routing Challenge

Network Administration Internship — IT-Simplera Institute
OSPF Multi-Area · Static Routing (floating static) · RIP v1/v2 · Route Redistribution

## Topology

7 routers across three routing domains — see `topology-diagram.png`.

- **R1** — OSPF backbone (Area 0)
- **R2 / R3** — ABRs into Area 1 / Area 2
- **R4** — ASBR, redistributes OSPF ↔ RIP
- **R5 / R6** — RIPv2 and RIPv1 sites
- **R7** — Remote office, static route (primary via R1, floating backup via R3)

## Contents

| File | Description |
|---|---|
| `Week3_Report_Pro.docx` | Full report — design, configs, verification, troubleshooting |
| `topology-diagram.png` | Topology diagram |
| `configs/R1.txt` – `R7.txt` | Router configs |
| `screenshots/` | Verification evidence |

## Addressing

Base block `172.16.0.0/16`, VLSM-subnetted. Full table in the report, Section 2.1.

## What's verified

- OSPF full adjacency across all areas
- RIPv1/v2 coexistence + redistribution into OSPF
- Static + floating static, live failover tested
- End-to-end connectivity across every domain boundary

Two real issues found and fixed during testing (documented in report Section 4): a duplicate OSPF router-id, and a RIPv1/VLSM masking limitation.

## Author

Ayachi Med Ali — Network Administration Intern, IT-Simplera Institute
