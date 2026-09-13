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
