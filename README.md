# Kaggle_Coleridge_4th_Solution

This is repository of the 4th place solution of [Coleridge Initiative - Show US the Data](https://www.kaggle.com/c/coleridgeinitiative-show-us-the-data).  

# Enviroment
Google Cloud Platform (most of the part)
- Debian GNU/Linux 10
- n1-standard-4.4 vCPUs, 15 GB RAM
Usuyama's enviroment (NER training)
Kaggle Code (for submission)

# Requirements
- Python 3.7.10
- numpy==1.19.5
- pandas==1.2.2
- matplotlib==3.3.4
- scikit-learn==0.24.1
- nltk==3.6.2
- tqdm==4.58.0

# Data setup
Download the [competition dataset](https://www.kaggle.com/c/coleridgeinitiative-show-us-the-data/data) and place them in `input/orig/`.   

# Training and Prediction
Run all the cells of `notebook/preprocess.ipynb`. This outputs `output/df_train_reduced.csv`. We placed this file in [coleridge-ext](https://www.kaggle.com/osciiart/coleridge-ext) to use it in kaggle code.  
Run all the cells of `notebook/detect_acronym.ipynb`. This outputs `output/df_label_acronym_ver1_all_210619_02.csv`. We placed this file in [coleridge-ext](https://www.kaggle.com/osciiart/coleridge-ext) to use it in kaggle code.  
Copy and run [govt_dataset_json_to_df](https://www.kaggle.com/mlconsult/100000-govt-datasets-api-json-to-df/). This outputs `datasets.csv`. We renamed this file into `datasets_govt.csv` and placed it in [coleridge-ext](https://www.kaggle.com/osciiart/coleridge-ext) to use it in kaggle code. We also place it in `output/` to use it in the next step.  
Copy and run [210615_det_acronym_ver2](https://www.kaggle.com/osciiart/210615-det-acronym-ver2/notebook?scriptVersionId=66042722). This outputs `df_acronym3_210615.csv`. Please place this file at `output/`.    
Run all the cells of `notebook/make_dataset_list.ipynb`. This outputs `output/df_labels_210619_01.csv`. We use this file for NER train in the next step.  
Train NER model using `coleridge_ner` repository. This outputs `model-best/` directory witch contains a trained NER model.  We placed this file in [spacy_ner_062020](https://www.kaggle.com/naotous/spacyner062020) to use it in kaggle code.  
Copy and run [210622_det1_NERu_train_govt](https://www.kaggle.com/osciiart/210622-det1-neru-train-govt?scriptVersionId=66367000). This outputs our final submission 1.  
Copy and run [210621_train_acronym_ver1](https://www.kaggle.com/osciiart/210621-train-acronym-ver1?scriptVersionId=66241779). This outputs our final submission 2.  