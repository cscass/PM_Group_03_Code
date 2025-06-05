# Project: Predictive Modeling for Design Risk and Delay Assessment

## Overview
This repository contains a Colab notebook aimed at supporting designers and planners in evaluating risks and predicting delays using two machine learning models.

The notebook is self-contained and well-commented, allowing users to execute the entire pipeline or selectively run parts of it using provided preprocessed data files.

## Repository Structure
```
.
├── PM_english_version.ipynb             # Main notebook containing all code and explanations
├── processed_permit_data_bo.csv         # Preprocessed dataset (optional, used to skip preprocessing steps)
├── BOLOGNA_permits.csv                  # Raw dataset (used in initial preprocessing)
├── excel_folder/                        # Folder containing multiple Excel files required in Cell 3
│   ├── file1.xlsx
│   ├── file2.xlsx
│   └── ...
├── geocoded_permit_data.csv             # Intermediate file after geocoding
├── processed_permit_data.csv            # Intermediate file before final cleaning
├── model1_features.csv                  # Features used for model 1 (if saved)
├── model2_features.csv                  # Features used for model 2 (if saved)
└── README.md                            # Project instructions and guidance
```

## Notebook Structure
- **Imports** – Cell #1
- **Dataset Creation** – Cells #2–9  
  (Loading raw data, categorizing entries, geolocating addresses)
- **Model 1 Creation** – Cells #10–15  
  (Training, evaluating, analyzing features, and simple UI)
- **Model 2 Creation** – Cells #16–19  
  (Training, evaluating, analyzing features, and simple UI)

## File Requirements by Notebook Cell
| Cell Range | Required File(s)                   | Description                                               |
|------------|------------------------------------|-----------------------------------------------------------|
| 2          | `BOLOGNA_permits.csv`              | Raw dataset loaded                                        |
| 3          | `excel_folder/` (entire folder)    | Contains Excel files required for data aggregation        |
| 4–5        | None (uses Google Maps API)        | Geocoding steps                                           |
| 6–7        | `geocoded_permit_data.csv`         | Used if skipping geocoding steps                         |
| 8–9        | `processed_permit_data.csv`        | Used if skipping full preprocessing                      |
| 10–15      | `processed_permit_data_bo.csv`     | Final preprocessed dataset for Model 1                  |
| 16–19      | `processed_permit_data_bo.csv`     | Final preprocessed dataset for Model 2                  |

## How to Use

### 1. Environment Setup
All required libraries and dependencies are installed in **Cell 1** of the notebook. Run this cell first.

### 2. Dataset Preparation (Optional)
Cells 2 through 9 handle dataset loading, cleaning, and geocoding.
- **If you have the file `processed_permit_data_bo.csv`, you can skip these preprocessing cells.**
- Start directly from Cell 10 for model training.
- If running from the beginning, ensure the `excel_folder/` and all intermediate files are uploaded to Colab.

### 3. File Dependencies
Many cells are independent and can be executed directly. For those that require specific files, a comment at the beginning of the cell indicates the filename and its expected location.

### 4. Model Training
Two models are trained for risk and delay prediction, respectively. These sections are clearly separated and include:
- Feature selection
- Model creation and training
- Evaluation metrics

### 5. Notes
- Be sure to upload any referenced files or folders to your Colab session before running the related cells.
- If you want to reproduce the models without preprocessing steps, ensure `processed_permit_data_bo.csv` is present.

## License
This project is for educational purposes only. Licensing terms can be added here if needed.

---

For any issues, please contact the project maintainer.
