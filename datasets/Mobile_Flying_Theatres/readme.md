# Mobile Flying Theatres — Mobile LED Domes

This dataset folder is part of the **Immersive Data Hub**, maintained by **Softmachine Immersive Productions**, a creative agency specializing in immersive media, fulldome experiences, and data-driven strategy.

We set out to answer a practical question for B2B projects:

> **Which Flying Theatres and LED dome systems are explicitly suitable for mobile / temporary deployments (rapid install, easy reassembly, pop-ups, touring)?**

The outcome is a pair of carefully curated, machine-readable CSVs plus a transparent methodology.

---

## Folder & Data Files

- **Folder**  
  `datasets/Mobile_Flying_Theatres/`  
  https://github.com/SoftmachineImmersive/immersive-data-hub/tree/main/datasets/Mobile_Flying_Theatres

- **Manufacturers & products (Flying Theatres) with mobility evidence**  
  `flying_theatre_manufacturers_products_mobile.csv`  
  https://github.com/SoftmachineImmersive/immersive-data-hub/blob/main/datasets/Mobile_Flying_Theatres/flying_theatre_manufacturers_products_mobile.csv

- **Venues (strictly verified) — Clean v1**  
  `flying_theatres_clean_v1.csv`  
  https://github.com/SoftmachineImmersive/immersive-data-hub/blob/main/datasets/Mobile_Flying_Theatres/flying_theatres_clean_v1.csv

> Context: We first attempted to enumerate Flying Theatres globally and arrived at this verified list (`flying_theatres_clean_v1.csv`). It is **much smaller** than the number of planetariums, which we study separately here:  
> https://github.com/SoftmachineImmersive/immersive-data-hub/blob/main/datasets/osm-planetariums/README.md  
> We expect additional Flying Theatres to exist but not surface on the open web due to **naming ambiguity** (e.g., listed as *tourist attraction*, *ride*, *flight experience*, *flying cinema*) and inconsistent operator terminology.

---

## Key Result (tl;dr)

- **LED domes:** In this research cycle, we found **no** official LED-dome product pages that **explicitly** claim “mobile/portable/touring” (so entries remain **No** for explicit mobility).
- **Flying Theatres:** We identified **at least one** candidate with explicit fast-setup wording: **Brogent o-Ride / o-Ride E**.  
  Most relevant evidence (manufacturer announcement covered by a recognized trade outlet):  
  *Amusement Today — IAAPA Expo Asia 2025:* “quick installation, easy operation, and minimal space requirements” for **o-Ride E**  
  https://amusementtoday.com/2025/07/brogent-announces-the-opening-of-niagara-takes-flight-and-debuts-two-new-rides-at-iaapa-expo-asia-2025/

---

## Scope & Definitions

- **Flying Theatre (FT):** Motion-seat theatre with a large curved or domed screen delivering a “flying” sensation.  
- **LED dome:** Hemispherical/spherical **LED** display surfaces (not projection domes).  
- **Explicitly mobile (Yes):** The **official product page** or **official manufacturer release** uses clear wording such as *mobile / portable / touring / rapid installation / quick install / easy reassembly* for the **product itself**.  
  - “Modular,” “fits existing buildings,” or “for exhibitions” **alone** does **not** qualify.

---

## Methods (transparent & reproducible)

**1) Source discovery**  
- Seed list from known FT/LED vendors and **verified venues**; expand via conference programs (e.g., IAAPA) and manufacturer ecosystems.  
- Only **official manufacturer pages** and **official brochures/press releases** are accepted as primary sources.

**2) Mobility evidence test (strict threshold)**  
- `explicitly_mobile = Yes` **only** if the product’s **official page/release** contains explicit mobility wording (see definitions).  
- “Implied mobility” (e.g., exhibitions or modular panels) remains **No** until explicit language is found.

**3) Venue verification (Clean v1)**  
- Each venue entry is backed by an **official operator website** and a **robust Google Maps query link**.  
- Aggregators and unverified lists are excluded to keep the table dependable for outreach and benchmarking.

**4) Normalization & fields**  
- **Manufacturers (FT):** `manufacturer`, `product_name`, `website_official`, `product_url`, `explicitly_mobile (Y/N)`, `mobile_evidence / note`, `mobile_claim_source_url`, `use_cases`, `maps_url` (query).  
- **Venues (Clean v1):** `name`, `city`, `country`, `website_url` (operator), `maps_url` (query).  
- Consistent naming and deduplication; links prefer official sources.

**5) QA**  
- Manual review of claims, link hygiene, consistent naming, and removal of ambiguous entries.  
- We favor a **smaller but accurate** dataset over speculative coverage.

**6) Naming ambiguity & discoverability**  
- Many venues are marketed under **non-standard labels** (e.g., *tourist attraction*, *ride*, *flight*, *flying cinema*), which suppresses search recall. The **Clean v1** list is therefore conservative by design and expected to grow as verifiable sources emerge.

---

## How to Use

- Start with **`flying_theatre_manufacturers_products_mobile.csv`** to identify candidate systems for pop-ups, touring, or interim venues. Filter by `explicitly_mobile == "Y"` and review `mobile_claim_source_url` for the exact wording and constraints.  
- Use **`flying_theatres_clean_v1.csv`** for verified venue examples and initial partner outreach.  
  
---

## Limitations

- Some manufacturers communicate mobility only in **press releases** rather than product pages; where the release is official and clearly product-specific, we link it.  
- Regulatory compliance (load, evacuation, operator training) is **site-specific** and must be validated per project.

---

## Contributing

- Propose additions via **Pull Request** or **Issue**.  
- Please include the **official product URL** and quote the **exact mobility wording**.  
- We will only mark `explicitly_mobile = Yes` with **clear, official** language.

---

## License & Maintainer

This dataset is released under **Creative Commons Attribution 4.0 International (CC BY 4.0)**.  
Please credit: **Softmachine Immersive — https://softmachine.de**

Maintained by **Softmachine Immersive Productions** — immersive experiences, fulldome shows, and data-driven strategy for brands, museums, and events.
