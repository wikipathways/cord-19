# Pathways in CORD-19
Pathway knowledge extracted from CORD-19 dataset for the fight against COVID-19

*Link to interactive shiny app for dataset exploration: https://gladstone-bioinformatics.shinyapps.io/shiny-covidpathways/*

Important Note: This site is to develop knowledge resources and tools to help tackle the COVID-19 outbreak. **It is NOT a guide to public information.** The content presented here has **NOT** been filtered or reviewed.

## COVID-19 Open Research Dataset (CORD-19)
https://pages.semanticscholar.org/coronavirus-research

"In response to the COVID-19 pandemic, the Allen Institute for AI has partnered with leading research groups to prepare and distribute the COVID-19 Open Research Dataset (CORD-19), a free resource of over 29,000 scholarly articles, including over 13,000 with full text, about COVID-19 and the coronavirus family of viruses for use by the global research community."

The PMC set of articles is based on [this query](https://www.ncbi.nlm.nih.gov/pmc/?term=%22COVID-19%22+OR+Coronavirus+OR+%22Corona+virus%22+OR+%222019-nCoV%22+OR+%22SARS-CoV%22+OR+%22MERS-CoV%22+OR+%E2%80%9CSevere+Acute+Respiratory+Syndrome%E2%80%9D+OR+%E2%80%9CMiddle+East+Respiratory+Syndrome%E2%80%9D).

***In total there are 9996 unique PMCIDs in CORD-19 collection (based on a filtering of the [metedata file](https://ai2-semanticscholar-cord-19.s3-us-west-2.amazonaws.com/2020-03-13/all_sources_metadata_2020-03-13.csv))***

## Pathway Figure OCR (PFOCR)
Independently, the [WikiPathways team](https://www.wikipathways.org/index.php/WikiPathways:Team), led by the [Pico group](https://profiles.ucsf.edu/alex.pico) at Gladstone has mined pathway figures at PMC from over the past 25 years (1995-2019) using a combination of image queries and machine learning, arriving at a set of 64,643 pathway figure images published and indexed by PMC. Pausing the publication of this work, we are investigating the intersection of our project and datasets in hand with the CORD-19 dataset.

***Of the 9996 PMC papers in CORD-19, 189 papers contain a total of 221 pathway figures.***

We then developed an entity recognition pipeline tailored for human gene mentions commonly found in pathway figures. This pipeline involves optical character recognition (OCR) followed by a series of normalizations and tranformations applied to the OCR output while matching against a custom lexicon of human gene symbols. *In addition to the genes we've recognized (as described below) we still have the [raw OCR output as a JSON](cord19_raw_ocr.json) that may be of interest to the NLP community. We have collected the figure titles and captions associated with this set as well.*

***Of the 221 pathway figures, we could identify one or more genes from 216 of them among 184 PMC papers.***

***These 216 pathway figures contain a total of 4818 gene mentions mapping to 1523 unique gene identifiers (NCBI Gene Entrez IDs).***

See our [notebook](https://wikipathways.github.io/cord-19/covid_figure_ocr_ner.nb.html) for more details.

Visit our [interactive shiny app](https://gladstone-bioinformatics.shinyapps.io/shiny-covidpathways/) to explore the dataset yourself.

---
Numbers last updated March 17, 2020

This work is funded by [NIH/NIGMS](https://www.nigms.nih.gov/) R01-GM100039.
