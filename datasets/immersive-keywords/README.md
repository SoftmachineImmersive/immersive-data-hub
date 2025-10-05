# Immersive Keywords Dataset

This dataset tracks the daily evolution of key terms related to immersive media in online news from 2008 to 2025. It is published as part of the SIP (Sustainable Immersive Practices) initiative by [Softmachine Immersive](https://softmachine.de), a creative studio for immersive content, fulldome media, and data-informed cultural strategy.

---

## 📁 Contents

The dataset provides normalized daily term frequencies for keywords such as:

- *fulldome*  
- *immersive*  
- *immersive experience*  
- *immersive storytelling*  
- *immersive content*  
- *immersive learning*  
- *immersive education*  
- *immersive training*  
- *immersive architecture*  
- *immersive marketing*  
- *virtual reality*  
- *VR*  
- *augmented reality*  
- *artificial intelligence*  
- *television*  
- *dog* (control keyword for normalization behavior testing)

The CSV file [`master_keywords_extended.csv`](https://github.com/SoftmachineImmersive/immersive-data-hub/blob/main/datasets/immersive-keywords/master_keywords_extended.csv) contains daily and yearly normalized metrics for these terms, allowing long-term media trend analysis and inter-term comparison.

---

## 🧪 Methodology

### Source

Data was collected using [MediaCloud.org](https://mediacloud.org), an open-source platform developed by the MIT Center for Civic Media and the Berkman Klein Center at Harvard.  
It aggregates articles from over 1,600 English-language online news sources.

- **Source collection used:** *Online News – Global English Sources*  
- **Time period:** 2008-01-01 → 2025-10-02  
- **Data granularity:** Daily  

---

### Metrics per keyword (per day)

| Column | Description |
|--------|-------------|
| `KEYWORD_count` | Number of articles mentioning the keyword that day |
| `KEYWORD_total_count` | Total number of articles published that day |
| `KEYWORD_ratio` | Relative share (mentions ÷ total articles) |
| `KEYWORD_normalized` | Ratio × 100 → mentions per 100 articles |

---

### Normalization

Because the total article volume in MediaCloud grows steadily over time, raw counts are incomparable across years.  
To remove that bias, each day’s keyword mentions are divided by the day’s total article count and multiplied by 100, producing the normalized metric:

\[
\text{normalized} = \frac{\text{count}}{\text{total\_count}} \times 100
\]

This expresses **mentions per 100 articles** and allows time-series comparison independent of global media volume.

---

### Annual Aggregation

For readability, daily data were averaged to yearly values:

\[
\text{yearly\_normalized} = \frac{\sum_{d=1}^{365} \text{normalized}_d}{N_d}
\]

where \(N_d\) is the number of publication days per year.  
This step reduces noise and reveals long-term trends.

---

## 📊 Interpretation

- **Immersive** and **immersive experience** show strong exponential growth from 2016 onward — paralleling the commercial rise of VR / AR ecosystems.  
- **Virtual reality (VR)** peaked earlier, around 2017–2018, indicating the initial hype phase, while **augmented reality** shows steadier long-term growth.  
- **Fulldome** remains a niche keyword with minor fluctuations, reflecting specialized professional discourse.  
- **Immersive storytelling**, **content**, and **learning** exhibit synchronous upward trends — highlighting their increasing relevance across media and education.  
- **Immersive marketing** and **training** emerge later (post-2020) and display rapid relative growth, signaling expanding corporate adoption.  
- **Immersive architecture** appears sporadically but shows a consistent uptick after 2021, aligned with experiential space design trends.  
- **Artificial intelligence** dominates overall, with exponential growth since 2022, reflecting its ubiquitous integration across topics.  
- Control keywords confirm normalization integrity:  
  - *Dog* remains statistically stable (≈ 1 mention per 100 articles).  
  - *Television* steadily declines, demonstrating semantic displacement through digitalization.

---

## 🔍 File structure

- **File name:** `master_keywords_extended.csv`  
- **Rows:** Daily or yearly (depending on subset)  
- **Columns per keyword:**  
  - `keyword_count`  
  - `keyword_total_count`  
  - `keyword_ratio`  
  - `keyword_normalized`  

---

## 🔖 License & Citation

This dataset is published under **Creative Commons Attribution 4.0 International (CC BY 4.0)**.  

> **Citation:**  
> Softmachine Immersive (2025): *Immersive Keywords Dataset – MediaCloud Trend Tracking (2008 – 2025).*  
> GitHub: https://github.com/SoftmachineImmersive/immersive-data-hub  
> Website: https://softmachine.de/

---

## 📬 Contact

For collaborations or dataset extensions:

- ✉️ mail@softmachine.de  
- 🌐 https://softmachine.de  
- 💼 https://github.com/SoftmachineImmersive  
