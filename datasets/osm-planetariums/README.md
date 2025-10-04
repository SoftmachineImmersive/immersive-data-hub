# Planetarium Distribution & Global Indicators

> This dataset is curated and maintained by [Softmachine Immersive Productions](https://softmachine.de), a studio for immersive storytelling and data-driven cultural research.

This README documents the full analytical journey that led to the creation of the dataset:
[**planetariums_with_culture_spending_v8.csv**](https://github.com/SoftmachineImmersive/immersive-data-hub/blob/main/datasets/osm-planetariums/planetariums_with_culture_spending_v8.csv)

This dataset brings together international data on planetariums, GDP, education, population, innovation, and cultural heritage investment. It provides a multi-dimensional view on the presence of planetariums per country or region, in the context of development, public infrastructure, and knowledge ecosystems.

---

## 🌍 Initial Phase: Planetarium Extraction from OSM

### 📊 OSM Planetariums Dataset

This dataset contains geolocated information on over 800 planetariums worldwide, extracted and curated from OpenStreetMap (OSM) using custom spatial processing.

### 🧪 Methodological Note: Planetarium Data Extraction and Processing

**1. Data Source**
Queried from OSM using the Overpass API with `amenity=planetarium`. Yielded 888 entries with coordinates and metadata.

**2. Country Assignment**
Coordinates matched to Natural Earth 1:50m country polygons. Full global assignment achieved.

**3. Data Cleaning**

* Empty names replaced with placeholders
* Google Maps links generated from lat/lon
* Faulty and duplicate entries removed

**4. Filtering**

* Observatories removed using multilingual keyword detection
* Final result: ~830 verified planetariums

**5. Translation and Normalization**

* Non-Latin names translated and retained in parentheses for clarity

**6. Completeness**

* Dataset reflects ~20–25% of the estimated global number of fulldome venues

**🌐 License:** Open Data Commons Open Database License (ODbL) 1.0
**Curation:** Softmachine Immersive Productions ([Website](https://softmachine.de/) / [GitHub](https://github.com/SoftmachineImmersive))

---

## 📂 Source Data

| Source                      | File                                                                                                                                                                                                                      | Description                                                                       |
| --------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------- |
| OpenStreetMap / Softmachine | [planetariums_clean_iso_matched_FINAL_FIXED.csv](https://github.com/SoftmachineImmersive/immersive-data-hub/blob/main/datasets/osm-planetariums/planetariums_clean_iso_matched_FINAL_FIXED.csv)                           | Cleaned list of geotagged planetariums worldwide                                  |
| World Bank                  | [API_NY.GDP.PCAP.CD_DS2_en_csv_v2_1211477.csv](https://github.com/SoftmachineImmersive/immersive-data-hub/blob/main/datasets/osm-planetariums/API_NY.GDP.PCAP.CD_DS2_en_csv_v2_1211477.csv)                               | GDP per capita (current US$)                                                      |
| UNDP                        | [HDR25_Statistical_Annex_HDI_Table.xlsx](https://github.com/SoftmachineImmersive/immersive-data-hub/blob/main/datasets/osm-planetariums/HDR25_Statistical_Annex_HDI_Table.xlsx)                                           | Education Index (expected years of schooling)                                     |
| World Bank                  | [API_SP.POP.TOTL_DS2_en_csv_v2_1211945.csv](https://github.com/SoftmachineImmersive/immersive-data-hub/blob/main/datasets/osm-planetariums/API_SP.POP.TOTL_DS2_en_csv_v2_1211945.csv)                                     | Total population by country                                                       |
| Our World In Data           | [expenditure-on-cultural-and-natural-heritage-per-capita.csv](https://github.com/SoftmachineImmersive/immersive-data-hub/blob/main/datasets/osm-planetariums/expenditure-on-cultural-and-natural-heritage-per-capita.csv) | Cultural heritage spending per capita (PPP USD)                                   |
| Final dataset               | [planetariums_with_culture_spending_v8.csv](https://github.com/SoftmachineImmersive/immersive-data-hub/blob/main/datasets/osm-planetariums/planetariums_with_culture_spending_v8.csv)                                     | Merged dataset with indicators for education, innovation, and cultural investment |

---

## 🔄 Processing & Merging Steps

### Initial Hypothesis:

> Planetarium density is correlated with GDP, education level, or innovation indicators.

### Results:

> **No strong correlation** found between GDP per capita, education index, or patent activity and the density of planetariums. This led to the hypothesis that the presence of planetariums is not purely economically driven but historically path-dependent or linked to cultural policy decisions.

### Final Discovery:

> A **moderately strong correlation** (Pearson r ≈ 0.65) was found between **cultural heritage spending per capita** and **planetariums per million inhabitants**.

---

## 📃 Final Dataset Fields

* `planetariums_count`: Count of planetariums per country
* `planetariums_per_million`: Core metric
* `gdp_per_capita_usd`: Economic indicator
* `education_expected_years`: UNDP educational development metric
* `population_with_tertiary_percent`: Share of population with higher education
* `region_patents_2023`: Total patents filed in region (WIPO)
* `culture_expenditure_per_capita_usd`: Cultural investment level
* `culture_expenditure_per_planetarium_usd`: Normalized cultural spending per planetarium

---

## 🔍 Key Finding

> “Countries with higher per capita investment in cultural heritage tend to have a higher density of planetariums.”

This supports a refined hypothesis that immersive infrastructure correlates more with **policy and cultural spending** than raw economic indicators.

---

## 🌐 License

This dataset is released under the Open Data Commons Open Database License (ODbL) 1.0 and CC BY 4.0 for derivative works.

* Attribution: **Softmachine Immersive Productions / SIP Mechanic Public**
* Website: [https://softmachine.de](https://softmachine.de)
* GitHub: [https://github.com/SoftmachineImmersive](https://github.com/SoftmachineImmersive)

---

## ✨ Next Steps

* Match with museum and library datasets (ICOM, OSM)
* Expand to XR/dome/mixed immersive infrastructures
* Explore national policies on science communication
* Use WHED or UNESCO UIS for university & research center counts

---

*Last updated: October 2025*

📅 Curated by: Softmachine Immersive Productions / SIP Mechanic Public

🔙 [Back to dataset folder ↗](https://github.com/SoftmachineImmersive/immersive-data-hub/tree/main/datasets/osm-planetariums)
