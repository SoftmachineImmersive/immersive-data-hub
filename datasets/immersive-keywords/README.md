# Immersive Keywords Dataset

This dataset tracks the daily evolution of key terms related to immersive media in online news from 2008 to 2025. It is published as part of the SIP (Sustainable Immersive Practices) initiative by [Softmachine Immersive](https://softmachine.de), a creative studio for immersive content, fulldome media, and data-informed cultural strategy.

---

## 📁 Contents

The dataset provides normalized daily term frequencies for keywords such as:

- *fulldome*
- *immersive content*
- *virtual reality*
- *immersive storytelling*
- *immersive learning*
- *immersive marketing*
- and others.

The CSV file `master_keywords_extended.csv` contains daily metrics for these terms, allowing for long-term media trend analysis and comparisons across terms.

---

## 🧪 Methodology

### Source

Data was collected using [MediaCloud.org](https://mediacloud.org), an open-source platform developed by the MIT Center for Civic Media and Berkman Klein Center at Harvard. It aggregates articles from over 1,600 English-language online news sources.

- **Source collection used:** *Online News – Global English Sources*
- **Time period:** 2008-01-01 to 2025-10-02
- **Data granularity:** Daily

---

### Metrics per keyword (per day)

For each keyword, four metrics are provided:

| Column | Description |
|--------|-------------|
| `KEYWORD_count` | Number of articles mentioning the keyword that day |
| `KEYWORD_total_count` | Total number of articles published that day |
| `KEYWORD_ratio` | Proportional frequency (mentions ÷ total articles) |
| `KEYWORD_normalized` | `KEYWORD_ratio` × 100, i.e. mentions per 100 articles |

---

### Normalization explained

Due to the growing size of the MediaCloud corpus over time, raw mention counts are not directly comparable across years. To allow meaningful comparison:

- We calculate the ratio:  
  \[
  \text{ratio} = \frac{\text{count}}{\text{total\_count}}
  \]

- To improve readability, we scale the ratio:  
  \[
  \text{normalized} = \text{ratio} \times 100
  \]  
  → This yields a metric expressing **mentions per 100 articles**, eliminating bias from varying publication volumes.

---

### Limitations

- Early years (2008–2012) may show volatile spikes due to low overall article volume.
- Keyword choices reflect curatorial intent and may not cover all variants.
- Data reflects media discourse, not necessarily real-world adoption or usage.

---

## 🔍 File structure

- **File name:** `master_keywords_extended.csv`
- **Rows:** One per day (2008–2025)
- **Columns:** For each keyword:
  - `keyword_count`
  - `keyword_total_count`
  - `keyword_ratio`
  - `keyword_normalized`

Total size: ~64,000 daily rows × ~20 columns (depending on term count)

---

## 🔖 License & Citation

This dataset is published under the **Creative Commons Attribution 4.0 International (CC BY 4.0)** license.

> Please cite as:  
> Softmachine Immersive (2025): *Immersive Keywords Dataset – MediaCloud Trend Tracking (2008–2025)*.  
> GitHub: https://github.com/SoftmachineImmersive/immersive-data-hub  
> Website: https://softmachine.de/

You are free to share and adapt this material for any purpose, including commercial use, as long as proper credit is given.

---

## 📬 Contact

For collaborations, questions, or dataset extensions:

- ✉️ mail@softmachine.de  
- 🌐 https://softmachine.de/  
- 💼 https://github.com/SoftmachineImmersive

---

