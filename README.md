# Telecom Circuit Cost Dashboard

> Python-powered finance dashboard tracking telecom infrastructure costs across 7 Deloitte member firms, 11 vendors, and thousands of circuit endpoints — refreshing in 2–3 minutes vs hours of manual work.

![Python](https://img.shields.io/badge/Python-3776AB?style=flat-square&logo=python&logoColor=white)
![SQL](https://img.shields.io/badge/SQL-4479A1?style=flat-square&logo=mysql&logoColor=white)
![SAP HANA](https://img.shields.io/badge/SAP%20HANA-0FAAFF?style=flat-square&logo=sap&logoColor=white)
![QlikSense](https://img.shields.io/badge/QlikSense-009848?style=flat-square&logoColor=white)
![Status](https://img.shields.io/badge/Status-Live%20at%20Deloitte-success?style=flat-square)

---

## What This Does

The Telecom Circuit Cost Dashboard is a Python-generated finance dashboard for Deloitte's Technology Finance team — tracking all telecom infrastructure costs across member firms, premises, floors, and rooms.

It gives Technology Finance full visibility into which circuits are active, which are lapsing, which need renewal approvals, and where costs are running high — from analyst level all the way to executive leadership.

---

## What It Tracks

- **WiFi circuits** — per premises, floor, and room
- **Router costs** — per device and location
- **Polycom / phone devices** — per location
- **Vendor rate cards** — current rates from 11 vendors (4 India, 7 US)
- **Circuit lifecycle status** — Active · Lapsing · Pending enablement · Renewal due
- **Invoice matching** — flags circuits with missing or unmatched invoices
- **Budget allocation tracking** — shows finance cost allocated by Technology team per vendor

---

## Coverage

| Dimension | Detail |
|---|---|
| Member firms | 7 Deloitte member firms |
| Vendors (India) | 4 vendors |
| Vendors (US) | 7 vendors |
| Granularity | Premises → Floor → Room → Device |
| Users | Analyst to Executive level |
| Data sources | SAP HANA, QlikSense, SQL, Vendor management |

---

## Dashboard Views

```
Executive Summary
    └── Total circuit cost by member firm
    └── Cost trend month-on-month
    └── Vendor spend breakdown

Circuit Status View
    └── Active circuits
    └── Lapsing circuits (with lapse date)
    └── Pending enablement
    └── Renewal approvals due

Premises Drill-down
    └── Member firm → Office → Floor → Room
    └── Device count and type
    └── Cost per location

Vendor Rate Card
    └── Current rate by vendor and circuit type
    └── Rate change history
    └── Contract renewal dates

Invoice Reconciliation
    └── Circuits with no invoice received
    └── Invoice vs rate card variance
    └── Approval status
```

---

## Technical Build

### Data Pipeline
```
SAP HANA (invoice postings)
        +
QlikSense (consolidated reporting)
        +
SQL (vendor management data)
        +
Vendor rate card files
        |
        v
Python (Pandas) — Extract, clean, merge
        |
        v
Python (Plotly / Matplotlib) — Generate dashboard
        |
        v
Output: Interactive HTML dashboard
        (refreshes in 2–3 minutes on Python run)
```

### Python Libraries Used
```python
pandas        # Data extraction and transformation
sqlalchemy    # SAP HANA and SQL connections
plotly        # Interactive dashboard charts
openpyxl      # Rate card Excel processing
```

---

## Impact Metrics

| Metric | Before | After |
|---|---|---|
| Dashboard refresh time | Hours of manual work | 2–3 minutes |
| Circuit visibility | Fragmented across teams | Single view for all |
| Lapse risk detection | Reactive (after lapse) | Proactive (pre-lapse flag) |
| Invoice reconciliation | Manual matching | Automated flag |
| User accessibility | Finance team only | Analyst to Executive |

---

> Note: All data in this repo uses anonymised sample data. Deloitte vendor names, circuit details, and cost figures are confidential.

---

*Part of the [Sughosh Anney Finance × AI Portfolio](https://github.com/sughosh-anney)*
