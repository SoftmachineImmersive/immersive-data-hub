# Immersive Keywords Dataset

This dataset tracks the yearly and daily evolution of key terms related to immersive media in online news from 2008 to 2025.
It is published as part of the SIP (Sustainable Immersive Practices) initiative by [Softmachine Immersive](https://softmachine.de),
a creative studio for immersive content, fulldome media, and data-informed cultural strategy.

---

## 🗁 Contents

The dataset provides normalized term frequencies for keywords such as:

* *fulldome*
* *immersive*
* *immersive experience*
* *immersive storytelling*
* *immersive content*
* *immersive learning*
* *immersive education*
* *immersive training*
* *immersive architecture*
* *immersive marketing*
* *virtual reality*
* *VR*
* *augmented reality*
* *artificial intelligence*
* *television*
* *dog* (control keyword for normalization validation)

### Available files

* **Raw daily dataset:** [`master_keywords_extended.csv`](https://github.com/SoftmachineImmersive/immersive-data-hub/blob/main/datasets/immersive-keywords/master_keywords_extended.csv)
  → contains daily mention counts, totals, ratios, and normalized frequencies (mentions per 100 articles).

* **Yearly aggregated dataset:** [`master_keywords_yearly_(1).csv`](https://github.com/SoftmachineImmersive/immersive-data-hub/blob/main/datasets/immersive-keywords/master_keywords_yearly_%281%29.csv)
  → contains averaged yearly values for long-term media trend visualization.

---

## 🧪 Methodology

### Source

Data was collected using [MediaCloud.org](https://mediacloud.org),
an open-source research platform developed by the MIT Center for Civic Media and the Berkman Klein Center at Harvard.
It aggregates content from over 1,600 English-language online news sources.

* **Collection:** *Online News – Global English Sources*
* **Period:** 2008-01-01 → 2025-10-02
* **Granularity:** Daily (aggregated to yearly averages)

---

### Metrics per keyword

| Column                | Description                                 |
| --------------------- | ------------------------------------------- |
| `KEYWORD_count`       | Number of articles mentioning the keyword   |
| `KEYWORD_total_count` | Total number of articles published that day |
| `KEYWORD_ratio`       | Relative share (mentions ÷ total articles)  |
| `KEYWORD_normalized`  | Mentions per 100 articles                   |

---

### Normalization

Since the total article volume in MediaCloud expands over time, raw counts are not directly comparable across years.
To correct for this bias, we normalize using:

[
\text{normalized} = \frac{\text{count}}{\text{total_count}} \times 100
]

This produces a **mentions per 100 articles** metric, ensuring comparability across time periods.

---

### Yearly Aggregation

To reduce noise and reveal long-term dynamics, normalized daily values were averaged by year:

[
\text{yearly_normalized} = \frac{\sum_{d=1}^{N} \text{normalized}_d}{N}
]

---

## 📊 Interpretation

* **Immersive** and **immersive experience** show exponential growth after 2016,
  paralleling the rise of VR/AR ecosystems and corporate interest in experiential technologies.
* **Virtual reality (VR)** peaked in 2017–2018, while **augmented reality** demonstrates steadier growth.
* **Fulldome** remains a niche indicator for professional and cultural use.
* **Immersive storytelling**, **content**, and **learning** reveal increasing relevance in communication, culture, and education.
* **Immersive marketing** and **training** emerge strongly after 2020, signaling business adoption.
* **Immersive architecture** shows continuous growth since 2021, linked to spatial and experiential design.
* **Artificial intelligence** accelerates sharply post-2022, dominating media attention.
* **Television** shows a **dramatic decline**, reflecting the structural transition from broadcast to digital media.
  It was used as a *control term* to verify the dataset’s alignment with observable real-world developments.
* **Dog** remained stable at roughly 1–2 mentions per 100 articles and served as a second control keyword to verify normalization stability.

---

## 🔍 File structure

| File                                                                                                                                                                    | Description                                                 |
| ----------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ----------------------------------------------------------- |
| [`master_keywords_extended.csv`](https://github.com/SoftmachineImmersive/immersive-data-hub/blob/main/datasets/immersive-keywords/master_keywords_extended.csv)         | Daily mentions, total counts, ratios, and normalized values |
| [`master_keywords_yearly_(1).csv`](https://github.com/SoftmachineImmersive/immersive-data-hub/blob/main/datasets/immersive-keywords/master_keywords_yearly_%281%29.csv) | Yearly averages of normalized keyword mentions              |

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

* ✉️ [mail@softmachine.de](mailto:mail@softmachine.de)
* 🌐 [https://softmachine.de](https://softmachine.de)
* 💼 [https://github.com/SoftmachineImmersive](https://github.com/SoftmachineImmersive)
