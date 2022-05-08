# Final Project - Reproducing Paper 211 - Improving clinical outcome predictions using convolution over medical entities with multimodal learning

This repository is an implementation of [Improving clinical outcome predictions using convolution over medical entities with multimodal learning](https://doi.org/10.1016/j.artmed.2021.102112). 

## Original Paper details

Batuhan Bardak, Mehmet Tan,
Improving clinical outcome predictions using convolution over medical entities with multimodal learning,
Artificial Intelligence in Medicine,
Volume 117,
2021,
102112,
ISSN 0933-3657,
https://doi.org/10.1016/j.artmed.2021.102112.
(https://www.sciencedirect.com/science/article/pii/S0933365721001056)
Keywords: Deep learning; Healthcare; EHR; NER; Multimodal

## Paper's original Repo

The code for the proposed method is available at https://github.com/tanlab/ConvolutionMedicalNer.

## Dependencies and Requirements

To install required packages and version on a conda based environment:

```setup
conda env create -f environment.yml
```

## Downloading and setting up data

Download the MIMIC-III dataset from [Physionet](https://mimic.physionet.org/)

Copy the `ADMISSIONS.csv`, `NOTEEVENTS.csv`, `ICUSTAYS.csv` files from MIMIC-III dataset into `data` folder.

Run MIMIC-Extract Pipeline as explained in https://github.com/MLforHealth/MIMIC_Extract or download the preprocessed extract file. Please note that this requires additional credentials approval from Physionet. 

Copy the output file of MIMIC-Extract Pipeline named `all_hourly_data.h5` to `data` folder.

## Preprocess data

Run `01-Extract-Timseries-Features.ipnyb` to extract first 24 hours timeseries features from MIMIC-Extract raw data.

Run `02-Select-SubClinicalNotes.ipynb` to select subnotes based on criteria from all MIMIC-III Notes.

Run `03-Prprocess-Clinical-Notes.ipnyb` to prepocessing notes.

## Extract data

Run `04-Apply-med7-on-Clinical-Notes.ipynb` to extract medical entities. 

Run `05-Represent-Entities-With-Different-Embeddings.ipynb` to convert medical entities into word representations.

Run `06-Create-Timeseries-Data.ipynb` to prepare the timeseries data to fed through GRU / LSTM.

## Baseline Models - Training and Evaluation

Download Pre-trained Word2Vec & FastText embeddings from https://github.com/kexinhuang12345/clinicalBERT and copy the files into `embeddings` folder 

Run `07-Timeseries-Baseline.ipynb` to run timeseries baseline model to predict 4 different clinical tasks.

Run `08-Multimodal-Baseline.ipynb` to run multimodal baseline to predict 4 different clinical tasks.

## Proposed Model - Training and Evaluation

Run `09-Proposed-Model.ipynb` to run proposed model to predict 4 different clinical tasks.

## Report generation

`11_Timeseries_Results.ipynb` - can be used for loading and reporting the results of TimeSeries baseline model. It compares the best models result and the generated files.

`12_Multimodal_Results.ipynb` - can be used for loading and reporting the results of MultiModal baseline model. It compares the best models result and the generated files.

`13_Proposed_Results.ipynb` - can be used for loading and reporting the results of Proposed model. It compares the best models result and the generated files.

## Experimentations / Ablations

Run `05_1-Ablation_Represent-Entities-With-Glove-Embedding.ipynb` to convert medical entities into word representations.

Run `06_1-Ablation-Create-Timeseries-Data-Glove.ipynb` to prepare the timeseries data for feeding it to GloVe model

Run `09_1-Ablation-Proposed-Model-Glove.ipynb` to run the proposed model with GloVe based embedding

## Results

MIMIC-Extract implementation: https://github.com/MLforHealth/MIMIC_Extract

med7 implementation: https://github.com/kormilitzin/med7

Download Pre-trained Word2Vec & FastText embeddings: https://github.com/kexinhuang12345/clinicalBERT

Preprocessing Script: https://github.com/kaggarwal/ClinicalNotesICU

