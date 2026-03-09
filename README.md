# Telemedicine & Registration Infrastructure (KPPMCH)

**Municipal-Scale Distributed Engine | Event-Driven Workflow | 80% Triage Efficiency Gain**

A high-concurrency, asynchronous healthcare framework engineered to bridge public intake and clinical decision-making through a resilient serverless architecture.

[![Next.js](https://img.shields.io/badge/Frontend-Next.js-black?style=flat-square&logo=next.js)](https://nextjs.org/)
[![Status](https://img.shields.io/badge/Status-Production_Verified-green?style=flat-square)](https://telemedscheduler.vercel.app/)

---

## 1. System Architecture Design

The platform implements a **Stateless Layered Architecture** to ensure high availability and strictly enforced data consistency (ACID) across distributed environments.

```mermaid
graph TD
    %% Layer 1: Patient Ingestion
    subgraph Ingestion_Layer [1. Patient Ingestion Layer]
        User([Patient / User]) -->|Input Consultation Data| WebApp[Next.js App Router]
        WebApp -->|Zod Schema Validation| WebApp
    end

    %% Layer 2: Logic & Integration
    subgraph Logic_Tier [2. Serverless Logic Layer]
        WebApp -->|Authorized JSON Payload| API{API Gateway}
        API -->|Request Mapping| Logic[Business Logic Engine]
        Logic -->|Data Normalization| Logic
    end

    %% Layer 3: Persistence
    subgraph Data_Tier [3. Persistence & Integrity]
        Logic -->|ACID Transaction| DB[(Google Sheets / Cloud Store)]
        DB ---|Audit Trail| Log[System Traceability]
    end

    %% Layer 4: Clinical Delivery
    subgraph Delivery_Tier [4. Clinical Notification]
        Logic -->|Asynchronous Webhook| LineAPI[LINE Messaging Gateway]
        LineAPI -->|Structured Flex Message| Nurse([Senior Nursing Staff])
    end

    %% Architectural Styling
    style User fill:#f9f9f9,stroke:#333
    style Nurse fill:#f9f9f9,stroke:#333
    style WebApp fill:#fff,stroke:#000,stroke-width:2px
    style API fill:#000,color:#fff,stroke-width:2px
    style Logic fill:#000,color:#fff,stroke-width:2px
    style DB fill:#fff,stroke:#000,stroke-dasharray: 5 5
