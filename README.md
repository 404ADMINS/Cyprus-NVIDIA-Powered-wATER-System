<div align="center">

# Cyprus Water Intelligence (CWI)
**An Enterprise-Grade, NVIDIA-Powered Multi-Agent Water Scarcity System**

[![NVIDIA NIM](https://img.shields.io/badge/NVIDIA-NIM-76B900?style=flat-square&logo=nvidia&logoColor=white)](https://build.nvidia.com)
[![H2O.ai](https://img.shields.io/badge/H2O.ai-Driverless_AI-FFE600?style=flat-square&logo=h2o&logoColor=black)](https://h2o.ai)
[![Python 3.12+](https://img.shields.io/badge/Python-3.12%2B-3572A5?style=flat-square&logo=python&logoColor=white)](https://python.org)
[![PostgreSQL](https://img.shields.io/badge/PostgreSQL-16-4169E1?style=flat-square&logo=postgresql&logoColor=white)](https://postgresql.org)
[![Grafana](https://img.shields.io/badge/Grafana-Telemetry-F46800?style=flat-square&logo=grafana&logoColor=white)](https://grafana.com)

**Reverse engineering enterprise architectures to build sovereign AI systems from the ground up.**  
*No SaaS lock-in. Just raw engineering, multi-agent AI, and real-world telemetry.*

</div>

---

> [!NOTE]
> **Project Status:** This system is currently under active evaluation by the Cyprus Government (Water Development Department) following its submission in July 2026.

## The Philosophy: I Build It, I Don't Rent It

Cyprus is facing a real water crisis. Reservoirs dropped to 13.7% capacity in early 2026. Up to 40% of distributed water is lost to leakage before it reaches anyone. A 14 million cubic meter annual deficit is projected with no signs of improving on its own.

Rather than wait for an enterprise vendor to offer a packaged solution, I chose to understand the problem from first principles and build the tooling myself, adapting and extending the open-source H2O.ai and NVIDIA Flood Intelligence Blueprint into a water scarcity intelligence system tailored specifically to Cyprus.

The goal is not to impress. The goal is to make something that works.

---

## System Overview

The **Cyprus Water Intelligence (CWI)** system is a production-grade, multi-tier software platform designed to convert raw public water resource metrics into operational decision intelligence. 

It aggregates real-time reservoir levels, historical inflow climatology, weather metrics, **Copernicus Sentinel-2 satellite imagery**, and simulated night-flow distribution network telemetry to detect leaks, predict shortages, and optimize desalination against renewable energy availability.

### The Tech Stack (The "Crazy Stuff")

- **AI & Multi-Agent Orchestration:** 
  - **NVIDIA NIM (Nemotron 49B)** for high-performance LLM inference without local GPU constraints.
  - **FastMCP & NeMo Agent Toolkit** for seamless multi-agent coordination.
- **Machine Learning & Predictive Analytics:**
  - **H2O Driverless AI** for anomaly detection on water network sensor telemetry (detecting 40% non-revenue water loss).
- **Telemetry & Visualization:** 
  - **Prometheus & Grafana** for real-time sensor ingestion, simulated night-flow leakage detection, and operational dashboards.
- **Backend & Data Pipeline:** 
  - Custom **Python/FastAPI** backend powering the agent runtimes.
  - **PostgreSQL 16** for deterministic state and historical climatology storage.
- **Frontend UI:** 
  - **Vue + Vite** for a lightning-fast, highly responsive web dashboard used by operators. *(A live demo link to the frontend dashboard can be provided upon request).*

### Key Features & Economic Impact

- **Agricultural & Soil Moisture Intelligence:** By integrating satellite data (Copernicus Sentinel-2), I monitor soil moisture and vegetation stress. This allows the system to intelligently optimize the routing of **~4M cubic meters of treated wastewater** to agricultural irrigation instead of dumping it into the sea.
- **Tourism Demand & Price Elasticity:** Cyprus tourism creates massive, geographically uneven demand. Tourist areas can consume up to 500L per person per day (vs. the 120L EU average). I built price elasticity modeling and demand forecasting specifically targeting hotels, resorts, and private swimming pools to simulate the financial and resource impact of consumption policies.

---

## The Multi-Agent Architecture

The core of the system is a decentralized fleet of AI agents, communicating via structured data contracts. 

```text
┌─────────────────────────────────────────────────────────────────────────────┐
│                       Cyprus Water Intelligence (CWI)                       │
│                                                                             │
│   ┌────────────────┐      ┌─────────────────┐       ┌─────────────────┐     │
│   │ Data Collector │ ───▶ │  Risk Analyzer  │ ────▶ │ AI Predictor    │     │
│   │ (Satellite,    │      │ (Drought &      │       │ (7-Day Forecast,│     │
│   │  Sensors, WDD) │      │  Leakage Scorer)│       │  Desal Sched.)  │     │
│   └──────┬─────────┘      └───────┬─────────┘       └─────────┬───────┘     │
│          │                        │                           │             │
│          ▼                        ▼                           ▼             │
│   ┌───────────────────────────────────────────────────────────────────┐     │
│   │                    FastMCP / NeMo Agent Toolkit                   │     │
│   └───────────────────────────────────────────────────────────────────┘     │
│          ▲                        ▲                           ▲             │
│          │                        │                           │             │
│   ┌──────┴─────────┐      ┌───────┴─────────┐       ┌─────────┴───────┐     │
│   │ PostgreSQL 16  │      │ ML Agent (H2O)  │       │ Emergency       │     │
│   │ (Time-Series)  │ ◀──▶ │ (Anomaly Det.)  │ ────▶ │ Responder       │     │
│   └────────────────┘      └─────────────────┘       │ (WDD Actions)   │     │
│                                                     └─────────────────┘     │
└─────────────────────────────────────────────────────────────────────────────┘
```

### The 5 Core Agents
1. **Data Collector:** Ingests live telemetry: reservoir levels, rainfall, desal output, Open-Meteo forecasts, and EU Copernicus satellite imagery.
2. **Risk Analyzer:** Calculates localized scarcity risk scores, identifies leakage hotspots, and flags supply-demand imbalances.
3. **ML Agent (H2O):** Runs continuous anomaly detection over network sensor data to spot microscopic deviations indicating burst pipes.
4. **AI Predictor:** Generates 7-day reservoir level forecasts, simulates district demand, and schedules energy-intensive desalination operations against peak solar/wind availability.
5. **Emergency Responder:** Emits actionable WDD (Water Development Department) recommendations: pressure management, restriction enforcement, and wastewater routing optimization.

---

## The Secret Sauce

This repository provides a high-level **architectural overview** of my capabilities. 

To protect my intellectual property and client data, the **proprietary risk algorithms, customized agent prompts, specific threshold logic, and direct Cyprus WDD integration code** remain closed-source. 

I don't share the exact math that runs the country, but I share this: **If you have a complex, data-heavy, critical infrastructure problem, I have the engineering firepower to solve it.**

