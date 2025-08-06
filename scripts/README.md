# Indoor Microbiome Analysis: Swab & ddPCR Timepoint Comparisons

## 🧬 Overview

This repository contains R Markdown analyses of microbiome data collected via surface swabs in an unoccupied house. The primary goal is to assess microbial changes across **rooms**, **locations**, and **experimental timepoints** using both:

- **CFU per swab** from Petrifilm analysis (RYM)
- **UFT/m²** from ddPCR quantification

---

## 📂 File Descriptions

### 🔹 `room_ddpcr_kruskal.Rmd`
- Compares **ddPCR (UFT/m²)** values between rooms (`room_id`) for locations like `light_switch` and `behind_bedroom_door`.
- Performs **Kruskal-Wallis tests** to assess statistical differences.
- Filters out samples with known disturbances.

### 🔹 `room_rym_kruskal.Rmd`
- Same structure as above, but analyzes **RYM data** (CFU per swab).
- Also uses **Kruskal-Wallis tests** grouped by `location`.

### 🔹 `the_heatmap_figures.Rmd`
- Visualizes **pre- vs post-experiment** microbial loads via **heatmaps**:
  - One for CFU (`cfu_per_swab`)
  - One for ddPCR (`UFT_m²`)
- Groups data by `room_id` and `location`
- Saves heatmaps to:
  - `products/combined_rym_heatmap_plot.png`
  - `products/combined_ddpcr_heatmap_plot.png`

### 🔹 `timepoint_ddpcr_wilcox.Rmd`
- Performs a **paired Wilcoxon test** comparing **pre- and post- ddPCR values**.
- Visualizes results using `ggstatsplot::ggbetweenstats()` with grouping by room and location.

### 🔹 `timepoint_rym_wilcox.Rmd`
- Same as above, but applied to **CFU per swab (RYM)** data.
- Outputs include Wilcoxon test results and statistical plots.

---

## 📦 Key Libraries Used

- `tidyverse` – Data cleaning and plotting
- `broom` – Tidying test results
- `ggplot2`, `ggstatsplot` – Heatmaps, boxplots, and statistical graphics
- `stats` – Wilcoxon testing
- `gridExtra`, `grid` – Plot layout tools

---

## 🖼️ Outputs

- 🔬 **Heatmaps** for CFU and ddPCR by timepoint
- 📊 **Statistical plots** showing pre vs post comparisons by room/location
- 📈 **Kruskal-Wallis and Wilcoxon test results** assessing microbial variation

---

---

## 🧾 Citation

If you use this analysis or code in your research or publications, please cite:

> Noble Lab, PreMiER REU Project, 2025. GitHub Repository.

---

## 📬 Contact

Questions? Issues?  
Please open an [issue](https://github.com/Manogna111/Indoor_Microbiome_Analysis/issues) or contact the project maintainers directly.


