## Mobile Flying Theatres & Mobile LED Domes Dataset – Methodology

### 1. Overview  
This dataset captures global instances of mobile flying theatre systems and mobile LED dome venues.  
It is designed to support the analysis of immersive venue mobility, deployment models, market reach, and spatial-temporal distribution of mobile immersive infrastructure.

Version: 1.0.0  
Last updated: 2025-11-19  
Maintainer: Martin Sambauer (martin-sambauer.com)

### 2. Source materials  
Primary sources include:  
- Manufacturer product listings and press releases  
- Trade show catalogues, rental-service brochures and mobile venue deployment announcements  
- Official venue websites and location databases  
- Publicly available data via industry directories, news articles and market reports

### 3. Inclusion criteria and scope  
#### 3.1 Definition of mobile flying theatre / mobile LED dome  
- A venue or installation that is designed for transport, rapid setup, and immersive projection (either flying theatre seat-based, or LED dome structure)  
- Mobile means it can be relocated and deployed rather than being permanently fixed  
- Must have a public-facing commercial or institutional use case (e.g., touring show, expo installation, rental for festivals)  

#### 3.2 Inclusion criteria  
- Must be identifiable by name, manufacturer or operator  
- Must include at least one deployment location, date or region  
- Must include specification features (e.g., dome diameter, seat count, mobility flag) if available  
- Must be verifiable through public sources  

#### 3.3 Exclusion criteria  
- Fixed permanent venue that is not mobile  
- Mobile structures without immersive projection or entertainment format  
- Pop-ups with insufficient data for location, date, or operator  

#### 3.4 Geographic and temporal scope  
- Global scope without geographic restriction  
- Timeframe: deployments up to the last verified date  
- Status: active and archived deployments may both be included; inactive or historical entries must have status flagged accordingly  

### 4. Data model  
Each record in the dataset file represents one mobile flying theatre or mobile LED dome installation.  
Key fields include:  
- Unique identifier (`id`)  
- Name of installation or mobile venue  
- Manufacturer / Operator  
- Mobility flag (`mobile = true/false`)  
- Venue type (Flying Theatre, LED Dome)  
- Deployment specification (seat count, dome diameter, LED panel area)  
- Deployment status (`status_active`)  
- Location information (country, city, region, latitude, longitude)  
- Deployment date(s) (first deployment, latest deployment)  
- Reference/source URL(s)  
- Notes

Full field definitions are described in `schema.json`.

### 5. Collection workflow  
#### 5.1 Candidate extraction  
- Start from manufacturer lists and trade directories  
- Compile entries of mobile venues and touring units  
- Create unique IDs and standardise names  
- Merge duplicate entries and identify variants  

#### 5.2 Verification and enrichment  
- Verify each entry via manufacturer website or press release  
- Extract location and deployment data where available  
- Geocode coordinate data when latitude/longitude not provided  
- Add operational status and relevant notes  

#### 5.3 Classification and specification  
- Assign primary type: “Flying Theatre” or “LED Dome”  
- Set mobility flag: always true for this dataset context  
- Populate specification fields if available (seat count, dome diameter, LED panel area)  
- Tag with formats (e.g., “VR motion seats”, “LED immersive dome”)  

### 6. Quality checks & limitations  
- Each record must contain `id`, `name`, `manufacturer`, `mobile`, `type`, `country`, `status_active`, `source`  
- Duplicate or nearly identical entries flagged and reviewed  
- Deployment dates and locations verified for plausibility  
- Limitations:  
  - Data is reliant on publicly available information.  
  - Some mobile installations may operate under private contracts and thus be under-represented.  
  - Specification details (seat count, diameter) may be incomplete or inconsistent.  
  - Geographical bias: English-language and trade-show reported entries are easier to capture.

### 7. Updates and community contributions  
- Contributions via pull requests are welcome: suggest new entries or updates to existing ones  
- When submitting a new entry: provide `name`, `manufacturer`, `type`, `country`, `first_deployment_date`, `source_url`  
- For updates: indicate what changed (e.g., “new deployment location”, “installation retired”)  

### 8. Licensing and attribution  
The dataset is released under **Creative Commons Attribution 4.0 International (CC BY 4.0)**.  
Attribution: Softmachine (softmachine.de) – Publisher  
Curated by Martin Sambauer (martin-sambauer.com)

Explore. repository folder · CSV dataset · article with insights  
Licensing. CC BY 4.0 · © Softmachine · softmachine.de
