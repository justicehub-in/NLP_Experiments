# Studying the implementation of POCSO law
In this experiment, we explored the use of [OpenNyAI](https://opennyai.org/) in extracting relevant POCSO Sections from judgement copies and how it can enrich the existing metadata available on [eCourts](https://ecourts.gov.in/ecourts_home/) portal. 

## Directory Tree:
1. [PDF_Txt_Conversion](https://github.com/CivicDataLab/NLP_Justice/blob/main/POCSO/PDF_Txt_Conversion.ipynb): Codebook to convert PDFs into TXT format. 
2. [POCSO_filter](https://github.com/CivicDataLab/NLP_Justice/blob/main/POCSO/Filtering_POCSO_Cases.ipynb): Codebook that details how 51 POCSO judgments were filtered from the 1764 POCSO judgments available in Assam.
3. [OpenNyAI_Summarize](https://github.com/CivicDataLab/NLP_Justice/blob/main/POCSO/OpenNyAI_Summarize.ipynb): Codebook that summarises judgment texts using OpenNyAI's Extractive Summariser.  
4. [pocso_analysis_datasets_1221](https://github.com/CivicDataLab/NLP_Justice/tree/main/POCSO/pocso_analysis_datasets_1221): Directory containing datasets created by the JusticeHub on analysing POCSO cases in Assam. Datasource: [Link](https://justicehub.in/dataset/data4justice-unpacking-judicial-data-to-track-implementation-of-the-pocso-act-in-assam-delhi-haryana)
5. [Results](https://github.com/CivicDataLab/NLP_Justice/tree/main/POCSO/Results): This directory contains all results generated during the experiment. 

The 51 judgments used in the experiment are not shared here for privacy concerns. They can be made available on request. Please send an email to info@justicehub.in

## How to run this experiment?

1. **Step 1:** Convert PDFs of the judgments into TXT format. OpenNyAI's NLP Models take TXT as inputs. This codebook has details on doing this conversion: [PDF_Txt_Conversion](https://github.com/CivicDataLab/NLP_Justice/blob/main/POCSO/PDF_Txt_Conversion.ipynb)
2. **Step 2:** Select a sample space of judgments to perform the experiment. We selected 51 POCSO judgments from 1764 judgments delivered. eCourts does not have a judgment PDF for all of it - so took only those judgments that have a PDF on eCourts. Details of this filtering process is in this codebook - [POCSO_filter](https://github.com/CivicDataLab/NLP_Justice/blob/main/POCSO/Filtering_POCSO_Cases.ipynb)
3. **Step 3:** Summarise the 51 selected POCSO judgments using OpenNyAI's Extractive Summariser. This will create 5 types of summaries for each judgment.
    - Preamble Summary
    - Facts Summary
    - Issue Summary
    - Analysis Summary
    - Decision Summary
    All these 5 types of summaries for a judgment are saved in the form of a JSON.
4. **Step-4:** From the judgment summaries, identify POCSO Sections from the `Preamble` and `decision` summaries. These are defined as the `Relevant POCSO Sections` for a given case. Pattern matching is used to identify the POCSO Sections. 
5. **Step-5**: A dataset is created comparing the POCSO Sections identified from the above step with the POCSO Sections identified in the metadata on eCourts. Link to the final dataset -  [pocso_provisions_51judgements.csv](https://github.com/CivicDataLab/NLP_Justice/blob/main/POCSO/Results/pocso_provisions_51judgements.csv)

Codes to implement Steps 3,4,5 are in this codebook - [OpenNyAI_Summarize](https://github.com/CivicDataLab/NLP_Justice/blob/main/POCSO/OpenNyAI_Summarize.ipynb)

The inferences are shared in this blog: [Link](https://medium.com/civicdatalab/exploring-the-capabilities-of-natural-language-processing-nlp-in-conducting-legal-analysis-88ef2b9dec9c)

The experiment was presented at a [HydPy](https://www.hydpy.org/) meetup. You can access the talk here:[Video](https://www.youtube.com/watch?v=xSibto2cLoA) and the slides used for the talk here: [Google Slides](https://www.youtube.com/watch?v=xSibto2cLoA)

## License
All content in this repository is licensed under
[![CC-BY-SA](https://www.gnu.org/graphics/agplv3-155x51.png)](LICENSE.md)
