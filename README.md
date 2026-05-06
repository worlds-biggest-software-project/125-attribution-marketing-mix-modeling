# Attribution & Marketing Mix Modeling

> Part of the [worlds-biggest-software-project](https://github.com/worlds-biggest-software-project) initiative.
>
> An AI-native, open-source platform for multi-touch attribution, marketing mix modeling, and incrementality testing in a single triangulated workflow.

This project unifies multi-touch attribution (MTA), marketing mix modeling (MMM), and incrementality testing into one open platform built for the cookieless era. It is aimed at performance marketing teams, DTC brands, and B2B revenue operations groups that have outgrown last-click analytics but cannot justify the five- to six-figure annual cost of enterprise measurement suites.

---

## Why Attribution & Marketing Mix Modeling?

- Rockerbox, the leading unified MTA + MMM + incrementality platform, was acquired by DoubleVerify in March 2025 for $85M, leaving roadmap and pricing uncertainty for existing customers.
- Commercial tools (Rockerbox, Northbeam, Measured) require enterprise contracts and long onboarding cycles, putting modern measurement out of reach for mid-market teams.
- Open-source alternatives (Google Meridian, Meta Robyn) are powerful but demand internal data science expertise in Python, R, or Bayesian statistics — there is no marketer-friendly UI.
- The deprecation of third-party cookies has made privacy-safe aggregate MMM the default approach, but most platforms still treat MMM, MTA, and incrementality as separate products requiring manual reconciliation.
- 53.5% of US marketers cite MMM as their primary cookieless measurement strategy (eMarketer 2024), yet quarterly manual model refit cycles remain the norm across both commercial and open-source tools.

---

## Key Features

### Attribution & Modeling Core

- Multi-touch attribution across digital channels (Google Ads, Meta, TikTok, LinkedIn)
- Marketing mix modeling with time-series decomposition (trend, seasonality, media effects)
- Channel ROI and ROAS calculation with adstock and saturation curve modeling
- Geo-lift and RCT calibration for causal grounding beyond statistical correlation
- Support for Bayesian causal inference and ridge regression approaches

### Budget Optimisation & Scenario Planning

- Budget allocation recommendations with confidence intervals
- Scenario simulation for reallocation across channels and markets
- Real-time CPA and ROAS tracking
- Multi-objective optimisation across paid, organic, and offline channels
- Incrementality testing and holdout group analysis

### Data Integration & Reporting

- Connectors for Google Ads, Meta, TikTok, and LinkedIn APIs
- Warehouse integration (Snowflake, BigQuery)
- CRM integration for revenue attribution
- CSV and JSON export for results
- Automated data validation and quality checks
- Support for offline channel data (TV, radio, print)

### AI-Native Capabilities

- Automated model calibration against fresh geo-lift and RCT results
- Natural-language scenario planning interface
- Anomaly detection on spend signals with automatic re-attribution triggers
- Synthetic data augmentation for cold-start channels with sparse history
- Cross-client transfer learning from a shared media-mix pattern library

---

## AI-Native Advantage

Incumbent platforms operate on quarterly manual refit cycles and require dashboard manipulation or code notebooks for any scenario analysis. An AI-native approach replaces this with continuous model calibration, plain-English budget queries, and LLMs that monitor ad-platform APIs to flag anomalies and trigger re-attribution automatically. Generative models can fill sparse-data gaps for new channels, and a multi-tenant platform can apply transfer learning across industries — a structural advantage unavailable to siloed enterprise tools.

---

## Tech Stack & Deployment

The project draws on the methodologies of Google Meridian (Apache 2.0, Bayesian inference with NUTS sampling, GPU-accelerated) and Meta Robyn (MIT, ridge regression with evolutionary hyperparameter search). Expected deployment modes include self-hosted (on-premise or private cloud) and managed cloud, with a Python core for modeling, warehouse-native data loading from BigQuery and Snowflake, and REST APIs for ad-platform and CRM integration. Open standards considered include Shapley Value attribution, IAB attribution frameworks, and Google's Privacy Sandbox Attribution Reporting API.

---

## Market Context

The global marketing mix optimisation market is valued at approximately USD 5.4 billion in 2025 and projected to reach USD 14.8 billion by 2035, with the broader marketing analytics sector at USD 7.12 billion in 2025. Commercial MMM platforms target enterprise buyers at five- to six-figure annual contracts; SMB-focused MTA tools start around $200–500 per month. Primary buyers are performance marketing directors at mid-market and enterprise DTC brands, CMOs at multi-channel retailers, growth-stage subscription businesses, and B2B revenue operations teams.

---

## Project Status

> This project is in the **research and specification phase**.  
> Contributions, feedback, and domain expertise are welcome.

---

## Contributing

We welcome contributions from developers, domain experts, and potential users.
See [CONTRIBUTING.md](CONTRIBUTING.md) for guidelines.

**Important:** All contributions must be your own original work or clearly attributed
open-source material with a compatible licence. Copyright infringement and licence
violations will not be tolerated and will result in immediate removal of the offending
contribution. If you are unsure whether a piece of code, text, or other material is
safe to contribute, open an issue and ask before submitting.

---

## Licence

Licence to be determined. See [discussion](#) for context.
