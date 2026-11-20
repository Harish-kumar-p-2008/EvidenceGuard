# EvidenceGuard

**CRIMEATHON'26 | Digital Forensic Investigation Prototype | Case CR-26-047**

EvidenceGuard is a Python and Streamlit prototype for reviewing digital evidence and highlighting potential API and financial security risks. It is designed to help investigators organise evidence, inspect suspicious events, correlate records, and prepare an investigation summary.

> **Important:** Alerts are investigation leads, not proof of fraud or unauthorised human activity. Findings must be verified against original evidence and organisational records.

## Project objectives

- Upload and process investigation evidence in CSV/JSON formats.
- Review API activity, credentials, source IPs and sensitive operations.
- Flag vendor bank-detail changes that lack approval references.
- Assign understandable Low, Medium and High risk levels.
- Correlate related records using timestamps, IP addresses, credentials and request IDs.
- Present findings through a dashboard and support report preparation.

## Main components

| Component | Responsibility |
|---|---|
| Evidence ingestion | Read, validate and standardise evidence records |
| Threat detection | Identify suspicious API and financial activity |
| Evidence correlation | Connect related records and build an event timeline |
| Dashboard and reports | Present evidence, alerts, risk levels and investigation results |

## Case study

The prototype was developed around CRIMEATHON'26 case **CR-26-047**, concerning Harbor & Finch Freight and its TallyBridge Integration system.

One reviewed event involved a vendor bank-detail modification for Coastal Packaging Ltd. on 3 September 2026. The API record and vendor change log shared the request ID `req-5f61b0de8`. The change lacked an approval reference and therefore requires verification. An HTTP 200 response indicates that the API request was processed; it does not establish that the change was authorised.

The investigation also reviewed API credential activity, missing approval references and unusual export-job volume. The available evidence does not by itself prove fraud, data theft, or that a payment was completed.

## Run locally

From the project directory, create and activate a virtual environment, then install the dependencies:

```powershell
python -m venv .venv
.\.venv\Scripts\Activate.ps1
pip install -r requirements.txt
streamlit run app.py
```

Open the local URL printed by Streamlit (normally `http://localhost:8501`).

## Project structure

```text
EvidenceGuard/
├── app.py
├── requirements.txt
├── modules/
├── data/
├── outputs/
└── tests/
```

The exact files available in a checkout may vary as team members integrate their modules.

## Team contributions

- **Evidence ingestion:** upload, validation and data preparation.
- **Threat detection:** API and financial risk identification.
- **Evidence correlation:** network/event matching and investigation timeline.
- **Dashboard and reporting:** application integration, visualisation and report preparation.

## Limitations

EvidenceGuard is a hackathon investigation prototype. Risk labels are triage indicators and depend on the quality and completeness of supplied evidence. A shared API key or IP address does not identify a specific human actor. Further log review, approval verification and payment-record checks are required before drawing final conclusions.

## Repository

https://github.com/Harish-kumar-p-2008/EvidenceGuard
