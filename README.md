# Data Centers + Wildfires

Interactive Leaflet maps of historical US wildfire perimeters, with an optional overlay of large AI data center campuses and a county-level climate-risk heat layer.

## Combined map: AI data centers x wildfires

- **File:** `ai-datacenters-x-wildfires.html` - self-contained; open in any browser (needs internet for basemap tiles and the Leaflet CDN)
- **Data centers:** 128 US sites of 100 MW or more (~116.5 GW total) - 65 operational, 31 under construction, 25 planned, 7 announced. Built from original public-records research (permits, operator announcements, filings), seeded by aidatacenterindex.com (CC BY 4.0 - attribution required). Includes the Fermi America HyperGrid (Project Matador) 11 GW planned campus near Amarillo, TX.
- **Features:** four status toggles (operational / under construction / planned / announced), dots sized by MW, per-site popup with operator, capacity, source links, and distance to nearest burn since 2016
- **Headline stats (recomputed on this dataset):** 36 of 59 AI campuses >= 500 MW sit within 50 miles of land that burned since 2016; 15 are within 25 miles
- **Climate-risk heat layer:** FEMA National Risk Index (public domain), county-level all-hazard and wildfire risk ratings; separate toggle, off by default
- **Fires layer:** same NIFC/WFIGS data and controls as the fire-only map below
- **Related:** popups link out to dcmap.us for more on a site (their terms prohibit copying their dataset, so we link rather than import)

## Dataset: us_data_centers_100mw_plus.csv

112-row dataset of US data center campuses >= 100 MW, with per-row sources. The map layer (128 sites) includes additional sites from ongoing research beyond this sourced CSV.

- **Schema:** `name, operator, city, state, lat, lon, coord_source, capacity_mw, mw_basis, status, notes, source_url, provenance`
- **`provenance`** records where each row originated (e.g. `seed: aidatacenterindex.com (CC BY 4.0)`), so the CC BY 4.0 attribution obligation travels with the data
- **`source_url`** is a per-row public source (operator page, permit record, filing, or press report) supporting the capacity/status claim
- **`mw_basis`** notes what the MW figure represents when it is not a like-for-like IT-load figure (e.g. announced campus capacity vs. delivered capacity, permitted on-site generation)
- **`coord_source`** flags coordinate quality: rows from aidatacenterindex records carry site coordinates, while `geocoded` rows are city-level approximations and should not be read as exact site locations
- **Known coverage gaps:** hyperscalers frequently do not disclose campus-level MW, so some large operational campuses are understated or missing; announced vs. delivered capacity is mixed across the industry and flagged per-row in `mw_basis`/`notes` where known

## Fire-only map

- **Data source:** NIFC / WFIGS Interagency Fire Perimeter History (open data)
- **Coverage:** Continental US, 2016 through September 2026 (2026 partial)
- **Scope:** Wildfires >= 300 acres; prescribed burns excluded
- **File:** `us-wildfire-perimeters-2016-2026.html` - self-contained; open in any browser (needs internet for the basemap tiles and Leaflet CDN)
- **Features:** filter by year and minimum fire size, click any fire for name/year/acres, annual acres bar chart
