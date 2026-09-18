# TenderTrack

TenderTrack is a procurement opportunity tracker covering Guyana and the United States. It started on September 13, 2026 as a Guyana-only snapshot of government and private-sector open tenders, and on September 18, 2026 it was rebuilt and rebranded as TenderTrack with a second country tab for the USA. The original Guyana dashboard was retired the same day; TenderTrack is the only live dashboard.

This repository holds the data files behind the dashboard. The dashboard itself is published separately. Everything here is a dated snapshot, not a live feed.

## Guyana snapshot (September 13, 2026)

The original research covered 46 open opportunities (28 government, 18 private oil-and-gas) plus 8 leads still needing deadline confirmation. Files from that pass are unchanged:

- `Guyana Open Government and Private Sector Orders.xlsx` (original workbook)
- `data/guyana-open-tenders.csv`
- `research/all-open-orders-2026-09-13.md`
- `research/government-refresh-2026-09-13.md`

Headline items from that date: World Bank-funded Mahaica Bridge to Abary Bridge road works (due Oct 2, international bidders eligible), five CDB water transmission-mains packages (due Oct 6), and the first open Guyana government oil-and-gas tender seen (GUYOIL annual petroleum products RFP for gasoline/gasoil/ULSD/Jet A-1, due Sept 29). No open pharma tenders; the Ministry of Health buys via a prequalified-supplier list. Foreign bidders must register on the NPTAB portal at least 7 days before bidding.

## USA dataset (verified September 18, 2026)

The USA tab adds 95 records verified on September 18, 2026:

- 15 verified open federal solicitations (SAM.gov)
- 10 SBA SubNet subcontracting notices (the complete live listing that day)
- 2 open K-12 school-district technology bids: Clarkston Community Schools, Michigan (classroom technology for the new junior high, bids due Sept 22) and Calcasieu Parish School Board, Louisiana (E-Rate wireless access points, digital proposals due Sept 30, sealed hard copy due Oct 2). Both have scope limits; they are network and classroom tech, not student-device refreshes.
- 40 recent federal awards (usaspending.gov)
- 12 DHS acquisition forecasts (forecasts are plans, not open bids)
- 34 winning contractors
- All 50 state procurement routes, with 45 verified state portal links. Louisiana, Mississippi, South Carolina, South Dakota, and Wyoming entries are blank because they were not safely verified; 8 more are labeled access-unverified.
- A SAM.gov bidding roadmap for first-time federal bidders.

Data files:

- `USA Government Contract Opportunities.xlsx` (full USA workbook)
- `data/usa-opportunities-2026-09-18.csv`
- `data/usa-subcontracts-2026-09-18.csv`
- `data/usa-state-portals-2026-09-18.csv`
- `research/usa-2026-09-18/VERIFICATION_LOG.md` (per-record verification notes and caveats)
- `research/usa-2026-09-18/verification-report-20260918.md`

## State education project sweep (verified September 18, 2026)

A 10-state sweep (CA, TX, FL, NY, IL, PA, OH, GA, NC, MI) verified 16 open K-12 and higher-education construction and facilities bids, deadlines September 22 through October 29, 2026, from Florida, New York, North Carolina, Michigan, California, Illinois, and Pennsylvania.

Data files:

- `data/state-education-bids-2026-09-18.json`
- `research/state-education-sweep/excluded-20260918.md` (near-misses with URL and reason)

Honest coverage notes:

- This is a dated snapshot, not a live feed. Deadlines move.
- Several federal deadlines fall between September 21 and 25, 2026 and must be rechecked before use.
- New York and North Carolina records show dates only on the official listings; no submission times.
- Michigan and California records are official advertisement documents (SIGMA ad, LAUSD RAMP form) read via mirror; verify each on the SIGMA or LAUSD supplier portal before bidding.
- Zero verified open IT-hardware bids (laptops, Chromebooks, desktops, printers, copiers) in all 10 sweep states. Districts overwhelmingly buy devices through master and cooperative contracts (TX DIR, REMC Save, MEEC), not open bids; fall refresh buying already happened over summer. The category is left empty on purpose, not padded.
- Zero open prime or subcontracting notices on official state portals.
- Zero verified records for Ohio and Georgia.
