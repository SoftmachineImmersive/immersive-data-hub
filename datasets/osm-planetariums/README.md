# OSM Based Planetariums Dataset

The OSM Based Planetariums dataset provides a global list of planetarium venues derived from OpenStreetMap (OSM) and enriched with regional and population context.  
It is designed for research, immersive media analysis, venue mapping, strategic planning, and global market comparison.

The dataset is curated by **Martin Sambauer** (https://martin-sambauer.com)  
and published and owned by **Softmachine** (https://softmachine.de) as part of the immersive-data-hub.

---

## Contents

This dataset consists of:

- **planetariums_with_population_and_regions_FINAL_FORMATTED.csv**  
  The main data file containing all global planetarium venues, with geolocation, country, region, population context and operational status.

- **methodology.md**  
  A detailed documentation of how the dataset was collected, enriched, verified, and structured, including inclusion criteria, OSM extraction logic, population data merging and limitations.  
  → View here:  
  https://github.com/SoftmachineImmersive/immersive-data-hub/blob/main/datasets/osm-planetariums/methodology.md

- **schema.json**  
  A JSON Schema defining all expected fields, datatypes and structural rules of the CSV for validation and interoperability.  
  → View here:  
  https://github.com/SoftmachineImmersive/immersive-data-hub/blob/main/datasets/osm-planetariums/schema.json

---

## Purpose

This dataset enables:

- mapping and comparison of planetarium venues globally  
- geographic and demographic analysis  
- research into immersive infrastructures  
- planning of Fulldome distribution strategies  
- integration into larger immersive-media datasets and pipelines  
- academic or journalistic use

It offers a unified, verified, global baseline for understanding the density and distribution of planetariums across world regions.

---

## Source principles

- OSM is the primary global source.  
- Data is enriched with population and world-region context.  
- All entries are checked for plausibility and duplicates.  
- When possible, venues are verified using official websites or institutional references.  
- Status information (`status_active`) is manually curated.

For full details see **methodology.md**.

---

## Licensing

The dataset is released under **Creative Commons Attribution 4.0 International (CC BY 4.0)**.

Required attribution:

**Softmachine** (softmachine.de) – Publisher  
**Curated by Martin Sambauer** (martin-sambauer.com)

For additional notes on textual content and reuse, see methodology.md.

---

## Explore and licensing

Explore. repository folder · CSV dataset · article with insights  
Licensing. CC BY 4.0 · © Softmachine · softmachine.de
