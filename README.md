# Where Does Taiwan's Food Waste Go?
A data review of the system behind Baked Tipsy, 2015–2024

## Why this project
From 2021 to 2025 I ran Baked Tipsy, a small venture that brewed beer from surplus bread. This project asks what the national data says about the system that venture worked inside: how much of Taiwan's household food waste is actually recovered, where it goes, and how that has changed.

## Research question and hypotheses
How has Taiwan's household food waste recovery changed from 2015 to 2024, and what does that mean for small upcycling ventures?

1. Recovery is shrinking as a share of total waste.
2. The lost pig-feed outlet was not replaced by other recovery routes.
3. Recovery varies widely between counties.

## Key findings
- **2024 snapshot:** 12.35 million tonnes of general waste were generated. Only 505,302 t (about 4.1%) was recovered as food waste: 231,369 t compost, 216,361 t pig feed and 57,572 t other uses.
- **Pig feed collapsed:** it fell from 408,524 t (2015) to 237,849 t (2019), down 42%. Over the same period compost grew by only 49,260 t and overtook pig feed in 2019.
- **The recovery rate halved:** 8.37% in 2015 versus 4.09% in 2024. The decline isn't continuous, since 2024 is up from 2023.
- **Counties differ a lot:** in 2024 Lienchiang recovered 57.0 kg per person and Keelung 8.9 kg. On the main island only, Tainan's 31.9 kg is about 3.6 times Keelung's.

**Conclusion:** single-product upcycling like Baked Tipsy can prove that an idea works, but it can't close system-level gaps of this size.

## Data sources
- MOENV open data: [STAT_P_150, national waste account](https://data.moenv.gov.tw/dataset/detail/STAT_P_150), [STAT_P_45, annual waste by county](https://data.moenv.gov.tw/dataset/detail/STAT_P_45), [STAT_P_127, monthly waste by county](https://data.moenv.gov.tw/dataset/detail/STAT_P_127)
- Population: Ministry of the Interior, Department of Household Registration, year-end county population ([download page](https://www.ris.gov.tw/info-popudata/app/awFastDownload/toMain_panel)), compiled into `population_by_county.csv`
- Policy context: [MOENV notice on food waste pig feed after African swine fever](https://enews.moenv.gov.tw/moenv-news/zh-tw/News/13385)

## Methods
Python (pandas, plotly) in Google Colab. I converted ROC years to AD (+1911), parsed the mixed annual and monthly rows, reshaped the data from wide to long, merged in county population, and computed food waste recovered per person.

## Limitations
- The data covers the household and municipal stream only. Business and industrial food waste, and pre-consumer food loss such as surplus bread from bakeries, are not included.
- No emissions figures are estimated.
- Total waste generated jumps between 2017 and 2018. This may reflect a definitional change that I have not verified.
- The 2019 pig-feed rules are context only. This analysis does not show they caused the decline.
- Outlying islands such as Lienchiang have high per-person numbers partly because of visitors.
- Baked Tipsy batch figures in the report are my own estimates, not dataset values.

## Files
- `Food_Waste_Analysis.ipynb`: the full analysis
- `report_draft.docx`: the written report
- `newplot.png` (Sankey 2024), `newplot-2.png` (destinations trend), `newplot-3.png` (recovery rate), `newplot-4.png` (county per capita): figures
- `stat_p_150.csv`, `stat_p_45.csv`, `stat_p_127.csv`, `stat_p_36.csv`, `population_by_county.csv`: data

## How to run
Open the notebook in Google Colab, put the CSVs in a Drive folder, update the data path in the first cell, then choose Runtime → Run all.

Author: Holly Liou
