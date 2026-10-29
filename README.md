# Recycling & Compost Contamination in Abbotsford, BC

A Tableau dashboard built on City of Abbotsford collection data to find out what is contaminating recycling and compost bins, where it happens, and which households keep doing it.

**Tools:** Tableau (data relationships, dashboards), Excel

## Business question

The City pays to deal with contaminated recycling and compost. What is going in the wrong bin, and where should education efforts be focused to reduce it?

## Data

Two related datasets from the City of Abbotsford:

| Dataset | Rows | What it contains |
|---|---|---|
| **Contamination** | 5,041 | Each time a collection truck flagged a contaminated bin (Apr 26 – Dec 8, 2021): bin type, what the contamination was, route, date and location |
| **Zones** | 83,207 | Every bin in the city: address, bin type and size, and its collection zone |

The two are linked on each bin's serial number, so every contamination incident can be traced to its street and collection zone.

## Approach

1. Connected both Excel sheets in Tableau and related them on `SerialNumber`.
2. Built views of contamination by bin type, by zone, and by zone → street → bin type.
3. Combined them into dashboards showing where and how much contamination occurs.
4. Calculated rates per zone and repeat incidents per bin in a follow-up analysis.

## Key findings

- **Recycling bins are the main problem.** They account for 64% of incidents (3,226), compost bins 35% (1,778), and garbage bins under 1%.
- **Three types of contamination make up 93% of incidents:**
  - Plastic and plastic bags: 51% (2,566)
  - Garbage in the wrong bin: 29% (1,437)
  - Non-recyclable plastic: 13% (662)
- **The same households repeat the mistake.** About a third of flagged bins (1,023 of 3,101) were flagged more than once. One bin was flagged 18 times.
- **Dark Green zone has the highest rate.** It logged 1,601 incidents, about 23 per 100 recycling and compost bins. That compares with about 13 per 100 in the Red zone.
- **A few streets stand out:** Babich St (70 incidents), Bradner Rd (68) and Lefeuvre Rd (56).

## Recommendations

1. **Run a plastic-bag campaign first.** Plastic bags alone cause half of all incidents, so one clear message ("no plastic bags in the blue bin") targets the biggest problem.
2. **Contact repeat households directly.** Reaching the ~1,000 bins with repeat incidents through letters or bin tags is cheaper and more targeted than a city-wide campaign.
3. **Start with Dark Green zone and the top streets**, then measure whether incident rates fall before expanding.

## Data quality notes

- Incidents appear in only 5 of the 10 zones (Dark Green, Purple, Dark Blue, Yellow, Red). The other five have at most one record each, which most likely means contamination wasn't being tracked there yet, not that those zones are clean. Zone comparisons should be limited to the five tracked zones.
- Monthly incidents rise from 25 in April to 1,364 in November. That could reflect tracking being rolled out over time rather than behaviour getting worse, so I would confirm with the City before reading it as a trend.

## Files

| File | Contents |
|---|---|
| `Tableau-Contamination.twb` | Tableau workbook: 7 sheets and 4 dashboards |
| `Contamination+Zones.xlsx` | Source data (Contamination and Zones sheets) |

*Data source: City of Abbotsford. Dashboard created March 2022.*
