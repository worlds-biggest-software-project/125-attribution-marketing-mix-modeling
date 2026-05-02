# Attribution & Marketing Mix Modeling — Feature & Functionality Survey

> Candidate #125 · Researched: 2026-05-02

## Solutions Analysed

| Tool | Type | Licence / Model | URL |
|------|------|-----------------|-----|
| Rockerbox | Commercial SaaS | Proprietary; custom enterprise pricing | https://www.rockerbox.com/ |
| Google Meridian | Open Source | Apache 2.0; free (self-hosted, GPU recommended) | https://github.com/google/meridian |
| Meta Robyn | Open Source | MIT; free (R/Python package) | https://github.com/facebookexperimental/Robyn |

## Feature Analysis by Solution

### Rockerbox

**Core features**
- Multi-Touch Attribution (MTA) across all channels
- Marketing Mix Modeling (MMM) with AI-driven projections
- Incrementality testing and holdout analysis
- Digital and offline channel support (paid media, organic, social)
- Non-paid media tracking (promotions, key dates, seasonality)
- ROI calculation by channel with budget allocation recommendations
- Real-time CPA and ROAS tracking
- Spend and efficiency monitoring with anomaly detection
- Cross-platform data consolidation

**Differentiating features**
- Unified platform combining MTA, MMM, and testing
- AI-powered budget allocation recommendations
- Handles complex brand scenarios (multi-product, multi-market)
- Offline channel support (TV, radio) alongside digital
- Automatic spend suggestions with confidence intervals
- SOC2 certified data infrastructure
- Integration with major ad platforms (Google, Meta, etc.)

**UX patterns**
- Dashboard showing channel ROI and efficiency trends
- Budget allocation simulator for scenario planning
- Anomaly detection flagging unusual spend patterns
- Reporting with CPA improvement tracking (reported up to 20% improvements)

**Integration points**
- Google Ads, Meta, TikTok, LinkedIn APIs
- CRM integrations for revenue attribution
- Warehouse connectors (Snowflake, BigQuery)
- REST API for custom workflows
- White-label reporting for agencies

**Known gaps**
- Acquired by DoubleVerify (Mar 2025) for $85M; roadmap uncertainty
- Enterprise pricing; not accessible to SMBs
- Long implementation and onboarding cycles
- Limited transparency on modeling methodology
- Requires significant historical data for accurate calibration

**Licence / IP notes**
- Proprietary SaaS; now part of DoubleVerify
- Customer data hosted on Rockerbox/DoubleVerify servers
- No self-hosting option

### Google Meridian

**Core features**
- Bayesian causal inference-based MMM framework
- Geo-level and national-level modeling support
- MCMC sampling (No U Turn Sampler / NUTS algorithm) for posterior inference
- GPU acceleration for real-time optimization (CUDA support)
- Handles multi-channel attribution at scale
- Geo-lift and RCT calibration for causal grounding
- Budget allocation optimization
- Reach and frequency modeling
- Time-series decomposition (trend, seasonality, media effects)

**Differentiating features**
- Google-backed Bayesian approach with causal inference
- Open-source with full transparency on methodology
- GPU support for fast training (can reduce hours to minutes)
- Handles large-scale geo-level data (thousands of markets)
- Replaces Lightweight MMM; more advanced and flexible
- No vendor lock-in; can be deployed on-premise
- Supports prior knowledge integration with data

**UX patterns**
- Python-based implementation with Colab notebooks
- Configuration files for model specification
- Visualization of channel effects and attribution
- Budget scenario analysis and optimization results

**Integration points**
- Python API for model training and prediction
- BigQuery integration for data loading
- Jupyter/Colab for iterative modeling
- JSON/CSV export for results
- Custom Python scripts for automation

**Known gaps**
- Requires significant data science expertise (Python, Bayesian statistics)
- No out-of-the-box marketer UI; requires technical setup
- NUTS sampling can be compute-intensive (GPU recommended)
- Limited support for granular user-level data (geo-level recommended)
- Steeper learning curve than commercial platforms

**Licence / IP notes**
- Apache 2.0 licence; open-source on GitHub
- Full transparency on methodology and algorithms
- Can be deployed on-premise or cloud with no restrictions
- Community contributions welcome

### Meta Robyn

**Core features**
- Ridge regression-based MMM with regularisation to prevent overfitting
- Multi-objective evolutionary algorithm for hyperparameter optimization
- Adstock rate and saturation curve modeling
- Time-series decomposition (trend, seasonality, media effects)
- Gradient-based budget allocation optimization
- Geo-holdout calibration for causal validation
- Clustering for pattern discovery across channels
- Support for many independent variables and granular data
- Digital and direct response advertising focus

**Differentiating features**
- Meta-backed open-source project with active community
- Lower computational requirements compared to Bayesian methods
- Designed specifically for granular digital data (suitable for DTC)
- Regularisation prevents overfitting on complex datasets
- MIT licence allows private and commercial use
- Free training available via Meta Blueprint
- Active development with ongoing improvements

**UX patterns**
- R and Python package interfaces
- Configuration-driven model specification
- Output tables showing channel efficiency and saturation
- Budget allocation recommendations with visualization
- Fit diagnostics and convergence checking

**Integration points**
- R/Python APIs for model training
- CSV/Excel data input
- Integration with data warehouses (via custom scripts)
- Jupyter notebooks for interactive analysis
- Export results to JSON/CSV

**Known gaps**
- Requires R or Python expertise; not marketer-friendly
- No built-in UI; requires custom dashboard development
- Less suitable for geo-level modeling than Meridian
- Limited support for offline channels
- Relies on historical data without explicit causal framework
- No automatic data quality checks or validation

**Licence / IP notes**
- MIT licence; open-source on GitHub
- Allows private, commercial, and derivative use
- Community-driven development with Meta backing
- No restrictions on deployment or modifications

## Cross-Cutting Feature Themes

### Table-Stakes Features
- Multi-touch attribution across digital channels
- Channel ROI and ROAS calculation
- Budget allocation recommendations
- Time-series decomposition (trend, seasonality)
- Geo-lift or RCT calibration for causal grounding
- Support for paid media channels (Google Ads, Meta, etc.)
- Scenario planning and budget simulation
- Historical data analysis (minimum 1-2 years recommended)
- Exportable results and reporting
- Data integration from multiple sources

### Differentiating Features
- Bayesian causal inference approach (Meridian)
- Unified MTA + MMM + testing platform (Rockerbox)
- GPU acceleration for fast training (Meridian)
- Regularisation to prevent overfitting (Robyn)
- Geo-level modeling at scale (Meridian)
- Direct response / DTC optimization (Robyn)
- Offline channel support (Rockerbox)
- Open-source with full methodology transparency (Meridian, Robyn)

### Underserved Areas & Opportunities
- **Automated model calibration**: Current tools require quarterly manual refit cycles; AI agents continuously calibrating against fresh geo-lift and RCT results would be a differentiator
- **Natural-language scenario planning**: Marketers could query budget scenarios in plain English; current tools require dashboard manipulation or code notebooks
- **Anomaly detection and triggers**: LLMs monitoring ad platform APIs to flag budget consumption anomalies and automatically trigger re-attribution runs
- **Synthetic data augmentation**: Generative models filling sparse data gaps (new channels with limited history) to bootstrap confidence sooner
- **Cross-client transfer learning**: AI-native platforms serving many clients could learn media-mix patterns across industries and apply to cold-start accounts
- **Real-time budget allocation**: Most tools operate on batch cycles; real-time continuous budget reallocation based on performance changes is missing
- **Privacy-safe attribution**: Attribution at scale without user-level tracking; aggregate-only approaches with explainability
- **Multi-currency and international modeling**: Few tools handle complex international scenarios with currency fluctuations and regional variations

## Legal & IP Summary

Commercial platforms (Rockerbox) operate on proprietary SaaS with enterprise pricing and data lock-in. Google Meridian (Apache 2.0) and Meta Robyn (MIT) are fully open-source, permitting private, commercial, and derivative use. Both require internal data science capability. Shapley Value Attribution is not patented; Bayesian MMM and RCT calibration are well-established academic methods. No significant IP traps exist beyond vendor lock-in on Rockerbox historical models.

## Recommended Feature Scope

**Must-have (MVP)**
- Multi-touch attribution across digital channels (Google Ads, Meta, TikTok, LinkedIn)
- Basic channel ROI and ROAS calculation
- Time-series decomposition (trend, seasonality, media effects)
- Budget allocation recommendations
- Historical data analysis and reporting
- CSV/JSON export for results
- Documentation and model specification UI
- Data integration from ad platforms

**Should-have (v1.1)**
- Incrementality testing and holdout group analysis
- Geo-lift calibration for causal grounding
- Scenario planning and budget simulation
- Advanced channel efficiency metrics (saturation, adstock)
- Support for offline channel data (TV, radio, print)
- Multi-object optimisation for budget allocation
- Automated data validation and quality checks
- Real-time CPA and ROAS tracking

**Nice-to-have (backlog)**
- Bayesian causal inference approach with confidence intervals
- GPU acceleration for fast model training
- Automated model calibration against fresh RCT results
- Natural-language scenario planning interface
- Anomaly detection with automatic re-attribution triggers
- Synthetic data augmentation for cold-start channels
- Cross-client transfer learning from pattern library
- Real-time continuous budget reallocation
- Multi-currency and international modeling
- Privacy-safe aggregate-only attribution
- Explainable AI scoring and interpretability
- White-label reporting for agencies
