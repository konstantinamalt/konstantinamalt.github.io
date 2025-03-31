# Troubled Waters
## The multiple devastating impact of floods across Europe

Troubled Waters is a data-driven research project analyzing flood impact on different leveles across Europe over the past decade by combining satellite data from the Copernicus Emergency Management Service (EMS) with public datasets like Hanze and EM-DAT, revealing the most vulnerable regions and the urgent need for a unified EU disaster database.

## Publication links:
##### Scrolly
- English [here](https://miir.gr/longreads/flood-in-europe-en.html)
- Greek [here](https://miir.gr/longreads/flood-in-europe-gr.html)

##### Articles
- [EFSYN](https://www.efsyn.gr/themata/thema-tis-efsyn/467620_taragmena-nera-o-katastrofikos-antiktypos-ton-plimmyron-stin-eyropi) (GR)
- [MIIR](https://miir.gr/otan-vrechei-akoma-fovamai-oti-to-potami-tha-mas-ta-parei-ola/) (GR)
- [EL CONFIDENCIAL](https://www.elconfidencial.com/mundo/europa/2025-03-31/valencia-tesalia-baja-sajonia-comparan-peores-inundaciones-europa_4096524/) (ES)
- [CIVIO](https://civio.es/medio-ambiente/2025/03/31/la-dana-de-valencia-frente-a-las-grandes-inundaciones-europeas-de-los-ultimos-anos/) (ES)
- [PRESSONE](https://pressone.ro/investigatie-ape-tulburi-impactul-devastator-al-inundatiilor-in-europa]) (RO)

## Project identity and credits
Organised and coordinated by the Mediterranean Institute for Investigative Reporting (MIIR.gr) with the collaboration of the European Data Journalism Network ((EDJNet)[https://www.europeandatajournalism.eu/]).
- Data collection and analysis: Konstantina Maltepioti
- Fact-checking: Eva Lopez ([DW](https://www.dw.com/en/top-stories/s-9097]))
- Research: Kostas Zafeiropoulos (MIIR)
- Scrolly design: Krisztián Szabó (Atlatszo)
- Illustrations: Louisa Karageorgiou

The project was a collaboration of 6 EDJNet members: [MIIR]([https://miir.gr/) (Greece), [Atlatszo](https://atlatszo.hu/) (Hungary), [Facta](https://facta.eu/) (Italy), [El Confidencial](https://www.elconfidencial.com/), [Civio](https://civio.es/) (Spain), [PressOne](https://pressone.ro/) (Romania).

## Objectives
- Identify flood-prone regions in Europe, deaths and population affected over a decade (2014–2024)
- Analyse land, infrastructure, and population affected over the last two years (2023-2024)
- Normalize inconsistent data from multiple sources (Copernicus, Public EM-DAT, Hanze)
- Provide a methodology for Copernicus' satellite data that can be used for othe natural disasters

## Findings
- Over the past two years alone, 32 floods in 17 countries affected 427,336 hectares—an area 1.5 times the size of Luxembourg. Around 76.7% of this was agricultural land, raising long-term concerns for food security and farmer livelihoods.
- Analysis of 61 impacted regions (NUTS 3 level) reveals rural areas experienced the most extensive flooding, with approximately 138,663 affected hectares. In comparison, 98,447 hectares were affected in intermediate regions and 88,468 hectares in urban regions.
- Although rural areas experienced the largest flood extents, urban regions saw the highest damage to roads, pipelines, and communication networks.
- Valencia's flood in 2024 and Thessaly's flood in 2023 were Europe’s most destructive floods. The Valencia flood was the deadliest, affecting 190,090 people and killing 232. The Thessaly flood claimed 17 lives and affected 122,375 hectares, 92% of which was farmland. The flood ultimately contributed to 335 deaths when post-flood mortality is considered.
- In the last two years, floods have affected 4,256.20 km of transportation infrastructure (especially local roads) and 1,223.6 km of pipelines and communication infrastructure.
- Despite increasing flood frequency and severity, Europe still lacks a centralized, consistent database for flood impact. The analysis had to reconcile data from Copernicus, EM-DAT, and Hanze, each using different methodologies, limiting long-term comparisons and undermining disaster preparedness.

## Methodology Summary
- Searched for open-access European flood datasets with key indicators (extent, land type, population, infrastructure).
- Selected three main data sources: **Hanze**, **Public EM-DAT**, and **Copernicus EMS**.
- Collected detailed flood data from **Copernicus API** (2023–2024), using unique flood IDs from the "Activations" page.
- Matched Copernicus **AOIs** (Areas of Interest) to official **NUTS 3 regions** using Eurostat and manual search.
- Filtered overlapping AOIs to avoid double counting flooded areas and population.
- Measured flood extent by combining flooded areas and flood traces, excluding permanent water bodies.
- Normalized Copernicus data subcategories creating bigger categories to group data better.
- Excluded inconsistent fields (e.g. residential buildings reported in incompatible units).
- Merged Copernicus data with Hanze and EM-DAT to build a decade-long, region-level flood dataset.
- Created consistent fields across datasets such as: flood ID, date, country, region, typology, population, fatalities, sources.

👉 See **From Space to Spreadsheet: The Troubled Waters Methodology** [here](https://konstantinamalt.github.io/floods/)

### Data Challenges
##### 1. Fragmented & inconsistent data 
Flood data across Europe is fragmented, with no centralized standard. Key indicators, such as flood extent, fatalities, affected population, and infrastructure damage, are often missing, outdated, or reported inconsistently across datasets.
##### 2. Regional mismatch and language
Copernicus defines Areas of Interest (AOIs) that do not match official administrative regions. Manual searching and cross-reference with Eurostat’s NUTS 3 classification was required to enable regional comparisons and typologies. Public EM-DAT data also required manual search to adhere to Eurostat's classification of administrative regions. HANZE had the proper names and codes based on Eurostat's classification, but needed to be updated to match the classification of 2024. Language was also an issue, since Eurostat region names had to be translated in English.
##### 3. Overlapping observations  
In Copernicus multiple AOIs often overlap for a single flood event, with repeated observations recorded as separate products. Filtering was required to avoid double counting flood extent, affected land, infrastructure and populations.
##### 4. Inconsistent satellite reporting  
Copernicus summary tables often exclude "flood traces," underreporting the actual flooded area. Manual review of each AOI’s full statistics was necessary to accurately capture total flood extent.
##### 5. Unit inconsistencies  
Satelitte data for infrastructure and buildings were reported using inconsistent units (e.g. hectares vs. number or kilometers), sometimes even within the same flood. To ensure consistency, some categories, like residential buildings, were excluded from final analysis.
##### 6. Coverage gaps  
- **Hanze** and **EM-DAT** lacked any flood extent data. Affected population data were available but still sparse.
- **Hanze** stops recording floods in 2020.
- **EM-DAT** records sharply declined in 2022, raising concerns about underreporting.
- **Copernicus** only tracks floods requested by authorized users, and not all flood occurencies.
##### 7. Evolving API and Platforms  
During the project, Copernicus changed its web platform, removing visible access to its open API in newer pages. Though the API remains functional as of May 30 2025, data retrieval using this methogology may require adapting in the future.

## Collection and Analysis
#### Libraries Used
This analysis was conducted using the following Python libraries:
- **pandas** – for data cleaning, analysis, and merging across multiple datasets.
- **requests** – to retrieve data from the Copernicus API (in JSON format).
- **numpy** – for numerical operations and handling missing values.
- **re (regex)** – to clean and translate region names.

## Jupyter Notebooks
- **Scraping in two steps**: One notebook collects flood information and another collects statistics to better structure the code. These are later merged:
  - `1_scraping_copernicus_api.ipynb`
  - `2_merge_copernicus_data.ipynb`

- **Additional scraping** was done after discovering that the summary tables containing flood extents were incorrect:
  - `3_scraping_copernicus_data_WITH_FLOOD_EXTENTS_HA.ipynb`

- **Merging with Eurostat regions**: Clean scraped data is merged with Eurostat's regional file:
  - `4_merging_copernicus_with_regions_excels_eu_commission.ipynb`

- **Final dataset generation**: Verifies data integrity after Copernicus’ site change and creates the final Excel:
  - `5_FINAL_EXCEL_merging_new_scraped_copernicus_data_with_old_final_excel.ipynb`

- **Processing HANZE dataset**: Fixes and merges HANZE data with Eurostat regional codes:
  - `6_hanze_and_regions_merge.ipynb`

- **Category-based analysis of Copernicus data (2023–2024)**:
  - `copernicus_analysis_2024-2023_1_max_extent.ipynb`
  - `copernicus_analysis_2024-2023_2_land_use.ipynb`
  - `copernicus_analysis_2024-2023_3_transportation.ipynb`
  - `copernicus_analysis_2024-2023_4_infrastructure_pipelines_communication.ipynb`
  - `copernicus_analysis_2024-2023_5_population.ipynb`
  - `copernicus_analysis_2024-2023_6_Storm_Boris.ipynb`  
    (This one uses the same final Excel file, with storm names and fatalities manually added, based on GDACS or media sources.)

- **Creating the decade-long dataset**:
  - `8_decade_floods_dataset_all_sources.ipynb`

- **Decade-long analysis**:
  - `analysis_9_decade.ipynb`

- **Creating summary Excel files** with totals per flood, per country, and per NUTS region for the most important Copernicus categories:
  - `7_Sums of categories per flood, country and nuts regions in Copernicus.ipynb`

## Datasets
- Download raw Copernicus flood impact data (2023-2024) [here](https://github.com/konstantinamalt/floods_project/blob/main/CLEAN_FINAL_aois_all_details_nuts_translated.xlsx), filename: "CLEAN_FINAL_aois_all_details_nuts_translated.xlsx"
- Download final file with sums of categories per flood, country and nuts regions for Copernicus [here](https://github.com/konstantinamalt/floods_project/blob/main/Sums%20of%20categories%20per%20flood%2C%20country%20and%20nuts%20regions%20in%20Copernicus.xlsx)
- Download final Decade dataset from all three sources (2014-2023) [here](https://github.com/konstantinamalt/floods_project/blob/main/decade_final_dataset_copernicus_emdat_hanze.xlsx), filename: "decade_final_dataset_copernicus_emdat_hanze.xlsx"
- Hanze original data filename: HANZE_events.csv / Hanze final: final_hanze_dataset_2020_2014.xlsx
- Original public EM-DAT data shared by EEA filename: public_emdat_custom_request_2024-12-12_konna.xlsx / Public EM-DAT final: final_public_emdat_2022_2021
- Download Eurostat regional data 2021-2024 [here](https://github.com/konstantinamalt/floods_project/blob/main/NUTS2021-NUTS2024(1).xlsx) filename: "NUTS2021-NUTS2024(1).xlsx"

## License
The data analysis for this project is open for use.


