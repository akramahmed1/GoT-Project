# US Federal Opportunity Verification Report — 2026-09-18

Target: live-verified, still-open SAM.gov Contract Opportunities in four categories,
verified on 2026-09-18, deadline after 2026-09-18.

## Result counts

| Category | NAICS | File | Verified open records |
|---|---|---|---|
| Warehousing & Storage | 493110, 493120, 531130 | `verified/warehousing-storage.json` | 0 |
| Furniture | 337121, 337122, 337127, 337214 | `verified/furniture.json` | 0 |
| Furnishings & Textiles | 314120, 314999, 337920 | `verified/furnishings-textiles.json` | 0 |
| Security Services | 561612, 561621 | `verified/security-services.json` | 0 |

Zero records met the bar. Per the no-padding rule, all four files are valid empty
JSON arrays (`[]`, validated with `python -m json.tool`).

## Market context (verified live today)

The SAMDaily.us daily index (`http://samdaily.us/today/`, fetched live 2026-09-18)
shows current issue SAM#9063 ("Issue of 19-Sep-26") with these solicitation counts:

- S (Utilities and Housekeeping Services, incl. S206 guard and S215 warehousing): 42 solicitations
- 71 (Furniture): 17 solicitations
- 72 (Household and Commercial Furnishings and Appliances): 3 solicitations
- S sources-sought: 4 notices

So opportunities DO exist today in these PSCs, but they span all NAICS codes under
those PSCs (S and 71/72 cover far more than the assigned NAICS). Individual notice
details for the current issue were not retrievable with the tools available (see
Method notes). Furniture is genuinely sparse: much federal furniture buying runs
through GSA schedules rather than open SAM solicitations.

## Method notes

- `opportunities.csv` (existing research notes) contains only IT, professional-services,
  and construction rows; nothing reusable for these four categories.
- Ran ~14 rounds of `browser_search` (live web search executed 2026-09-18) targeting
  each assigned NAICS code against sam.gov-indexed pages, SAMDaily/fbodaily archives,
  highergov.com, fedops.com, lightrfp.com, rfpmart.com, and governmentcontracts.us.
- **Limitation 1:** a `browser_open` page fetch failed earlier in the session; a
  developer directive then barred further `browser_open` calls for the turn, so no
  live SAM.gov opportunity page could be opened to confirm a current response date.
- **Limitation 2:** SAM.gov API opportunity search returned 404 earlier; the route was
  not retried per instruction.
- **Limitation 3:** search-engine snippets for sam.gov pages carry crawl dates days to
  weeks old; a future-dated deadline in a stale snapshot cannot confirm the notice is
  still open today (amendments, extensions, and awards are invisible in the snapshot).
- Per the task rule ("exclude opportunities whose current deadline cannot be
  confirmed"), no record was admitted without a confirmable deadline after 2026-09-18.

## Unverified leads (excluded from JSON, with reasons)

### Security Services (561612 / 561621)
1. **N3220526R6110** — SBX-1 security services, Military Sealift Command. Presolicitation
   only; solicitation issue ~2026-08-26 and close ~2026-09-26 were ESTIMATES. 8(a)
   set-aside, NAICS 561612. No SAM.gov notice permalink found; actual solicitation not
   confirmed posted. Source: fedops.com mirror of the presolicitation document.
2. **Unarmed guard services, Los Angeles National Cemetery** —
   https://sam.gov/opp/77cc4dc9b34a4f088ae9a8d6e453dcea/view — SDVOSB presolicitation,
   NAICS 561612, published 2026-02-15. No response date listed.
3. **140R3026Q0096** — Hoover Dam K9 services, Bureau of Reclamation. Combined
   synopsis/solicitation, NAICS 561612, total small business set-aside. Award estimated
   Aug 2026, PoP from Oct 2026; almost certainly closed, no current deadline shown.
4. **36C26226Q0469** — Supplemental security guard services, VA San Diego Healthcare
   System. Services ran 2026-09-01 to 2027-08-31; closed.
5. **36C24826Q0958** — RFID Library Security System, VA Caribbean Healthcare System.
   NAICS 561621; response date 2026-09-08; closed.
6. **70LCHE26QPFB00002** — quoted deadline Oct 4, 2026 on SAM.gov, but this is an
   ammunition RFQ (9mm blank rounds, PSC 13), not security services. Excluded.
7. **FPS PSO sole-source extensions** (e.g. 70RFP219FREC00135, Rockville MD; also
   70RFP218DEC000015/16/18) — sole-source extensions, not competitive, no deadline.
8. **DISA Fort Meade physical security guards** and **CMS armed guard services** —
   highergov.com contract FORECASTS (8(a) recompete est. Q4 FY26; CMS forecast est.
   award 3/1/25), not open solicitations.
9. **FA561326Q0040** — Lenel access control, 86th Airlift Wing, NAICS 561621; response
   date was 2026-06-22; closed.

### Warehousing & Storage (493110 / 493120 / 531130)
10. **Navy warehousing requirement** (contact Brittany Simmons,
    brittany.s.simmons3.civ@us.navy.mil) —
    https://sam.gov/opp/af1801cfdcca422785a2495ab80d3b9d/view — NAICS 493110,
    PSC S215, base period began 2026-09-01; closed. Notice ID not captured from snippet.
11. **DLA Distribution Djibouti** —
    https://sam.gov/opp/68e6387ef8d844e7b7195750e4e19f24/view — NAICS 493110,
    PSC S215, distribution support; offers due 2026-01-21; closed.
12. **Fort Polk forklift** —
    https://sam.gov/opp/bd9238027eb9412e8153da8b723a7ecf/view — NAICS 493110 but
    PSC 3930 (warehouse trucks, equipment buy); due 2026-02-17; closed.
13. **W31P4Q-26-R-0050** — Redstone Arsenal RFI/market research only (not a
    solicitation), NAICS 493110, PSC J014.
14. DLA SP3300 leads (SP3300-26-Q-0221 boiler repair; SP3300-26-Q-0175 weigh-scale
    maintenance, NAICS 811210) — maintenance/repair, closed, wrong NAICS.

### Furniture (337121 / 337122 / 337127 / 337214)
15. **W912DY-26-Q-A078** — Fort Riley casegoods, NAICS 337214, due 2026-04-06; closed.
16. **Wright-Patterson private-office furniture**, NAICS 337214, due 2026-04-08; closed.
17. **GSA partition RFQ**, NAICS 337214, due 2026-02-05; closed.
18. **FA301626R0037** — instructor chairs, NAICS 337214; no open deadline confirmed.
19. **Creech AFB furniture** — questions due 2026-08-04; closed/unknown.
20. **Basewide Furniture Maintenance 2026, Wright-Patterson AFB** (rfpmart 1165320) —
    sources-sought (market research, not a solicitation), deadline 2026-09-28; prior
    contract FA860122D0006 was NAICS 561210, so likely not a furniture-manufacturing
    NAICS. Excluded from the Furniture category.
21. **FA448425Q0010** — Dorm Furniture Refresh, JB McGuire-Dix-Lakehurst; stale
    (261 days); closed.
22. **N6817126QS009** — Housing Furniture; NAICS 423620 (merchant wholesalers), not an
    assigned NAICS. Excluded.

### Furnishings & Textiles (314120 / 314999 / 337920)
23. **SPE4A7-26-R-0438** — parachute slider/panel, NAICS 314999, due 2026-03-30; closed.
24. **Enhanced Parachutist Drop Bag** sources-sought, NAICS 314999, due 2026-03-04; closed.
25. **BIE linen products**, NAICS 314999; older 2026 deadline; closed.

## Coverage gaps

- Individual notices in today's SAMDaily issue (#9063) were not yet indexed by the
  search engine, so their titles, NAICS codes, and deadlines could not be mined.
- SAM.gov opportunity pages require a live page fetch to confirm current response
  dates and amendment history; this was unavailable this session.
- GSA eBuy / GSA schedule buys (a major channel for furniture) are out of scope
  (SAM.gov only per task).
- No data on 493120, 531130, 337121, 337122, 337127, 314120, or 337920 open
  solicitations was found at all.

## Recommended next step (needs live-browser delegation)

To complete verification, have a browser-capable agent:
1. Open `http://samdaily.us/today/` and enumerate the individual notices under
   PSC S, 71, and 72 (solicitations + sources sought), capturing each notice's
   SAM.gov permalink, notice ID, NAICS, agency, set-aside, and response due date.
2. Filter to the assigned NAICS codes and confirm each notice is still open on
   sam.gov with a deadline after 2026-09-18.
3. Re-check the candidate URLs listed above (items 1-3, 10-11) in case any have been
   amended or re-issued with a live deadline.

---
*Generated 2026-09-18. Method: live web search only; no SAM.gov page could be opened
this session, so no record is asserted as live-verified.*
