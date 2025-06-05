# Project: Reducing the influence of beaurocracy in construction projects through the use of ML tools

## Overview
This repository contains a Colab notebook containing the project work of Group 03 (Cirilli, Scassellati) for the PCM course. 
The notebook contains the code to create tools supporting designers and planners in evaluating risks and predicting delays using two machine learning models.

The notebook is self-contained and well-commented, allowing users to execute the entire pipeline or selectively run parts of it using provided preprocessed data files.

## Repository Structure
```
.
├── PM_english_version.ipynb             # Main notebook containing all code and explanations
├── database_permessi.csv                # Raw dataset containing information about building permits in Bologna (2008-2024)
├── excel_folder/                        # Folder containing multiple Excel files containing building descriptions
│   ├── PDC giugno 2011.xlsx
│   ├── PDC ago - dic 2020.xlsx
│   └── ...
├── df_merged_geocoded.csv               # Intermediate file after geocoding to avoid having to rerun the code
├── restrictions_historical.csv          # File containing the list of buildings in historically significant areas 
├── restrictions_hydro.csv               # File containing the list of buildings in areas subject to hydrogeological risk 
├── processed_permit_data_bo.csv         # Output of the preprocessing of the dataset at the basis of model creation (used to skip preprocessing steps)
├── confini_bologna/                     # Folder containing Bolgona's shapefile for data visualisation
│   ├── confini_bologna.dbf
│   ├── confini_bologna.prj
│   └── ...
└── README.md                            # Project instructions and guidance
```

## Notebook Structure
- **Imports** – Cell #1
- **Dataset Creation** – Cells #2–9  
  (Loading and cleaning raw data, categorizing entries, geolocating addresses)
- **Model 1 Creation** – Cells #10–15  
  (Training, evaluating, analyzing features, and simple UI)
- **Model 2 Creation** – Cells #16–19  
  (Training, evaluating, analyzing features, and simple UI)

## File Requirements by Notebook Cell
| Cell Range | Required File(s)                   | Description                                               |
|------------|------------------------------------|-----------------------------------------------------------|
| 2          | `BOLOGNA_permits.csv`              | Raw dataset loaded                                        |
| 3          | `excel_folder/` (entire folder)    | Contains Excel files required for data aggregation        |
| 4–8        | None                               |                                                           |
| 9          | `df_merged_geocoded.csv`           | Used if skipping geocoding steps (recommended)            |
| 9          | `restrictions_historical.csv`      | Needed to complete the dataset                            |
| 9          | `restrictions_hydro.csv`           | Needed to complete the dataset                            |
| 10-15      | `processed_permit_data_bo.csv`     | Final preprocessed dataset for Model 1                    |
| 11         | `confini_bologna/` (entire folder) | Contains shape files required for data visualisation      |
| 16–19      | `processed_permit_data_bo.csv`     | Final preprocessed dataset for Model 2                    |

N.B. Cells 2-9 add on and make reference to files created while being run in sequence. For completeness we recommend either running them all uploading the files above or skip to cell 10 and upload only the files from 'processed_permit_data_bo.csv' on.  

## How to Use

### 1. Environment Setup
All required libraries and dependencies are installed in **Cell 1** of the notebook. Run this cell first.

### 2. Dataset Preparation (Optional)
Cells 2 through 9 handle dataset loading, cleaning, and geocoding.
- **If you upload directly the file `processed_permit_data_bo.csv`, you can skip these preprocessing cells.**
- Start directly from Cell 10 for model training.
- If running from the beginning, ensure the `excel_folder/` and all intermediate files are uploaded to Colab as detailed in the "File Requirements" section.

### 3. File Dependencies
Many cells are independent and can be executed directly. For those that require specific files, a comment at the beginning of the cell indicates the filename and its expected location.

### 4. Model Training
Two models are trained for request delay and outcome prediction, respectively. These sections are clearly separated and include:
- Feature selection
- Model creation and training
- Evaluation metrics
- Visualisation of data

### 5. Notes
- Be sure to upload any referenced files or folders to your Colab session before running the related cells.
- If you want to reproduce the models without preprocessing steps, ensure `processed_permit_data_bo.csv` is present.

## License
This project is for educational purposes only. 

---

For any issues, please contact the project maintainers at:
- caterina.scassellati@mail.polimi.it
- carlotta.cirilli@mail.polimi.it
