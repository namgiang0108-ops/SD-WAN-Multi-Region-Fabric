# Cisco SD-WAN Multi-Region Fabric (MRF)

## Overview
This repository demonstrates the design and implementation of a Cisco SD-WAN
Multi-Region Fabric (MRF) for a large-scale enterprise network.

The project focuses on architecture, control-plane separation, failure domain
isolation, and traffic steering across regions using Cisco Viptela SD-WAN.

This is a **hands-on lab project**, not a theoretical overview.

---

## Key Design Objectives
- Multi-Region Control Plane using Region 0
- Isolation of failure domains between regions
- Inter-Region routing via OMP
- Dual-Transport support (Internet + MPLS)
- Centralized and localized policy control
- High Availability for Control and Data Plane

---

## Architecture Highlights
- Region 0 acts as the core OMP distribution hub
- Each region has independent control-plane components
- No direct control-plane dependency between non-core regions
- Traffic steering based on SLA and application-aware routing

---

## Topology Overview
The lab includes:
- Central Control Plane (vManage, vBond, vSmart)
- Multiple Regions (Region 1, Region 2, ...)
- Hub, Branch, and Data Center Edge devices
- Simulated WAN transports

Detailed diagrams are available in `topology/diagrams/`.

---

## Lab Environment
- Platform: EVE-NG / PNETLab
- SD-WAN Version: Cisco Viptela 20.9.1
- Transport Types: Internet, MPLS
- Routing: OMP (Overlay Management Protocol)

---

## Repository Structure
```text
.
├── architecture/      # Design rationale and theory
├── topology/          # Network diagrams and IP plan
├── lab/               # Build steps and verification
├── config/            # Device configurations (sanitized)
├── policy/            # Centralized & localized policies
├── test-cases/        # Failure and validation scenarios
├── automation/        # API / Ansible / Python (optional)
└── appendix/          # Terminology, lessons learned
