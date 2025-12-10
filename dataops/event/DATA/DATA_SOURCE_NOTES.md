# Data Source Notes (Cubic³ Demo)

## Publicly sourced (from press/website)
- `demo_data/cubic_kpi.csv`: public metrics only for:
  - Connected vehicles live: 17,000,000
  - Monthly vehicle adds: 450,000
  - Countries covered: 190
  - MNO partners: 550
  - SoftBank investment: €473,000,000 for 51% (Dec 2023)

## Synthetic demo data (plausible, not real)
All other CSVs are synthetic placeholders created for the Cubic³-themed demo. This includes, but is not limited to:
- `demo_data/` tables: product/category dims, customers, vendors, sales reps, sales_fact, finance_transactions, marketing_campaign_fact, campaign_dim, channel_dim, region_dim/coverage, activation_lead_time, arpu_segment, sf_accounts, sf_contacts, sf_opportunities, hr_employee_fact, employee_dim, etc.
- `quickstart/assets/data/` tables: network_performance, infrastructure_capacity, customer_details, customer_feedback_summary, customer_interaction_history, csat_surveys, call_transcripts_sample, etc.
- Unstructured markdown/PDF placeholders under `unstructured_docs/`.

## Guidance
- Treat all synthetic tables as demo-only. Do not use for real reporting or decisions.
- If you have real Cubic³ data, replace the corresponding CSVs and rerun the pipeline.
- Keep `cubic_kpi.csv` as the only table with public figures; remaining rows in that file are marked "Synthetic demo placeholder".

- Placeholder PDFs added (Cubic³-branded) in quickstart/assets/data/pdfs_to_upload and dataops/event/DATA/unstructured_docs/strategy. Replace with official Cubic³ PDFs for production.
