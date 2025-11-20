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
  Documentation of how the dataset was collected, enriched, verified, and structured, including inclusion criteria, OSM extraction logic, data cleaning, population merging, and limitations.  
  → https://github.com/SoftmachineImmersive/immersive-data-hub/blob/main/datasets/osm-planetariums/methodology.md

- **schema.json**  
  A JSON Schema defining all expected fields, datatypes and structural rules of the CSV.  
  → https://github.com/SoftmachineImmersive/immersive-data-hub/blob/main/datasets/osm-planetariums/schema.json

---

## Purpose

This dataset examines how immersive science infrastructures like planetariums relate to broader socio-economic conditions such as education, GDP per capita and cultural investment. It treats planetariums as cultural indicators that reflect how societies value knowledge, learning and imagination.

It enables:

- mapping and comparison of planetarium venues globally  
- geographic and demographic analysis  
- research into immersive and science-communication infrastructures  
- planning of Fulldome distribution strategies  
- integration into larger immersive-media datasets and pipelines  
- academic or journalistic work

It offers a unified, verified global baseline for understanding the density and distribution of planetariums across world regions.

---

## Key results

- The dataset harmonises more than 800 verified planetariums worldwide into a consistent structure, combining OSM venue data with population and regional indicators.  
- Spatial and demographic comparison strongly suggests that the presence of planetariums correlates more with cultural policy, public education strategies and the long-term value placed on science communication than with pure economic strength.  
- Some highly developed regions show surprisingly low coverage, while culturally ambitious regions with moderate GDP maintain dense networks of venues.  
- This pattern indicates that planetariums are not typical market-driven entertainment infrastructures, but rather **publicly subsidised cultural-educational institutions** with long-term societal objectives.  
- This makes the dataset a useful **indirect indicator for publicly funded cultural infrastructure** within regions.  
- Whether planetariums should be categorised more broadly as systematic **economic subsidy institutions** (Ökonomische Zuschussbetriebe) requires further economic analysis and can be explored in future studies—this dataset provides an empirical baseline for such inquiries.

---

## Source principles

- OSM is the primary global source for venue locations and base attributes.  
- Population and world-region data come from established statistical datasets.  
- All entries undergo plausibility checks and manual verification where feasible.  
- Status information (`status_active`) is curated manually.

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

## Knowledge Graph Reference

This dataset is part of the Immersive Datasets library by Martin Sambauer.  
For semantic context and machine-readable metadata, see the root-level knowledge graph:

[martin-sambauer-knowledge-graph.json](../../martin-sambauer-knowledge-graph.json)

