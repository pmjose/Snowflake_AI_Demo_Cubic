# IT Ops, Vendors, and BI Adoption (Cubic³)

Use these reference points for Snowflake Intelligence questions. All amounts in EUR.

## IT Operational Expenses (finance_transactions)
- Use `FINANCE_SEMANTIC_VIEW` and map categories from `ACCOUNT_TYPE` + `DEPARTMENT` + `PRODUCT_CATEGORY`.
  - **Connectivity Ops:** roaming partner costs, IMS/SIM provisioning, QoS monitoring, edge routing.
  - **Platform & Software:** SaaS, CRM, analytics/Explore³, security/compliance tooling, licenses.
  - **Personnel:** connectivity engineering, partner ops, SRE, data/AI, support.
  - **Maintenance:** platform support, incident response, managed services, SOC/NOC tooling.
- Metrics: total spend, average transaction, vendor, department, month/quarter.
- Example prompt: “Break down IT opex by connectivity ops, platform/software, personnel, maintenance for last quarter (EUR).”

**Illustrative Q4 IT opex (EUR):**
- Connectivity Ops: €18.4M
- Platform & Software: €7.6M
- Personnel: €14.2M
- Maintenance: €5.1M

**Illustrative Q4 total IT opex:** €45.3M

## Top Vendors and Supplier Risk (vendor_dim + finance_transactions)
- Largest tech spend: sum `AMOUNT` by `VENDOR_KEY`; join to `vendor_dim` (MNO partners, cloud, security).
- Supplier exposure: % of connectivity spend by vendor + count of critical services tied to each; flag single-source categories (cloud, security, roaming).
- Example prompts:
  - “Top 10 vendors by IT spend last quarter; show EUR, category, and % of total.”
  - “Which vendors are single-source for roaming or security, and what % of connectivity spend do they represent?”

**Illustrative top vendors (Q4, EUR):**
- Vodafone: €6.2M (Roaming, 34% of connectivity spend)
- Orange: €4.8M (Roaming, 26% of connectivity spend)
- AT&T: €3.1M (Roaming, 17% of connectivity spend)
- Deutsche Telekom: €2.4M (Roaming, 13% of connectivity spend)
- Security Monitoring Add-on: €1.5M (Security, 8% of platform spend)

## OEM Programs (public logos in demo data)
- OEM programs referenced in `customer_dim` / `sf_accounts`: Bentley, Volkswagen, Cariad, Audi, Iveco, Lamborghini, Porsche, SEAT, Skoda, GM, CNH, Honda.
- Use these OEM names when slicing `sales_fact`, `sf_opportunities`, and `customer_dim` for demos.

**Supplier risk notes (illustrative):**
- Roaming: top 2 partners cover ~60% of roaming spend (high exposure).
- Security tooling: concentrated in a single vendor (medium exposure).

## Tech Investment vs Revenue (sales_fact + finance_transactions + product_dim)
- Correlate platform/connectivity spend vs revenue by product category:
  - Spend: `finance_transactions` grouped by product category (Connectivity Core, StreamLocal³, DriverConnect³, FleetWallet³, Explore³).
  - Revenue: `sales_fact` joined to `product_dim` and `region_dim`.
  - Use the same time window (e.g., last two quarters) and segment splits.
- Example prompts:
  - “Compare connectivity/software spend vs revenue by product category for the last two quarters; show correlation and EUR.”
  - “Revenue per € of connectivity spend by OEM program segment (Premium EV, Mass Market, Fleet).”

**Illustrative tech spend vs revenue (Q4, EUR):**
- Connectivity Core: €11.2M spend vs €74.0M revenue (6.6x)
- StreamLocal³: €9.5M spend vs €58.0M revenue (6.1x)
- DriverConnect³: €4.1M spend vs €19.5M revenue (4.8x)
- Explore³ Analytics: €3.2M spend vs €16.0M revenue (5.0x)

**OEM demo prompt examples (aligned to dataset):**
- “Show revenue and units by OEM program (Bentley, VW, Audi, Porsche, Honda) for the last two quarters.”
- “Compare attach success and support sentiment for GM vs Honda programs.”
- “Which OEMs have the highest marketing-sourced pipeline this quarter?”

## Analytics / BI Adoption (usage proxy)
- Use available proxies (counts over time):
  - Marketing: campaigns executed (`marketing_campaign_fact`), impressions, leads.
  - Sales: opportunities created/closed (`sf_opportunities`), revenue from marketing-sourced deals.
  - Finance/HR: transaction counts and approvals; active HR records.
  - Support: call transcripts and CSAT surveys as usage proxies.
  - KPIs: use `cubic_kpi.csv` for headline metrics.
- Example prompts:
  - “Show trend of campaigns, leads, and marketing-sourced closed-won revenue by month.”
  - “Show opportunities created vs closed by month and by region; highlight marketing-sourced.”
  - “Count finance transactions and average approval time (approval_date - date) by month; show top departments.”
  - “Show CSAT survey counts and average score by month; correlate with attach success in network_performance.”

**Illustrative BI adoption snapshot (Q4):**
- Marketing campaigns run: 36 (avg 1.2/week)
- Leads generated: 6,100; closed-won marketing revenue: €8.6M
- Finance transactions processed: 3,250; average approval time: 4.1 days
- HR records updated: 2,980 (monthly)
- Support artifacts: 10k+ transcripts, 25 CSAT surveys in demo

## How to Query via Agent
- Use:
  - `Query Finance Datamart` for spend by category/vendor.
  - `Query Sales Datamart` for revenue by OEM/product/region.
  - `Search Internal Documents: Strategy` for platform roadmap context.
  - `Search Internal Documents: Network` for attach/latency context.
- Mention time windows (last quarter/6 months) and segments (OEM programs, regions) to keep answers tight.
