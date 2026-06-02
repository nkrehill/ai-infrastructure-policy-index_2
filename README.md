# The AI Infrastructure-Policy Friction Index (Alberta Case Study)

An empirical data tool that models the physical and regulatory boundaries of scaling frontier AI clusters. This project cross-correlates regional electric utility connection queues against qualitative legislative bottlenecks to map infrastructure deployment risk.

## 1. Project Motivation & Core Novelty
Frontier AI relies heavily on massive, resource-intensive physical infrastructure (data centers, multi-gigawatt power grids). While computational capabilities scale exponentially, the physical rollout of cluster infrastructure faces steep regulatory, environmental, and municipal bottlenecks. 

While macroscopic economic reports frequently highlight grid stress, this project introduces an empirical framework that:
* **Disaggregates Macro Data:** Breaks down regional utility connection queues into hyper-local grid stress nodes.
* **Automates Policy Benchmarking:** Uses the **Anthropic Claude API** to parse evolving legislative text (e.g., Alberta's Bill 8 & Bill 12 data center connection limits) and output structured, quantitative risk parameters.
* **Quantifies the Friction Point:** Merges quantitative grid capacities with qualitative policy risk scores to create a predictive deployment index.

## 2. Technical Architecture & Methodology
The data engineering pipeline is split into three main components within a Jupyter Notebook environment:
1. **Quantitative Grid Modeling (`pandas`):** Filters and processes real-world regional grid data to compute a **Grid Stress Ratio** (Requested Megawatts vs. Transmission Node Capacity).
2. **Qualitative Policy Classification (`anthropic` SDK):** Feeds raw legislative bills into `claude-3-5-sonnet` with strict system instructions to algorithmically extract risk categories as clean JSON.
3. **Multivariate Index Synthesis (`seaborn`):** Synthesizes both metrics into a combined Hazard Score to isolate structural roadblocks.

## 3. Key Findings & Visualization
The pipeline automatically exports the consolidated risk index matrix:

![Infrastructure Friction Index](infrastructure_friction_index.png)

* **High-Risk Zones:** The **South Region** exhibits extreme friction (18.2x grid capacity overshoot combined with a Tier-5 regulatory delay score due to cluster assessment backlogs).
* **Strategic Takeaway:** Tech firms attempting deployment cannot look at jurisdictions as a monolith; infrastructure rollout velocity is heavily bounded by local transmission topology and localized self-supply mandates.

## 4. Environment & Dependencies
To run this pipeline locally, install the core dependencies outlined in the `requirements.txt` file:
```bash
pip install -r requirements.txt
