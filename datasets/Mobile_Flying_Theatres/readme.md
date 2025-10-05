
# Mobile Flying Theatres – Open Datasets (Softmachine)

This directory contains open, machine-readable datasets created by Softmachine to answer a practical question for B2B immersive projects:

> **Which Flying Theatres and LED dome systems are explicitly suitable for mobile / temporary deployments?**

Our goal is to help operators, brands, museums, and event teams assess whether an immersive theatre or LED dome can be **rapidly installed**, **easily reassembled**, and run as **pop-ups or touring exhibits**.

---

## Datasets

- Repository folder (all files):  
  https://github.com/SoftmachineImmersive/immersive-data-hub/tree/main/datasets/Mobile_Flying_Theatres

- Manufacturers & products (Flying Theatres), incl. explicit mobility flag (**Y/N**) and evidence:  
  https://github.com/SoftmachineImmersive/immersive-data-hub/blob/main/datasets/Mobile_Flying_Theatres/flying_theatre_manufacturers_products_mobile.csv

- Venues (strictly verified) – Clean v1:  
  https://github.com/SoftmachineImmersive/immersive-data-hub/blob/main/datasets/Mobile_Flying_Theatres/flying_theatres_clean_v1.csv

> Note: We also maintain a **LED dome manufacturers** table in this folder. In the current research round, no entry met our “explicitly mobile” criterion (see Methods).

---

## Scope and Definitions

- **Flying Theatre (FT):** Motion-seat theatre with a large curved or domed screen delivering a “flying” sensation.
- **LED dome:** Hemispherical/spherical LED display (as opposed to projection domes).
- **Explicitly mobile (Y):** The **official product page** (or official manufacturer release) uses clear wording such as *mobile / portable / touring / rapid installation / easy reassembly / quick install* for the **product itself**.  
  - “Modular”, “fits existing buildings”, or “suitable for exhibitions” **alone** does **not** qualify as “explicitly mobile”.

---

## Key Finding (short)

- **LED domes:** In this research cycle we found **no official product page** that **explicitly** states mobility/portability for LED domes. All entries currently fall under **N (no explicit claim)**.
- **Flying Theatres:** We found **at least one candidate** with explicit “rapid installation / minimal space” wording: **Brogent o-Ride / o-Ride E**.  
  Most relevant source: *Amusement Today* coverage of IAAPA Expo Asia 2025 – “quick installation, easy operation, and minimal space requirements” for **o-Ride E**  
  → https://amusementtoday.com/2025/07/brogent-announces-the-opening-of-niagara-takes-flight-and-debuts-two-new-rides-at-iaapa-expo-asia-2025/

---

## Methods

1. **Source-first curation**  
   - Start from known FT/LED vendors and venues; add candidates via conference programs (e.g., IAAPA), trade coverage, and manufacturer ecosystems.
   - Only consider entries with **official manufacturer pages** (or official brochures/press releases) that describe the **specific product**.

2. **Mobility evidence test (strict)**  
   - Mark **explicitly_mobile = Y** only if the **product page** (or **official manufacturer release**) includes explicit mobility wording for the product (examples: *mobile*, *portable*, *touring*, *rapid installation*, *easy reassembly*, *quick install*).  
   - “Implied mobility” (e.g., mentions of exhibitions or modularity) is recorded in **notes** but remains **N** unless the above wording is present.

3. **Venue verification (Clean v1)**  
   - The venues table is intentionally small and **strictly verified**: official operator websites for each venue + robust Google Maps query links. Aggregators and unverified lists are excluded.

4. **Fields & consistency**  
   - **Manufacturers (FT & LED):** `manufacturer`, `hq_city`, `hq_country`, `website`, `product_name`, `product_url`, `explicitly_mobile (Y/N)`, `mobile_evidence / mobile_claim_note`, `mobile_claim_source_url`, `use_cases`, `maps_link`.  
   - **Venues (Clean v1):** `name`, `city`, `country`, `website_url` (operator), `maps_url` (query), plus notes where relevant.  
   - All links prefer **official** sources; all names normalized for deduplication.

5. **What we deliberately do *not* do (yet)**  
   - No second-hand claims from resellers or non-official blogs.  
   - No projection domes in the LED table (separate technology class).  
   - No “implied = Y”. We keep the threshold high to maintain credibility.

---

## How to Use

- **Manufacturers (FT):** Start with `flying_theatre_manufacturers_products_mobile.csv`. Filter by `explicitly_mobile == "Y"` and review `mobile_claim_source_url` for the exact wording and constraints (space, rigging, operator requirements).  
- **Venues:** Use `flying_theatres_clean_v1.csv` as a verified reference set for examples, benchmarking, or outreach.  
- **LED domes:** Use the LED table for vendor discovery; mobility remains **N** until an official page explicitly states it.

---

## Limitations

- Some manufacturers publish mobility language in **press releases** rather than on product pages. Where that release is official (e.g., manufacturer quote hosted by a recognized trade outlet), we include it as evidence and link it.  
- Certification, load, and evacuation constraints vary by country/venue; “quick install” does not equal “no permitting”. Always confirm engineering and code compliance.

---

## Contributing / Updates

- Propose additions or corrections via Pull Request or Issue.  
- Please include: **official product URL**, exact **mobility wording**, and (if possible) a PDF or permanent page location.  
- We will only flip `explicitly_mobile` to **Y** with **clear, official wording** on the product or official release page.

---

## Citation

If you reference these datasets, please cite:

> Softmachine (2025). *Mobile Flying Theatres – Open Datasets.*  
> GitHub: `immersive-data-hub/datasets/Mobile_Flying_Theatres`  
> Data files:  
> - `flying_theatre_manufacturers_products_mobile.csv`  
> - `flying_theatres_clean_v1.csv`  
> - (LED dome manufacturers table in the same folder; current entries: explicitly_mobile = N)

---
