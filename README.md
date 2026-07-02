# BHCPF Accountability Platform

**An open civic data platform tracking ₦57.1 billion in Basic Health Care Provision Fund (BHCPF) disbursements and 8,309 validated Primary Health Centres across Nigeria's 36 States and FCT.**

Built by **Lawal Lawal Ali** (Data Wrangler, PPDC) in partnership with the **Public and Private Development Centre (PPDC)**.

---

## 🔍 What This Platform Does

The BHCPF is Nigeria's flagship public health financing mechanism, disbursing funds through four national gateways — NPHCDA, NCDC, EMTC, and NHIA — to support Primary Health Centres at the ward and LGA level.

This platform makes three quarters of 2025 disbursement data (Q1, Q2, and Q3) — previously buried in government spreadsheets, PDFs, and newspaper notices — interactive, searchable, and verifiable by any Nigerian citizen.

---

## 📁 Project Structure

```
bhcpf-accountability-platform/
│
├── index.html                      # Landing page — links to dashboard and map
├── bhcpf_dashboard.html            # Interactive disbursement dashboard
└── bhcpf_accountability_map.html   # Live facility accountability map
```

---

## 📊 Dashboard Features (`bhcpf_dashboard.html`)

- **KPI Strip** — ₦57.1B combined total, Q3-specific ₦27.5B figure, facility count, functionality rate
- **Disbursements Tab** — Quarter toggle (Q1 / Q2 / Q3 / Q1+Q2 / All), searchable state table with allocation breakdown across all four Q3 gateways
- **Facilities Tab** — All 8,309 validated PHC facilities, filterable by state, LGA, and functionality status (Functional L2 / Functional L1 / Partial / Non-functional)
- **State Detail Tab** — Drill down to individual LGA and facility level for any of the 37 states

### Q3 2025 Gateway Structure
Q3 introduced a four-gateway disbursement model, a change from the Q1/Q2 dual-gateway structure:
| Gateway | Description |
|---------|-------------|
| NPHCDA | Disbursed to State PHC Boards and LGA-level facilities |
| NCDC | National surveillance and emergency disease response |
| EMTC | Emergency Medical Treatment — only fully onboarded states |
| NHIA | Social Health Insurance Agencies (equal + population-based) |

---

## 🗺️ Accountability Map Features (`bhcpf_accountability_map.html`)

- **8,309 colour-coded pins** — Green (Functional L2), Teal (Functional L1), Amber (Partial), Red (Non-functional)
- **GPS "Find Near Me"** button — instantly shows the nearest PHC facilities to your current location
- **One-tap Google Maps navigation** — no app required, works on any phone
- **State, LGA, and functionality filters** — narrow the map to exactly what you're looking for
- **Location precision labels** — each pin is explicitly flagged as LGA-precise, city-level, or state-level estimate, so users know how accurate the pin is

---

## 🔢 Data Sources & Methodology

| Source | Description |
|--------|-------------|
| NPHCDA | Q1 & Q2 2025 disbursement spreadsheets (Excel) |
| Daily Trust (Feb 11, 2026, p.19) | Q3 2025 disbursement table (four-gateway structure) |
| NPHCDA | `BHCPF_PHCs_8309_Validated.pdf` — 231-page facility list with State, LGA, Ward, Facility, and Functionality |
| dr5hn/countries-states-cities-database | Geographic coordinates for geocoding at state and city level |

### Data Pipeline
- Extracted and reconciled Q1, Q2, and Q3 figures — each verified row by row until every gateway summed to the published consolidated total
- Extracted all 8,309 facility records from a 231-page scanned government PDF
- Matched facility ward/LGA names to a geographic coordinate reference database
- Deterministic jitter applied to avoid pin stacking where multiple facilities share the same LGA centroid
- Q3 Rivers State NCDC figure corrected (misread in initial extraction: ₦18.8M → ₦7.2M, resolving a ₦11.6M total discrepancy)

---

## 💻 Running Locally

No build step, no server, no dependencies to install. Every file is a standalone HTML file with all data and assets embedded.

```bash
git clone https://github.com/YOUR_USERNAME/bhcpf-accountability-platform.git
cd bhcpf-accountability-platform
open index.html          # macOS
xdg-open index.html      # Linux
start index.html         # Windows
```

Or simply double-click `index.html` in your file explorer.

---

## 🌐 Deployment (Netlify)

1. Fork or clone this repository
2. Go to [netlify.com/drop](https://app.netlify.com/drop)
3. Drag the entire project folder onto the page
4. Netlify generates a live URL instantly (e.g., `ppdc-bhcpf.netlify.app`)
5. Rename under **Site settings → Change site name**

For a custom domain: add a CNAME record pointing to your Netlify site from your domain registrar.

---

## 🏢 About PPDC

The **Public and Private Development Centre (PPDC)** is a Nigerian civil society organisation focused on public procurement monitoring, civic accountability, and transparency in governance.

- 🌐 [www.ppdc.org](https://www.ppdc.org)
- 📧 info@ppdc.org
- 𝕏 [@PPDC_NG](https://twitter.com/PPDC_NG)
- 📸 [@PPDC_NG](https://instagram.com/PPDC_NG)

---

## 👤 Author

**Lawal Lawal Ali**
Data Wrangler · Public and Private Development Centre (PPDC)
AI & Data Scientist with hands-on experience applying machine learning and data engineering to civic accountability challenges.

---

## 📄 License

This project is open source under the [MIT License](LICENSE).
Data sourced from publicly available Nigerian government publications and is reproduced here for public interest accountability purposes.
