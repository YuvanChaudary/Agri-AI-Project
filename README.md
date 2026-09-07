# Agri-AI — Intelligent Agricultural Decision Platform

![Agri-AI](frontend/src/assets/hero.png)

Agri-AI is a modular, production-ready platform that brings modern ML, explainability, and delivery mechanisms to agriculture. It provides advisory intelligence across market forecasting, soil analysis, crop recommendations, risk assessment, subsidy eligibility and profitability planning — with an approachable frontend, robust backend services, and reproducible training pipelines.

If you'd like to visit the source repository or discuss collaboration, please email: yuvanchaudary2004@gmail.com

---

## Highlights

- Multi-model architecture: market forecasting, yield & soil analysis, risk & subsidy engines, crop intelligence and profitability calculators.
- Explainability built-in (SHAP-based explainers and local/sample explanations).
- Reproducible training pipelines and model registries.
- Monitoring and drift detection for model health and data quality.
- Delivery adapters: PDF reports, voice IVR, WhatsApp bot and offline caches for low-connectivity environments.
- Full-stack demo with a Vite + React frontend and FastAPI-style services.

---

## Project Composition (at a glance)

- models/           — Trained models and model-serving components (market_price, risk_engine, soil_analysis, subsidy_eligibility, yield_forecast, crop_intelligence, profitability_engine)
- models/shared/    — Shared libraries: agents, inference, delivery, orchestration, registry
- api/              — Lightweight API adapters and microservices
- frontend/         — Vite + React frontend (dashboard, charts, forms, explanation panels)
- training/         — Training pipelines and scripts for each model
- monitoring/       — Drift detectors and monitoring reports
- explainability/   — SHAP explainers and explainability utilities
- data_pipeline/    — Dataset preparation, certification and online feature push
- docs/             — Dataset schema, generation rules, and API key notes
- artifacts/        — Example artifacts, audit reports and freeze validation manifests

---

## Architecture Overview

Agri-AI uses a modular microservice-style architecture where each domain (market, soil, risk, subsidy, yield) exposes a small inference service. A lightweight orchestrator routes requests and aggregates results for delivery. Explainability modules attach SHAP summaries and local explanations to improve transparency. Monitoring pipelines compute drift statistics and surface alerts for model degradation.

For a full blueprint see: Architecture_Blueprint.md

---

## Quickstart (Development)

Requirements:
- Python 3.10+
- Node 18+
- Poetry or pip + virtualenv
- Docker (optional, for local composition)

1) Clone the repository

   git clone https://github.com/YuvanChaudary/Agri-AI.git

2) Backend: create a venv and install

   python -m venv .venv
   source .venv/bin/activate
   pip install -r requirements.txt

3) Run a single model service (example: market price)

   python models/market_price/api/main.py

4) Run the frontend

   cd frontend
   npm install
   npm run dev

5) Run the end-to-end demo (if available)

   python run_e2e_demo.py

For Docker-compose based local deployment:

   docker-compose up --build

---

## Example API Endpoints

- Market price prediction: POST /market_price/predict
- Soil analysis inference: POST /soil_analysis/infer
- Risk assessment: POST /risk_engine/predict
- Subsidy eligibility: POST /subsidy_eligibility/predict

Refer to api/ and models/*/api/ folders for concrete request/response schemas and examples.

---

## Reproducible Training & Model Registry

Training pipelines and registration lives under training/ and models/*/registry. Artifacts, evaluation metrics and feature contracts are stored alongside models to help reproduce experiments. Use the provided training scripts to reproduce a model version and the registry writers to snapshot metadata.

---

## Explainability & Monitoring

- SHAP explainers included in explainability/ and in model-specific explainability modules produce both global and local explanations.
- monitoring/ contains drift detectors (PSI/feature drift) and monitoring dashboards.

---

## Contributing

Agri-AI is structured for extensibility. To contribute:

1. Fork the repository
2. Create a feature branch
3. Run tests: pytest (or the appropriate test runner)
4. Open a PR with a clear description and tests

See CONTRIBUTING.md for more details (if created).

---

## License

This project is licensed under the MIT License — see LICENSE for details.

---

## Contact

If you'd like access to this repository, want to collaborate or demo the project, please email: yuvanchaudary2004@gmail.com

