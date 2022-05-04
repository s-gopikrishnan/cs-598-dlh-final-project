# Implementation for Improving Clinical Outcome Predictions Using Convolution over Medical Entities with Multimodal Learning


## Usage

1. Clone the code to local.   
```
https://github.com/s-gopikrishnan/cs-598-dlh-final-project
cd cs-598-dlh-final-project
```
2. Run MIMIC-Extract Pipeline as explained in https://github.com/MLforHealth/MIMIC_Extract.   

3. Copy the output file of MIMIC-Extract Pipeline named `all_hourly_data.h5` to `data` folder.

4. Run `01-Extract-Timseries-Features.ipnyb` to extract first 24 hours timeseries features from MIMIC-Extract raw data.

5. Copy the `ADMISSIONS.csv`, `NOTEEVENTS.csv`, `ICUSTAYS.csv` files into `data` folder.

6. Run `02-Select-SubClinicalNotes.ipynb` to select subnotes based on criteria from all MIMIC-III Notes.

7. Run `03-Prprocess-Clinical-Notes.ipnyb` to prepocessing notes.

8. Run `04-Apply-med7-on-Clinical-Notes.ipynb` to extract medical entities. 

9. Download pretrained embeddings into `embeddings` folder via link in given References section.

10. Run `05-Represent-Entities-With-Different-Embeddings.ipynb` to convert medical entities into word representations.

11. Run `06-Create-Timeseries-Data.ipynb` to prepare the timeseries data to fed through GRU / LSTM.

12.Run `07-Timeseries-Baseline.ipynb` to run timeseries baseline model to predict 4 different clinical tasks.

12.Run `08-Multimodal-Baseline.ipynb` to run multimodal baseline to predict 4 different clinical tasks.

12.Run `09-Proposed-Model.ipynb` to run proposed model to predict 4 different clinical tasks.

You can use the `10-Report-Metrics.ipynb` file to print the metrics of the models

`11_Timeseries_Results.ipynb` - is used for loading and reporting the results of TimeSeries baseline model. It compares the best models result and the generated files.

`12_Multimodal_Results.ipynb` - is used for loading and reporting the results of MultiModal baseline model. It compares the best models result and the generated files.

`13_Proposed_Results.ipynb` - is used for loading and reporting the results of Proposed model. It compares the best models result and the generated files.

## References

Download the MIMIC-III dataset via https://mimic.physionet.org/

MIMIC-Extract implementation: https://github.com/MLforHealth/MIMIC_Extract

med7 implementation: https://github.com/kormilitzin/med7

Download Pre-trained Word2Vec & FastText embeddings: https://github.com/kexinhuang12345/clinicalBERT

Preprocessing Script: https://github.com/kaggarwal/ClinicalNotesICU

