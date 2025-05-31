# MIMIC-Foresight

First machine learning project using real-world ICU data to predict patient mortality using MIMIC-IV.

## Overview

This project was developed during my studies at Bern University of Applied Sciences and marks my first venture into machine learning and medical data science. I built and compared two predictive models to estimate in-hospital mortality:

- Random Forest Classifier trained on structured ICU data (>1,000 features)
- DistilBERT trained on medical text (ICD codes & DRG descriptions)

Dataset: MIMIC-IV (https://physionet.org/content/mimiciv/3.1/)

## Technologies Used

- Python (pandas, scikit-learn, nltk, PyTorch)
- Hugging Face Transformers (distilbert-base-uncased)
- Jupyter Notebooks
- Feature engineering: Ordinal, One-hot, Binary encoding
- NLP: Lemmatization, tokenization, stop word removal

## Notebooks

| File                          | Description                             |
|------------------------------|-----------------------------------------|
| preproc_feature_eng_rf.ipynb | Feature engineering for Random Forest   |
| RF.ipynb                     | Random Forest model development         |
| data_extraction_bert.ipynb   | ICD/DRG text aggregation for BERT       |
| train_bert.ipynb             | DistilBERT training and evaluation   |

## Results

Random Forest:
- Precision: 82–87%
- Important features: Palliative and DNR ICD codes, DRG mortality, insurance type

DistilBERT:
- Accuracy: 55%
- Limitations: Low context length, poor text normalization, class imbalance, short training time

## Discussion and Limitations

- Random Forest performed better due to richer structured data.
- BERT was limited by the quality, length of training and length of input text.
- Mortality labels include up to one year post-discharge, which may bias results.
- Balancing the dataset and handling missing values were significant preprocessing steps.

## Outlook

This proof of concept could be extended into a clinical decision support tool.

Future integration: CDS Hooks.
- Hook: patient-view
- Suggestion card example: "High predicted mortality. Consider palliative care discussion."
- Next Steps: Build a pipeline for MIMIC-IV on FHIR. Perfect use case for CDS Hooks. This concept is further explored in Renner Cs BSc Thesis. 

## Notes

- This was my first machine learning project. The code is not yet fully optimized or streamlined.
- Since then, I gained further experience in ML and Python during my internships. My skills have significantly improved.
- A reference from the internship can be provided upon request.

## Author

Constantin Renner
