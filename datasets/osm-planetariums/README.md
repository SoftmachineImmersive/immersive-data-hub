> This dataset is part of the Immersive Data Hub maintained by [Softmachine Immersive Productions](https://softmachine.de/), a creative agency for immersive media, fulldome content, and data-driven strategy.

# 🌍 OSM Planetariums Dataset

This dataset contains geolocated information on over 800 planetariums worldwide, extracted and curated from OpenStreetMap (OSM) using custom spatial processing.

---

## 🧪 Methodological Note: Planetarium Data Extraction and Processing

### 1. Data Source  
The initial dataset was extracted from OpenStreetMap (OSM) using the Overpass API. We queried all nodes, ways, and relations tagged with `amenity=planetarium`, which yielded 888 entries worldwide. These entries included coordinates, names, and, when available, address fields like city or country.

### 2. Country Assignment  
Because many entries lacked country data, we matched lat/lon coordinates to country polygons from [Natural Earth](https://www.naturalearthdata.com/). We first tried 1:110m boundaries, but switched to 1:50m for better accuracy on islands and coasts (e.g., Okinawa, Azores, Shanghai). All 888 were successfully assigned to countries.

### 3. Data Cleaning  
- Empty names were replaced with `No-Name` placeholders.  
- Each entry was given a unique ID per country (e.g., `Germany 1`, `Germany 2`).  
- A direct Google Maps link was generated from coordinates for easy validation.  
- A few faulty/duplicate entries were removed (e.g., from Chile, Argentina, Germany).

### 4. Filtering  
OSM mixes planetariums and observatories. We removed all entries identified as observatories using multilingual keywords (e.g., `Observatory`, `Sternwarte`, `天文台`, `Обсерватория`, etc.). This resulted in ~830 verified planetarium entries.

### 5. Translation and Normalization  
- Non-Latin names (Chinese, Arabic, Cyrillic, Japanese) were translated to English.  
- Original names were retained in parentheses:
  - Example: 上海天文馆 → 上海天文馆 (Shanghai Planetarium)  
  - Example: مركز القبة السماوية → مركز القبة السماوية (Planetarium Center)

This makes the dataset both culturally authentic and globally accessible.

### 6. Completeness and Limitations  
- The final dataset includes **830 planetariums**.  
- Industry estimates suggest up to **4,000 fulldome theaters** globally, so this dataset may reflect only 20–25% of actual venues.  
- Still, this open dataset offers a structured and reproducible baseline for:
  - Global distribution analysis  
  - Country-level comparisons  
  - Merging with private databases and industry directories  

---

## 📜 License  
This dataset is released under the **Open Data Commons Open Database License (ODbL) 1.0**:  
[https://opendatacommons.org/licenses/odbl/1-0/](https://opendatacommons.org/licenses/odbl/1-0/)

You are free to use, share, and modify the data, provided that you:  
- Attribute [Softmachine Immersive Productions](https://softmachine.de/)  
- Share any derived datasets under the same license  
- Link to this license in your work  

---

## ✉️ Curation Contact  
[Softmachine Immersive Productions](https://softmachine.de/)  
Mail: [mail@softmachine.de](mailto:mail@softmachine.de)  
GitHub: [https://github.com/SoftmachineImmersive/](https://github.com/SoftmachineImmersive/)  
Website: [https://softmachine.de/](https://softmachine.de/)

---

## 📎 Related Resources  
- [OpenStreetMap Overpass API](https://overpass-turbo.eu/)  
- [Natural Earth](https://www.naturalearthdata.com/)  
- [Softmachine Immersive Productions](https://softmachine.de/)

