# US Wildfire Perimeters Map + AI Data Centers

Interactive Leaflet maps of historical US wildfire perimeters, with an optional overlay of large AI data center campuses and a county-level climate-risk heat layer.

## Combined map: AI data centers x wildfires

- **File:** `ai-datacenters-x-wildfires.html` - self-contained; open in any browser (needs internet for basemap tiles and the Leaflet CDN)
- **Data centers:** aidatacenterindex.com (CC BY 4.0, data as of Jul 2026); 56 continental US sites plotted (28.6 GW) - 34 operational, 12 under construction, 10 planned
- **Features:** status toggles (operational / under construction / planned), dots sized by MW, per-site popup with operator, capacity, and distance to nearest burn since 2016; headline stat: 10 of 21 campuses >= 500 MW sit within 50 miles of land burned since 2016
- **Climate-risk heat layer:** FEMA National Risk Index (public domain), county-level all-hazard and wildfire risk ratings; separate toggle, off by default
- **Fires layer:** same NIFC/WFIGS data and controls as the fire-only map below
- **Related:** popups link out to dcmap.us for more on a site (their terms prohibit copying their dataset, so we link rather than import)

## Fire-only map

- **Data source:** NIFC / WFIGS Interagency Fire Perimeter History (open data)
- **Coverage:** Continental US, 2016 through September 2026 (2026 partial)
- **Scope:** Wildfires >= 300 acres; prescribed burns excluded
- **File:** `us-wildfire-perimeters-2016-2026.html` - self-contained; open in any browser (needs internet for the basemap tiles and Leaflet CDN)
- **Features:** filter by year and minimum fire size, click any fire for name/year/acres, annual acres bar chart
