# Immersive Keywords Dataset

The *Immersive Keywords* dataset tracks how terms related to immersive media appear in global online news.  
It provides a longitudinal view of how cultural, technological and experiential concepts rise or decline in public discourse.

The dataset is curated by **Martin Sambauer** (https://martin-sambauer.com)  
and published by **Softmachine** (https://softmachine.de) as part of the immersive-data-hub.

---

## Contents

This dataset contains:

- **master_keywords_extended.csv**  
  Daily keyword frequencies including total article counts and normalized rates.

- **master_keywords_yearly.csv**  
  Yearly aggregated frequencies with long-term trend indicators.

- **methodology.md**  
  Complete documentation of data sources, extraction logic, normalization workflow, quality checks and limitations.  
  → https://github.com/SoftmachineImmersive/immersive-data-hub/blob/main/datasets/immersive-keywords/methodology.md

- **schema.json**  
  A JSON Schema defining field names, types and structural rules for both CSV files.  
  → https://github.com/SoftmachineImmersive/immersive-data-hub/blob/main/datasets/immersive-keywords/schema.json

- **Articles with insights**  
  Analytical interpretation, visualisations and narrative context based on this dataset:  
  → Immersive Keywords – https://martin-sambauer.com/immersive-keywords/  
  → Origins of Wonder – An Immersive Impact Investment – https://martin-sambauer.com/origins-of-wonder-an-immersive-impact-investment/

---

## Purpose

This dataset provides a quantitative foundation for understanding how immersive media enters cultural consciousness.  
It enables researchers, creatives and strategists to track the diffusion of immersive terminology across time and to compare immersive concepts against each other or against baseline control keywords.

Use cases include:

- longitudinal trend analysis  
- cultural diffusion and adoption research  
- comparison of emerging vs. mature immersive concepts  
- input for whitepapers, market reports, strategic documents  
- qualitative–quantitative hybrid research  
- evidence base for essays and impact-investment narratives on immersive media (as in the example articles linked above)

---

## Key Results (condensed)

- **Global relevance of immersive media has risen sharply**, with several immersive terms showing multi-year upward trajectories in news frequency.  
- **“Immersive experience” and “immersive storytelling” exhibit the strongest sustained growth**, indicating that immersive media moves from a purely technical framing towards culture, communication and experience design.  
- **VR and AR show slower, more volatile patterns**, suggesting that public discourse gradually shifts from hardware-centric narratives towards broader experiential frameworks.  
- **Control keywords confirm data stability:**  
  - The baseline media term **“television”** shows a clear decline over time, consistent with the long-term erosion of its cultural centrality.  
  - The dataset successfully identifies the dog **“Uggie”** (famous from the film *The Artist*) as a distinct entity in the reference set, demonstrating that specific named entities can be tracked and recognised reliably across the corpus.  
- Overall, the dataset points to a **structural cultural shift from technical terminology to narrative-experiential framing**, marking immersive media as a long-term societal theme rather than a short-cycle tech trend.

Further interpretation and concrete narrative use of these results can be found in:

- https://martin-sambauer.com/immersive-keywords/  
- https://martin-sambauer.com/origins-of-wonder-an-immersive-impact-investment/

---

## Source Principles

- Global online news data retrieved through the MediaCloud API.  
- Keywords selected based on relevance to immersive media, spatial storytelling, and experiential technologies.  
- Counts normalized relative to total daily article volume to ensure comparability.  
- Control keywords included for baseline calibration and sanity checks.  
- Data cleaning and aggregation documented in methodology.md.

---

## Licensing

The dataset is released under **Creative Commons Attribution 4.0 International (CC BY 4.0)**.

Required attribution:

**Softmachine** (softmachine.de) – Publisher  
**Curated by Martin Sambauer** (martin-sambauer.com)

For additional conditions regarding textual fields and reuse, see methodology.md.

---

## Explore and licensing

Explore. repository folder · CSV datasets · article with insights  
Licensing. CC BY 4.0 · © Softmachine · softmachine.de
