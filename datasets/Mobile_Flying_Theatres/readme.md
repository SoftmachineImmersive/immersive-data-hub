# Mobile Flying Theatres — Mobile LED Domes

This dataset folder is part of the **Immersive Data Hub**, maintained by **Softmachine Immersive Productions**, a creative agency specializing in immersive media, fulldome experiences, and data-driven strategy.

We set out to answer a practical question for B2B projects:

> **Which Flying Theatres and LED dome systems are explicitly suitable for mobile / temporary deployments (rapid install, easy reassembly, pop-ups, touring)?**

The outcome is a pair of carefully curated, machine-readable CSVs plus a short, reproducible methodology.

---

## Placement in the Immersive Data Hub

- Repository (context):  
  **Immersive Data Hub** — structured data, research, and insights on immersive content, fulldome infrastructure, and market signals.

- Folder:  
  `datasets/Mobile_Flying_Theatres/`  
  https://github.com/SoftmachineImmersive/immersive-data-hub/tree/main/datasets/Mobile_Flying_Theatres

---

## Data Files

- **Flying Theatre manufacturers & products (with mobility evidence)**  
  `flying_theatre_manufacturers_products_mobile.csv`  
  https://github.com/SoftmachineImmersive/immersive-data-hub/blob/main/datasets/Mobile_Flying_Theatres/flying_theatre_manufacturers_products_mobile.csv

- **Flying Theatre venues (strictly verified)**  
  `flying_theatres_clean_v1.csv`  
  https://github.com/SoftmachineImmersive/immersive-data-hub/blob/main/datasets/Mobile_Flying_Theatres/flying_theatres_clean_v1.csv

*(A complementary LED-dome manufacturers table is maintained in this folder for discovery. In this research round, no LED dome product met our “explicitly mobile” threshold; see Methods.)*

---

## Scope & Definitions

- **Flying Theatre (FT):** Motion-seat theatre with a large curved or domed screen that delivers a “flying” sensation.  
- **LED dome:** Hemispherical/spherical **LED** display surfaces (not projection domes).  
- **Explicitly mobile (Yes):** The **official product page** or **official manufacturer release** uses clear wording such as *mobile / portable / touring / rapid installation / quick install / easy reassembly* for the **product itself**.  
  - “Modular,” “suits exhibitions,” or “fits existing buildings” **alone** does **not** qualify.

---

## Key Result (tl;dr)

- **LED domes:** In this cycle, we found **no** official LED-dome product pages that **explicitly** claim “mobile/portable” (so all entries remain **No**).  
- **Flying Theatres:** We identified **at least one** candidate with explicit fast-setup language: **Brogent o-Ride / o-Ride E**.  
  - Evidence (manufacturer announcement covered by a recognized trade outlet):  
    *Amusement Today — IAAPA Expo Asia 2025:* “quick installation, easy operation, and minimal space requirements” for **o-Ride E**  
    https://amusementtoday.com/2025/07/brogent-announces-the-opening-of-niagara-takes-flight-and-debuts-two-new-rides-at-iaapa-expo-asia-2025/

---

## Methods (transparent & reproducible)

**1) Source discovery**  
- Seed list from known FT/LED vendors, verified venues, conference programs (e.g., IAAPA), and manufacturer ecosystems.  
- Only **official manufacturer pages** and **official brochures/press releases** are accepted as primary sources.

**2) Mobility evidence test (strict threshold)**  
- `explicitly_mobile = Yes` **only** if the product’s **official page/release** contains explicit mobility wording (see definitions).  
- “Implied mobility” (e.g., mentions of exhibitions or modular panels) remains **No** until explicit language is found.

**3) Venue verification (Clean v1)**  
- Each venue entry is backed by an **official operator website** and a robust **Google Maps query link**.  
- Aggregators and unverified lists are excluded to keep the table dependable for outreach and benchmarking.

**4) Normalization & fields**  
- **Manufacturers (FT):** typical columns include  
  `manufacturer`, `product_name`, `website_official`, `product_url`, `explicitly_mobile (Y/N)`, `mobile_evidence / note`, `mobile_claim_source_url`, `use_cases`, `maps_url` (query).  
- **Venues (Clean v1):**  
  `name`, `city`, `country`, `website_url` (operator), `maps_url` (query).  
- Names normalized for deduplication; links prefer official sources.

**5) QA**  
- Manual review of claims, link hygiene (no dead aggregators), consistent naming, and removal of ambiguous entries.  
- We favor a **smaller but accurate** dataset over speculative coverage.

**6) Change management**  
- New evidence that meets the explicit threshold will be appended and version-tagged.  
- LED-dome entries will flip to **Yes** only with clear wording on an official product or official release page.

---

## How to Use

- Start with **`flying_theatre_manufacturers_products_mobile.csv`** to identify candidate systems for pop-ups, touring, or interim venues.  
  - Filter by `explicitly_mobile == "Y"` and review `mobile_claim_source_url` to understand scope and constraints.  
- Use **`flying_theatres_clean_v1.csv`** for verified venue examples and initial partner outreach.

---

## Limitations

- Some manufacturers communicate mobility in **press releases** rather than product pages; if the release is official and clearly product-specific, we link it.  
- Regulatory compliance (load, evacuation, operator training) is **site-specific** and must be validated per project.

---

## Contributing

- Propose additions via **Pull Request** or **Issue**.  
- Please include the **official product URL** and quote the **exact mobility wording**.  
- We only mark `explicitly_mobile = Yes` with **clear, official** language.

---

## License

This dataset is released under **Creative Commons Attribution 4.0 International (CC BY 4.0)**.  
Please credit: **Softmachine Immersive — https://softmachine.de**

---

## Maintainer

**Softmachine Immersive Productions**  
We create immersive experiences, fulldome shows, and data-driven strategy for brands, museums, and events.
