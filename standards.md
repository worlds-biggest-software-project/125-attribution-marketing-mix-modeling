# Standards & API Reference

> Project: Attribution & Marketing Mix Modeling · Generated: 2026-05-06

## Industry Standards & Specifications

### IAB Standards

**IAB Modernizing MMM Best Practices for Marketers (December 2025)**
- URL: https://www.iab.com/guidelines/modernizing-mmm-best-practices-for-marketers/
- PDF: https://www.iab.com/wp-content/uploads/2025/12/IAB_Modernizing_MMM_Best_Practices_for_Marketers_December_2025.pdf
- The definitive industry best-practice guide for MMM, covering data preparation standards, model refresh cadences (weekly quick refreshes, monthly/quarterly full retrains), integration with attribution and experimentation systems, and auditability requirements. Developed in partnership with MMM vendors and practitioners.

**IAB Guidelines for Incremental Measurement in Commerce Media**
- URL: https://www.iab.com/guidelines/guidelines-for-incremental-measurement-in-commerce-media/
- Covers causal incrementality standards relevant to geo-holdout testing and experiment design used to calibrate MMM models.

**IAB/MRC Retail Media Measurement Guidelines (January 2024)**
- URL: https://www.iab.com/wp-content/uploads/2024/01/IAB_Retail_Media_Measurement_Guidelines_January2024.pdf
- Joint IAB and Media Rating Council (MRC) guidelines covering viewability, attribution, fraud prevention, and data privacy for retail media measurement.

**IAB/MRC Attention Measurement Guidelines (November 2025)**
- URL: https://www.iab.com/wp-content/uploads/2025/11/IAB_MRC_Attention_Measurement_Guidelines_November_2025.pdf
- Standards for attention-based measurement, relevant for weighting impression quality in MMM channel inputs.

**IAB Australia Market Mix Modelling Landscape Report (2025)**
- URL: https://www.iabaustralia.com.au/resource/market-mix-modelling-landscape-report-2025/
- Survey of twelve active MMM vendors across methodologies ranging from classical econometric models to modern Bayesian and machine learning approaches.

### Media Rating Council (MRC) Standards

**MRC Minimum Standards for Media Rating Research**
- URL: https://www.mediaratingcouncil.org/standards-and-guidelines
- Base assessment criteria for all accredited media measurement products. Establishes ethical and operational standards for ratings production, including requirements for viewable impressions before attribution of outcomes to ad exposures.

**MRC Accreditation Programme**
- URL: https://mediaratingcouncil.org/
- Formal accreditation for media measurement products across digital, OOH, print, radio, TV, and cross-media. Nielsen Big Data + Panel national TV measurement received first-ever hybrid panel/big-data accreditation in January 2025.

### W3C / WICG Standards

**Attribution Reporting API (WICG Incubation)**
- GitHub spec: https://github.com/WICG/attribution-reporting-api
- MDN reference: https://developer.mozilla.org/en-US/docs/Web/API/Attribution_Reporting_API
- Overview: https://privacysandbox.google.com/private-advertising/attribution-reporting
- A privacy-preserving browser-level attribution standard being developed under the W3C Web Incubator Community Group (WICG). Replaces third-party cookie-based conversion tracking. Supports both event-level reports (coarse conversion data with differential privacy noise) and aggregatable reports (campaign-level aggregate measurement). Directly relevant to any MTA component of an attribution platform.

### Data Model & API Specifications

**OpenAPI Specification v3.1.0 / v3.2.0**
- URL: https://spec.openapis.org/oas/v3.1.0.html
- URL: https://spec.openapis.org/oas/v3.2.0.html
- The standard for describing REST APIs. v3.1.0 aligns data types with JSON Schema Draft 2020-12. v3.2.0 adds formal support for streaming media types (application/jsonl, text/event-stream) and expanded OAuth 2.0 device authorization flows — both relevant for data pipeline and real-time attribution APIs.

**JSON Schema (Draft 2020-12)**
- URL: https://json-schema.org/
- Foundation for defining attribution event payloads, model input/output schemas, and data pipeline contracts between measurement platforms and data warehouses.

**OAuth 2.0 (RFC 6749)**
- URL: https://datatracker.ietf.org/doc/html/rfc6749
- Standard authorization framework used by all major marketing APIs (Google Ads, Meta Marketing API, Triple Whale) for authenticating third-party integrations.

### Security & Privacy Compliance

**GDPR (EU General Data Protection Regulation)**
- URL: https://gdpr-info.eu/
- Constrains user-level tracking; one of the primary drivers pushing the market from MTA toward aggregate MMM approaches. Any platform ingesting EU user data must comply with data minimisation and consent requirements.

**CCPA (California Consumer Privacy Act)**
- URL: https://oag.ca.gov/privacy/ccpa
- US equivalent of GDPR for California; similarly restricts cross-site user tracking. Accelerates server-side and aggregate measurement adoption.

**OWASP API Security Top 10**
- URL: https://owasp.org/www-project-api-security/
- Relevant for securing data ingestion APIs that receive conversion event payloads from advertiser servers.

---

## Similar Products — Developer Documentation & APIs

### Google Meridian

- **Description:** Open-source Bayesian MMM framework released by Google in January 2025, enabling in-house model building with geo-level data support and MCMC sampling via JAX/TensorFlow.
- **API Documentation:** https://developers.google.com/meridian/reference/api/meridian
- **Python Package (PyPI):** https://pypi.org/project/google-meridian/ — requires Python 3.11–3.13; current version 1.6.0 (2026)
- **GitHub Repository:** https://github.com/google/meridian
- **Developer Guide / Tutorials:** https://developers.google.com/meridian — includes Colab notebooks, methodology docs, and visualisation walkthroughs
- **Google Cloud Cortex Integration:** https://docs.cloud.google.com/cortex/docs/v6/meridian
- **Standards:** Python library with JSON-serialisable model configs; no REST API — programmatic integration only
- **Authentication:** N/A (local library); optional Google Cloud credentials for Cortex integration

### PyMC-Marketing

- **Description:** Open-source Bayesian marketing toolbox from PyMC Labs, providing MMM, customer lifetime value (CLV), and customer choice analysis models. Most widely used MMM library by PyPI downloads as of 2026.
- **API Documentation:** https://www.pymc-marketing.io/en/stable/
- **Python Package (PyPI):** https://pypi.org/project/pymc-marketing/
- **GitHub Repository:** https://github.com/pymc-labs/pymc-marketing
- **Example Notebooks:** https://www.pymc-marketing.io/en/stable/notebooks/mmm/mmm_example.html
- **Tool Comparison Guide:** https://www.pymc-marketing.io/en/stable/guide/mmm/comparison.html
- **Standards:** Python library; Bayesian inference via PyMC/Aesara/PyTensor backends; no REST API
- **Authentication:** N/A (local library)

### Google Ads API

- **Description:** Full programmatic access to Google Ads campaign data, conversion tracking, attribution models, and reporting — core data source for MMM channel spend inputs.
- **API Documentation (REST):** https://developers.google.com/google-ads/api/rest/overview
- **Developer Videos:** https://developers.google.com/google-ads/api/videos/catalog/working-with-rest-1
- **Standards:** gRPC (primary) or REST; resource-oriented design; responses in JSON/Protocol Buffers
- **Authentication:** OAuth 2.0 with developer tokens
- **Key Features:** Data-Driven Attribution (DDA) now the default model; supports conversion window configuration and geo-level reporting useful for MMM calibration

### Meta Marketing API (Conversions API / CAPI)

- **Description:** Server-side event ingestion API enabling advertisers to send conversion data directly from their servers to Meta, bypassing browser-based pixel limitations. Critical for first-party data measurement strategies.
- **Main API Documentation:** https://developers.facebook.com/docs/marketing-api/conversions-api/
- **Get Started Guide:** https://developers.facebook.com/docs/marketing-api/conversions-api/get-started/
- **Server Event Parameters Reference:** https://developers.facebook.com/documentation/ads-commerce/conversions-api/parameters/server-event
- **Meta Ads API Setup Guide:** https://admanage.ai/blog/meta-ads-api
- **Standards:** REST/JSON; event deduplication via `event_name` + `event_id` pair; customer data fields must be SHA-256 hashed
- **Authentication:** Pixel ID + access token (passed as API parameter); OAuth 2.0 for third-party integrations
- **Key 2025 Changes:** Unified attribution settings enforced server-side; Incremental Attribution model introduced; `action_attribution_windows` parameter controls conversion window scope

### Triple Whale

- **Description:** AI-powered ecommerce attribution and analytics platform used by 45,000+ brands. Provides MTA, media mix modeling, CTV attribution, and natural language query interface.
- **API Documentation:** https://triplewhale.readme.io/reference/introduction-to-the-triple-whale-api
- **API Landing Page:** https://www.triplewhale.com/api
- **GitHub (Public APIs + Examples):** https://github.com/Triple-Whale/triple-whale-public-apis
- **SDKs:** JavaScript/Node.js SummaryApi client library (available in the GitHub repo)
- **Standards:** REST/JSON; OpenAPI-documented endpoints
- **Authentication:** OAuth 2.0 (for third-party integrations) or personal API key (generated from UI)
- **Key Endpoints:** Summary (metrics dashboard), Metrics (push custom data / extract), Attribution (full customer journey export)

### Northbeam

- **Description:** ML-based multi-touch attribution platform targeting high-spend DTC and enterprise brands, combining journey-level MTA with media mix modeling.
- **API Documentation:** https://docs.northbeam.io/docs/using-the-api
- **Data Export API:** https://docs.northbeam.io/docs/northbeam-api-data-export-1
- **Touchpoints Export:** https://docs.northbeam.io/docs/touchpoints-export
- **Attribution Models Reference:** https://docs.northbeam.io/docs/attribution-models
- **Base URL:** https://api.northbeam.io/v1
- **Standards:** REST/JSON; requires `Authorization` header and `Data-Client-ID` header per request
- **Authentication:** API key (provided in account settings)
- **Key Endpoints:** `/v1/exports/attribution-models`, `/v1/exports/metrics`, `/v1/exports/breakdowns`, `/v1/exports/data-export/result/{export_id}`

### Rockerbox

- **Description:** Unified MTA + MMM + incrementality platform with strong coverage of hard-to-measure channels (direct mail, podcasts, linear TV, OTT). Acquired by DoubleVerify in March 2025.
- **Help Documentation:** https://help.rockerbox.com/
- **API Integrations Hub:** https://help.rockerbox.com/category/wcd840uzni-api-integrations
- **Direct API Docs:** https://backend-prod-k8s.rockerbox.tech/docs
- **API Tracker Entry:** https://apitracker.io/a/rockerbox
- **Standards:** REST/JSON; push-based data warehouse integrations (Snowflake, BigQuery, Redshift)
- **Authentication:** API key
- **Notable:** Platform prioritises data portability — push to internal warehouses and custom dashboards is a first-class feature

### Google Privacy Sandbox Attribution Reporting API

- **Description:** Browser-level, privacy-preserving attribution API replacing third-party cookie tracking. Supports event-level and aggregatable reports with differential privacy noise.
- **Overview:** https://privacysandbox.google.com/private-advertising/attribution-reporting
- **Getting Started:** https://privacysandbox.google.com/private-advertising/attribution-reporting/getting-started
- **Android Developer Guide:** https://developers.google.com/privacy-sandbox/private-advertising/attribution-reporting/android/developer-guide
- **W3C/WICG Spec:** https://github.com/WICG/attribution-reporting-api
- **Demo:** https://arapi-home.web.app/
- **Standards:** W3C WICG incubation; differential privacy framework for noise injection; no server-side SDK required — browser/OS handles report generation
- **Authentication:** N/A (browser API); ad-tech vendors must register HTTP endpoints to receive reports

---

## Notes

**No universal ISO standard for MMM or marketing attribution data exists.** The field is governed by a combination of IAB/MRC industry guidelines, platform-specific API specifications, and open-source library conventions. The IAB December 2025 MMM Best Practices document is the closest current approximation to a formalised cross-industry standard.

**Data ingestion standardisation is a major gap.** Each platform (Google Ads, Meta, TikTok, programmatic DSPs) exposes spend and impression data in incompatible schemas. Tools like Fivetran and Airbyte provide connector-level normalisation but there is no shared data model standard for MMM input files. The IAB best practices guide recommends a "simple, auditable ingestion template" but does not prescribe a specific schema.

**The W3C Attribution Reporting API remains in WICG incubation** as of 2026. Its adoption is not yet mandatory and browser support is limited. Any platform building on it should treat the spec as evolving.

**Bayesian inference libraries (PyMC-Marketing, Meridian) use Python-native interfaces** rather than REST APIs. Integration with production systems typically requires wrapping these libraries in a service layer (FastAPI, Cloud Run, etc.) and designing a custom API contract — an area where a standardised OpenAPI schema for MMM model inputs/outputs would provide value.
