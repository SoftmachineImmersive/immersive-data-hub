# Immersive Keywords Dataset

This dataset tracks the yearly evolution of key terms related to immersive media in online news from 2008 to 2025.  
It is part of the SIP (Sustainable Immersive Practices) initiative by [Softmachine Immersive](https://softmachine.de),  
a creative studio for immersive content, fulldome media, and data-informed cultural strategy.

---

## 📁 Contents

The dataset provides normalized yearly term frequencies for keywords such as:

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
- *dog* (control keyword for normalization validation)

📄 **Dataset file:**  
[`master_keywords_yearly_(1).csv`](https://github.com/SoftmachineImmersive/immersive-data-hub/blob/main/datasets/immersive-keywords/master_keywords_yearly_(1).csv)

---

## 🧪 Methodology

### Source

Data was collected via [MediaCloud.org](https://mediacloud.org),  
an open-source research platform by the MIT Center for Civic Media and the Berkman Klein Center at Harvard.  
It aggregates over 1,600 English-language online news sources.

- **Collection:** *Online News – Global English Sources*  
- **Period:** 2008-01-01 → 2025-10-02  
- **Granularity:** Daily data, averaged to yearly values for trend clarity  

---

### Metrics per keyword

| Column | Description |
|--------|-------------|
| `KEYWORD_count` | Articles mentioning the keyword |
| `KEYWORD_total_count` | Total articles published that day |
| `KEYWORD_ratio` | Relative frequency (mentions ÷ total articles) |
| `KEYWORD_normalized` | Mentions per 100 articles |

---

### Normalization

Because the overall article volume in MediaCloud has increased over time,  
raw counts are not directly comparable across years.  
To remove that bias, we use the following normalization:

\[
\text{normalized} = \frac{\text{count}}{\text{total\_count}} \times 100
\]

This produces **mentions per 100 articles**, a unit-independent frequency measure.

---

### Yearly Aggregation

To visualize long-term evolution, daily normalized values were averaged per year:

\[
\text{yearly\_normalized} = \frac{\sum_{d=1}^{N} \text{normalized}_d}{N}
\]

This reduces noise and reveals structural trends in media attention.

---

## 📊 Interpretation

- **Immersive** and **immersive experience** exhibit steep growth since 2016,  
  paralleling the commercialization of VR/AR ecosystems.  
- **Virtual reality (VR)** peaked in 2017–2018, consistent with early hype cycles.  
- **Augmented reality** shows steadier long-term adoption.  
- **Fulldome** remains niche, marking its role in specialized cultural and scientific contexts.  
- **Immersive storytelling**, **content**, and **learning** indicate  
  rising integration of immersive concepts in communication and education.  
- **Immersive marketing** and **training** have grown rapidly since 2020,  
  signaling expanding corporate engagement with immersive technologies.  
- **Immersive architecture** gained traction post-2021,  
  reflecting the rise of experiential design and spatial branding.  
- **Artificial intelligence** shows exponential growth after 2022,  
  dominating the discourse across nearly all sectors.  
- Control terms confirm data integrity:  
  - *Dog* remains statistically flat (≈ 1–2 mentions per 100 articles).  
  - *Television* declines steadily, mirroring the media shift toward digital platforms.

---

## 🔍 File structure

- **File:** `master_keywords_yearly_(1).csv`  
- **Rows:** One per year (2008–2025)  
- **Columns:** For each keyword:  
  - `_count`, `_total_count`, `_ratio`, `_normalized`  

---

## 🔖 License & Citation

**License:** Creative Commons Attribution 4.0 International (CC BY 4.0)

> **Citation:**  
> Softmachine Immersive (2025): *Immersive Keywords Dataset – MediaCloud Trend Tracking (2008–2025).*  
> GitHub: [Softmachine Immersive Data Hub](https://github.com/SoftmachineImmersive/immersive-data-hub)  
> Website: [softmachine.de](https://softmachine.de)

---

## 📬 Contact

For collaborations or dataset extensions:

- ✉️ mail@softmachine.de  
- 🌐 https://softmachine.de  
- 💼 https://github.com/SoftmachineImmersive
