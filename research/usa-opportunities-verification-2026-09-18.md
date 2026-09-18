# USA Opportunities Verification Log — 2026-09-18

**Research date:** Friday, 2026-09-18. Every record in the JSON files was checked against a live source on this date. Items that could not be verified were excluded from the JSON and are documented below as UNVERIFIED.

**Headline counts:** 15 verified open federal solicitations (SAM.gov) · 10 open subcontracts (SBA SubNet) · 40 recently awarded contracts (usaspending.gov API) · 12 upcoming forecast programs (DHS APFS) · 2 open K-12 school-district IT-hardware bids. **79 records total.**

**Files:** one JSON per category in this directory, plus `subcontracts.json`, `awards.json`, `upcoming.json`. Record schema: `id, title, agency, naics, category, status, deadline_or_award_date, url, verified_on, source` (optional extras: `notice_type`, `set_aside`, `place_of_performance`, `recipient`, `amount_usd`, `notes`).

---

## 1. What was verified, by file

| File | Records | Status | Method |
|---|---|---|---|
| it-services.json | 4 | open | Live SAM.gov page loads (2) + fresh search-verified (2) |
| professional-services.json | 1 | open | Fresh search-verified (SAM solicitation PDF) |
| building-construction.json | 7 | open | Live SAM.gov page re-confirms today |
| janitorial-facilities.json | 1 | open | Fresh GovTribe + USACE NWD listings |
| laboratories.json | 1 | open | Full solicitation text in fresh search results |
| medical-supplies.json | 0 | — | Nothing met the bar |
| food-bakery.json | 1 | open | SAM.gov-indexed page + GovWin cross-confirm |
| office-supplies.json | 0 | — | Nothing found under target NAICS |
| warehousing-storage.json | 0 | — | Blocked from per-notice confirmation |
| furniture.json | 0 | — | Blocked from per-notice confirmation |
| furnishings-textiles.json | 0 | — | Blocked from per-notice confirmation |
| security-services.json | 0 | — | Blocked from per-notice confirmation |
| subcontracts.json | 10 | open | Full live listing fetched from subnet.sba.gov |
| awards.json | 40 | closed | Direct usaspending.gov API rows (pull_awards.py, re-runnable) |
| upcoming.json | 12 | upcoming | DHS APFS public print pages |
| k12-it-hardware.json | 2 | open | Full bid/RFP text in fresh search results (district + state-portal sources) |

## 2. Per-record caveats (read before publishing)

- **it-services.json / FDA-SOL-75F40126Q00384:** deadline 2026-09-24 confirmed via a mirror crawled ~2h before verification; the direct SAM.gov URL was not recoverable. The record carries a notes caveat. Open the SAM page directly before quoting.
- **professional-services.json / 12318726Q0077:** verified via the SAM solicitation PDF (mirror link in `url`, noted in record). Deadline 2026-09-25 confirmed.
- **janitorial-facilities.json / W912DQ27QA001:** "Kansas FY27 Mass Solicitation - Custodial Services", ~10 packages, quotes due 2026-10-02, verified via GovTribe + official USACE NWD contracting page (URL in record, noted). No standalone SAM.gov opp URL was publicly indexed yet.
- **laboratories.json / W9127N26QA092:** quotes due 2026-09-25 confirmed from full solicitation text; `url` is the solicitation attachment mirror, not a sam.gov/opp page.
- **food-bakery.json / 15BFTD26Q00000001:** FCI Fort Dix FY26 2nd Qtr Subsistence, offers due 2026-11-20. SAM shows published Nov 13, 2025 with a one-year open window; the exact official page title was not re-confirmed on a fresh page load today. Open the SAM URL directly before quoting the title.
- **building-construction.json / 36C24826R0133 (VA, Repair Water Tanks, SDVOSB, due 2026-09-24):** this is a two-phase design-build RFP restricted to existing VISN 8 Caribbean Construction MATOC IDIQ holders. Not a generally accessible opportunity. Flag before presenting as an actionable lead.
- **building-construction.json / 75H70126R00026:** Amendment A02 extended the deadline to 2026-10-08; some listings still show 2026-09-24. The file uses 2026-10-08.
- **it-services.json / HS0021-26-CSO-DCSA:** long-running CSO/OTA umbrella (due 2031-06-22). Proposals are accepted only against separately published "Innovation Calls", not the umbrella itself. The related Innovation Call #01 had a solution-concept deadline of 2026-09-18 (today) and was therefore excluded.
- **awards.json:** the usaspending `spending_by_award` endpoint returns `NAICS Code` as null on every row, so each record's `naics` is the *filter code used in the query*, not a per-record API value. `deadline_or_award_date` is the API's period-of-performance Start Date; several FY26 awards show 2026/2027 start dates (verbatim from the API). The 40 awards are the latest-by-start-date per category in the 2026-06-01 to 2026-09-18 window, not a comprehensive sample.
- **upcoming.json:** all 12 items are DHS APFS forecasts with estimated solicitation quarters. One record (Kodiak Door Hanger 3) was updated during verification: solicitation release target is now 2027-08-01, award targeted Q1 FY2028. Forecasts are plans, not open bids.
- **k12-it-hardware.json / CPSB-ERATE-YR30-330-WAP:** deadline 2026-09-30 (digital proposals, noon CST) and 2026-10-02 (sealed hard copy, noon CST) confirmed from full RFP text. E-Rate eligibility rules apply: vendors need a valid USAC SLD SPIN and FCC Registration Number. Network infrastructure hardware (wireless access points), not end-user devices. Verify scope in the RFP PDF before pursuing.
- **k12-it-hardware.json / RFP-CLA-260000002552-1:** bids due 2026-09-22 12:00 PM EST confirmed from the full advertisement text (Michigan SIGMA via LightRFP). Classroom technology equipment and installation for the New Clarkston Junior High 2022 Bond project. The advertisement does not confirm end-user laptops, Chromebooks, desktops, printers, or copiers; verify scope in the full bid documents.

## 3. What failed / was blocked

- **SAM.gov page fetches:** `browser.open` on SAM.gov notice URLs worked for the first few fetches, then failed terminally mid-sweep for several workers. A same-turn retry was not permitted, so remaining verification fell back to fresh search-result hits containing full notice text. A dedicated re-check pass recovered 4 records (CFBLNet, FDA Think Trends, USDA Market Rent Study, Kansas custodial).
- **SAM.gov API:** the public opportunities search endpoint returned 404 when tried; not retried per instructions.
- **SBA SubNet:** fully reachable — the complete live listing and all 10 detail entries rendered in one fetch. No block.
- **usaspending.gov API:** worked as documented (one transient IncompleteRead, retried successfully).
- **Forecast portals:** GSA gov-wide Forecast (acquisitiongateway.gov), VA forecast portal, and DOT forecast are JS-walled and yielded no verifiable entries. DHS APFS public print pages were readable and supplied all 12 upcoming records.

## 4. UNVERIFIED — checked but excluded from JSON

- **832675541** (claimed DISA WRMS sustainment, due 2026-09-23): zero search hits for the notice ID; could not confirm existence or deadline.
- **DCSAInnovationCall01**: confirmed real, but solution-concept deadline is 2026-09-18 (today) — not after the cutoff.
- **36C78626Q50098** (LA National Cemetery guard services, 561612): real solicitation, but no post-2026-09-18 response date confirmable; amendment history is jumbled.
- **N3220526R6110** (SBX-1 armed security, MSC): solicitation confirmed, current deadline not confirmable.
- **Navy warehousing candidates** (incl. sam.gov/opp/af1801cfdcca422785a2495ab80d3b9d): no confirmable open deadline; other hits were June 2026 or earlier.
- **NAFBA1-26-R-0027** (Army Fort Wainwright food service): amendment extended closing to Sep 18, 2026 4:00 PM CDT — time-sensitive today, no confirmable SAM URL/NAICS. Lead only.
- **W912WJ26QA066, W912DQ26QA042** (janitorial): due dates not recoverable — excluded.
- **Medical/lab near-misses:** W913E526QA005, 36C25926Q0434, HT941026Q2052, W50S80-26-Q-0022, 36C25626Q1085 — deadlines expired or unconfirmable.
- **TSA Gold+ (F2026073907)** and **CISA CEEOSS** forecasts: details visible in snippets but live URLs failed verification — excluded per rules.
- **VA CMOP printer supplies (36C77026Q0075)** and Navy office RFQs: wrong NAICS (325992/339940) or closed.
- **K-12 IT-hardware near-misses (checked but excluded — scope or deadline):** Bolivar R-I School District MO (600-800 Chromebooks, closed 2026-07-10) · Lake County School District R-1 (75 Chromebooks, closed 2026-07-15) · Tahoma SD WA (5th-grade Chromebooks, delivery due 2026-08-01) · Port Angeles SD WA (500 Chromebooks, September 2026 deployment, no post-2026-09-18 deadline confirmed) · Edina Public Schools MN (200 Windows laptops, closed 2026-01-05) · Edmond Public Schools OK (500-700 desktops + Chromebooks, closed 2026-03-24) · McDuffie County Schools GA (desktops, closed 2026-06-01) · Liberty County School System GA (copier lease, closed 2026-02-06) · Jefferson SD WI (printers/managed print, closed 2026-02-13) · Moniteau SD PA (copiers/printers, closed 2026-04-27) · Sulphur Springs Union SD CA (copier services, closed 2026-04-17) · Barrow County School System GA (2,000-3,000 Dell Chromebooks, Q1 2026 contract through 2026-06-30) · North Penn SD PA (spring 2026 Chromebook bid, closed) · Council Rock SD PA Bid 26-07 (library/classroom tech, quantities in bid packet but no confirmable post-2026-09-18 deadline) · Howard County PSSA MD RFP 047.26.B6 (student Chromebooks page live, no bid deadline supplied) · Oro Grande SD CA RFP 25-26-04 (Chromebook backpacks, contract through 2026-06-30) · CiTi BOCES NY B27-0004/B26-6002A (due 2026-09-30, musical instruments and welding materials — not IT hardware).
- **Southwest ISD board item (San Antonio, TX, Aug 2026):** up to $2.7M approved for Windows computers, Chrome computers, printers, and other technology — but procurement runs through DIR state contracts, purchasing cooperatives, and RFQs to approved vendors, not a public open RFP. Not a bid opportunity; document kept as evidence of the channel pattern.

## 5. Structural facts (why some categories are thin — not a search miss)

- **Food/bakery:** most DLA Troop Support subsistence buying runs through DIBBS; only procurements over $25,000 are publicized on SAM.gov. BOP quarterly subsistence (e.g., Fort Dix) is the main live open pipeline.
- **Office supplies:** federal buying flows through GSA SmartPay/FSS schedules; essentially no open solicitations under 424120/453210.
- **Medical supplies (339112/339113/621999):** VA and DLA buying flows through MSPV, FSS, ECAT, and VA NAC indefinite-delivery contracts as catalog/delivery orders, not open SAM.gov solicitations. Standalone notices are thin and turn over fast.
- **Furniture (337xxx):** most federal furniture buying runs through GSA Federal Supply Schedule.
- **IT/professional services (5415xx/5416xx):** large share flows through GWACs and MACs (SEWP, OASIS+, SeaPort-NxG, GSA schedules) rather than standalone open solicitations.
- **Construction (236220):** significant volume is MATOC/IDIQ task orders (e.g., the VA Caribbean MATOC record above). Open standalone solicitations exist but many require IDIQ-holder status.
- **Janitorial (561720):** open federal custodial work appears mostly as small USACE district RFQs with short windows (e.g., the Kansas City District FY27 mass solicitation: 10 packages, due 2026-10-02).
- **SBA SubNet:** the live listing currently holds exactly 10 open subcontract notices — 10 is the complete set today, not a sample.
- **K-12 school IT hardware:** the open-device-bid pipeline is thin right now for structural, not search-quality, reasons. (1) Seasonality: the 2026 student/staff device refresh cycle ran February through July; by mid-September those bids are closed. (2) Channels: most districts buy devices through state contracts (e.g., DIR in Texas), purchasing cooperatives (e.g., Sourcewell, BuyBoard), board-approved vendor lists, and RFQs sent only to approved suppliers — not public open RFPs. The Southwest ISD (TX) August 2026 board item ($2.7M for computers/printers via DIR + coops + RFQs) is the documented example. (3) E-Rate infrastructure RFPs (like CPSB 330-WAP) are the most consistently public open school-tech solicitations, but they cover network gear, not end-user devices. Expect the next open Chromebook/laptop wave in the January–April 2027 refresh cycle.

## 6. Recommended follow-ups

1. Re-run the SAM.gov-dependent categories (warehousing, furniture, furnishings/textiles, security, medical, office) via a live-browser pass now that page fetches may have recovered; the near-miss URLs in section 4 are the starting list.
2. Re-fetch SBA SubNet periodically — new subcontract notices post continuously.
3. Re-check DHS APFS and the GSA gov-wide forecast closer to FY27 Q1 for fresh upcoming programs.
4. Re-run the K-12 device-bid sweep in January–April 2027 (next refresh cycle) via Michigan SIGMA, NC eVP, Texas ESC portals, Florida district portals, and DemandStar. Before publishing any record, open its `url` directly to confirm the title and deadline text, especially the four caveat-flagged records in section 2.
