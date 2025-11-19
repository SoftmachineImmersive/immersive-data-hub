## Immersive Keywords Dataset – Methodology

### 1. Overview  
The Immersive Keywords dataset tracks the occurrence of key immersive-media terms in global online news between 2008 and 2025. It is designed to show how adoption and discourse around immersive formats, technologies and narratives evolve over time.

Version: 1.0.0  
Last updated: 2025-11-19  
Maintainer: Martin Sambauer (martin-sambauer.com)

### 2. Source materials  
- News article metadata and counts from MediaCloud (MIT & Harvard) covering global media. :contentReference[oaicite:1]{index=1}  
- A defined list of immersive keywords (e.g., “fulldome”, “immersive experience”, “immersive storytelling”, “virtual reality”, “augmented reality”). :contentReference[oaicite:2]{index=2}  
- Control keywords (e.g., “television”, “dog”) used for normalization checks. :contentReference[oaicite:3]{index=3}

### 3. Inclusion criteria and scope  
- Keywords selected based on relevance to immersive media, location-based experiences, and cultural/technological adoption.  
- News articles counted when they contain keyword mentions in title or body (depending on MediaCloud feed).  
- The dataset covers global online news, aggregated by year and (in some files) by day.  
- Time span: 2008 – 2025 (data may end earlier depending on coverage).  
- Normalisation: counts expressed as mentions per 100 articles to allow comparison over time and across keywords.

### 4. Data model  
The dataset files include two main forms:  
- A daily/raw dataset with keyword counts per day.  
- A yearly aggregated dataset with keyword-year combinations.  
Each row typically includes:  
- keyword  
- date (day or year)  
- count_mentions  
- count_articles (denominator)  
- normalized_rate (mentions per unit)  
- optional region or language filter (if available)  
Full field definitions are captured in the accompanying schema.json.

### 5. Data collection and processing workflow  
#### 5.1 Extraction  
- Use MediaCloud API to query counts of articles per keyword per time unit.  
- For each keyword, retrieve daily (or weekly) counts, and total article volume for that day.  
- Collect control keyword counts for quality check.

#### 5.2 Cleaning & normalization  
- Remove days with extremely low article volume or gaps.  
- Compute normalized rate = (mentions / article_count) × 100 (or other unit) for comparability.  
- Aggregate daily data to yearly totals for the yearly dataset.

#### 5.3 Quality checks  
- Confirm control keywords show stable or expected trends (e.g., “television” declining).  
- Check for sudden spikes or anomalies (e.g., multiple keywords peaking on same day) and flag for manual review.  
- Validate that each keyword has coverage across a minimum threshold of time units.

### 6. Limitations & biases  
- The dataset reflects online news coverage, not total public discourse; media bias exists (language, region, topic).  
- Keywords may appear in multiple contexts (marketing, culture, education), so interpretation must be cautious.  
- Normalisation assumes article count is comparable across time; changes in news volume or coverage can affect rates.  
- Some emerging keywords may have low counts early on, making trend lines volatile.

### 7. Updates & contributions  
- Contributors may suggest additional keywords or time spans via pull requests.  
- When adding keywords, include definition, example usage, and anticipated coverage.  
- Data refreshes planned on an annual basis.

### 8. Licensing & attribution  
The dataset is released under **CC BY 4.0**.  
Attribution: Softmachine (softmachine.de) – Publisher  
Curated by Martin Sambauer (martin-sambauer.com)

Explore. repository folder · CSV dataset · article with insights  
Licensing. CC BY 4.0 · © Softmachine · softmachine.de
