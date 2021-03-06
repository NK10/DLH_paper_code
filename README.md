# DLH_paper_code

**Citation:** Batuhan Bardak, Mehmet Tan. mproving Clinical Outcome Predictions Using Convolution over Medical Entities with Multimodal Learning. 
https://doi.org/10.48550/arXiv.2011.12349

**Original Paper Repo:** - https://github.com/tanlab/ConvolutionMedicalNer

**Dependencies** - https://github.com/NK10/DLH_paper_code/blob/main/Package_list.txt

**Fix the below points:**
 - Path was set incorrectly in notebook 2, instead of reading from “DATAPATH” for “patients” we have to read from “MIMIC_EXTRACT_DATA”
 - Asked to installed nltk.punkt in notebook 3, use the below command:
   - pip install –user nltk
 - Error in step med7 = spacy.load("en_core_med7_lg")
   - Error msg “OSError: [E050] Can't find model 'en_core_med7_lg'. It doesn't seem to be a Python package or a valid path to a data directory.”
   - Solution follow solution from link (Med7 — an information extraction model for clinical natural language processing | by kormilitzin | Medium)
- Install gensim pip install --user gensim==3.7.0
 - Fix the code in notebook 5, 6, 7, 8, and 9 to make it work, we have added the comment where we fixed it.
- Create a cnn folder under the results. 

**Execute the notebooks in the following order:**
 - Clone the repo : https://github.com/NK10/DLH_paper_code/
 - Get the "all_hourly_data.h5" by following the steps mentioned in "Pre-processed Output" from git repo https://github.com/MLforHealth/MIMIC_Extract and put it in the data folder.
 - Move files ADMISSIONS.csv, NOTEEVENTS.csv, ICUSTAYS.csv files into the data folder.
 - Execute 02-Select-SubClinicalNotes.ipynb to select sub nodes based on criteria from all MIMIC-III Notes.
 - Run 03-Prprocess-Clinical-Notes.ipnyb to preprocessing notes.
 - Run 04-Apply-med7-on-Clinical-Notes.ipynb to extract medical entities.
 - Download pre trained embeddings into embeddings folder via link in given References section.
 - Run 05-Represent-Entities-With-Different-Embeddings.ipynb to convert medical entities into word representations.
 - Run 06-Create-Timeseries-Data.ipynb to prepare the time series data to fed through GRU / LSTM. 
 - Run 07-Timeseries-Baseline.ipynb to run a timeseries baseline model to predict 2 different clinical tasks.
 - Run 08-Multimodal-Baseline.ipynb to run multimodal baseline to predict 2 different clinical tasks. 
 - Run 09-Proposed-Model.ipynb to run a proposed model to predict 2 different clinical tasks.


# References from original paper:

-  https://github.com/tanlab/ConvolutionMedicalNer
-  https://github.com/MLforHealth/MIMIC_Extract
-  Download the MIMIC-III dataset via  https://mimic.physionet.org/
-  MIMIC-Extract implementation:  https://github.com/MLforHealth/MIMIC_Extract
-  med7 implementation:  https://github.com/kormilitzin/med7
-  Download Pre-trained Word2Vec & FastText embeddings:  https://github.com/kexinhuang12345/clinicalBERT
-  Preprocessing Script:  https://github.com/kaggarwal/ClinicalNotesICU


