## OSM Based Planetariums Dataset – Methodology

### 1. Overview  
The OSM Based Planetariums dataset compiles geolocated planetarium venues around the world, enriched with population and regional context data. It is aimed at immersive media professionals and researchers who need a global view of planetarium distribution in relation to regional population and infrastructure.

Version: 1.0.0  
Last updated: 2025-11-19  
Maintainer: Martin Sambauer (martin-sambauer.com)  

### 2. Source materials  
The dataset primarily uses the following sources:  
- OpenStreetMap / Overpass API for venue location and basic metadata.  
- National and regional population data (e.g., from World Bank / United Nations Development Programme) for contextual regional metrics.  
- Additional manual verification via official planetarium websites and institutional profiles where available.

### 3. Inclusion criteria and scope  
#### 3.1 Definition of “planetarium”  
For this dataset, a planetarium is any venue with a dome theatre or immersive projection space dedicated primarily to astronomical education or immersive media presentation.

#### 3.2 Inclusion criteria  
- Location must be geocoded (latitude & longitude) and linked to a physical address.  
- Must appear in OSM with a relevant tag (e.g., `amenity=planetarium`, `science_center`, or similar) or be manually added with verification.  
- Must be currently operational (active venue) unless explicitly noted otherwise.  
- Additional context: associated city, region, and population-category data must be available or derivable.

#### 3.3 Exclusion criteria  
- Temporary pop-up installations without a fixed venue.  
- Venues exclusively virtual or home-based without public access.  
- Venues without sufficient spatial data or unable to verify public availability.

#### 3.4 Geographic and temporal scope  
- Global: no region is pre-excluded.  
- The dataset is cross-sectional: it captures the status of venues as of the last verification date.  
- Historical venues may be included if relevant, with status marked as inactive.

### 4. Data model  
Each row in `planetariums_with_population_and_regions_FINAL_FORMATTED.csv` includes:  
- Venue identification and naming: `id`, `name`  
- Classification and type: `type`, `format`, `tagged_as_planetarium`  
- Geographic data: `country`, `region`, `city`, `latitude`, `longitude`  
- Population and regional context: `population`, `region_population`, `world_region`, etc.  
- Operational status and notes: `status_active`, `notes`  
- Source and verification: `source`, `source_url`, `last_verified`

Full schema defined in `schema.json`.

### 5. Collection workflow  
#### 5.1 Data extraction  
1. Retrieve OSM entries with relevant tags using Overpass queries.  
2. Clean and normalise names (remove duplicate entries, harmonise naming conventions).  
3. Geocode missing coordinates when necessary.

#### 5.2 Enrichment  
1. Match venue country and region to population datasets (UNDP / World Bank).  
2. Compute derived fields (e.g., world region category, per-capita context).  
3. Verify each entry via official zone or venue website and record `last_verified`.

#### 5.3 Classification  
- Assign world region (e.g., Europe, North America, Asia-Pacific, Latin America, MENA).  
- Assign status: active/inactive.  
- Tag with formats (e.g., “Fulldome”, “Hybrid immersive theatre”) where available.

### 6. Quality checks & limitations  
- All entries must contain id, name, country, latitude, longitude, and status_active.  
- Duplicate coordinates or names are flagged for review.  
- Smaller venues in non-English regions may be under-represented due to language and information access bias.  
- Population and region data are snapshots and may lag behind current values.

### 7. Updates and community contributions  
The dataset is updated periodically.  
Contributors may suggest new venues or corrections via pull requests.  
Recommended to include at least name, country, city, coordinates, and source_url when submitting.

### 8. Licensing and reuse  
The dataset is released under CC BY 4.0.  
Attribution: Softmachine (softmachine.de) · Dataset curated by Martin Sambauer (martin-sambauer.com)  
Detailed attribution instructions and reuse conditions are in the README file.

### Explore and licensing  
Explore. repository folder · CSV dataset · article with insights  
Licensing. CC BY 4.0 · © Softmachine · softmachine.de
