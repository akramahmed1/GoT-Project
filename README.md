# GoT Project

Open tenders, RFPs, RFQs, EOIs and purchase orders in Guyana, tracked across government and private sector sources. Built for suppliers and contractors who want to bid on or fulfill Guyanese procurement opportunities.

## What is here

- **Guyana Open Government and Private Sector Orders.xlsx** - the full workbook. One row per opportunity with buyer, tender reference, title, category, quantity or scope, submission deadline, official notice link and bidder notes. A second tab holds leads whose deadlines still need confirmation.
- **data/guyana-open-tenders.csv** - the same data as a flat CSV.
- **research/** - dated research notes showing what was verified, from which source, and what could not be confirmed.

## Coverage

As of 13 September 2026 the tracker holds 47 open opportunities:

- 28 government notices (e-procure portal, DPI adverts, GPL, Guyana Water Inc, CHPA, GUYOIL, ministries)
- 18 private oil and gas supply chain notices (Local Content Register: GYSBI, SBM Offshore, Oceaneering, Halliburton, CNOOC, Tenaris, Champion X, G-Boats)
- 1 multilateral notice (UNDP Guyana)

## Live dashboard

An interactive dashboard with buyer type filtering and the same 47 rows is published separately.

## How to read the data

- Deadlines are in Guyana time (AST, UTC-4).
- Where a quantity or scope column says the detail is not publicly stated, that information only exists inside the paid or collected bid documents. Nothing here is invented.
- Rows flagged as unverified need a direct check of the notice page before acting. Government adverts published as scanned images and some JS rendered portals could not be machine read.
- Private oil and gas bidders generally need a Guyana Local Content Certificate (or proof of application) under the Local Content Act 2021.
- Foreign government bidders generally must register on the NPTAB e-procure portal at least 7 days before bidding.

## Refreshing

This is a point in time snapshot. Tenders close, new ones publish daily. Re-run the source sweep (eprocure.gov.gy, DPI adverts, gplinc.com/bids, guyanawaterinc.com/procurement, chpa.gov.gy, guyoil.gy, lcregister.petroleum.gov.gy/opportunities, UNDP procurement notices) before acting on any row.

## USA opportunities (added 18 September 2026)

**USA Government Contract Opportunities.xlsx** - verified federal snapshot plus a new K-12 school IT-hardware tab. Research date 18 September 2026. Contains 13 verified open federal notices, 10 open SBA SubNet subcontract notices, all 50 state procurement portals mapped, and a dedicated K-12 IT Hardware sheet.

The K-12 tab holds 2 school-district technology-hardware solicitations that met the verification bar on the research date:

- Calcasieu Parish School Board (Louisiana), E-Rate Yr. 30 RFP 330-WAP for wireless access points. Digital proposals due September 30, 2026 noon CST; sealed hard copy due October 2, 2026 noon CST. Note: network infrastructure hardware, not end-user devices; E-Rate SPIN and FCC registration required.
- Clarkston Community Schools (Michigan), 2022 Bond Program classroom technology for New Clarkston Junior High (RFP-CLA-260000002552-1). Bids due September 22, 2026 12:00 PM EST. Note: classroom technology for new construction; the ad does not confirm end-user laptops, Chromebooks, desktops, printers, or copiers.

Why only 2: the 2026 school device refresh cycle ran February to July, so by mid-September most device bids are closed. Most districts buy computers and printers through state contracts (for example DIR in Texas), purchasing cooperatives, board-approved vendor lists, and RFQs to approved suppliers rather than public RFPs. The next open-bid wave is expected January to April 2027. Full method, caveats, and the excluded near-miss list are in research/usa-opportunities-verification-2026-09-18.md, and the machine-readable records are in data/usa/k12-it-hardware.json.
