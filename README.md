# DS4002_Project3
Fossil Period Identification


## Section 1: Software and platform section
- Type of Software: Integrated Development Environment (IDE) / Interactive Computing Platform / Web-based notebook environment
- Packages installed: numpy, pandas, matplotlib, Image, Path, PIL, tensorflow
- Platform: Cloud-based (SaaS)

## Section 2: A Map of your documentation
```

DS4002_Project2/
│
├── README.md
├── LICENSE.md
│
├── DATA/
│   ├── net worth by quarter.csv
│   ├── net_worth_cleaned.csv
│   ├── README_net_worth.txt
│   ├── README_unemployment.txt
│   ├── unemployment by month.csv
│   ├── unemployment_cleaned.csv
│   └── Project 2 - Data Appendix.pdf
│
├── SCRIPTS/
│   ├── Data Cleaning.ipynb
│   ├── EDA_unemployment.ipynb
│   ├── EDA_wealth_differences.ipynb
│   ├── Predictive Analysis.ipynb
│   └── Unemployment_and_Net_Worth_Correlation.ipynb
│
└── OUTPUT/
    ├── ARIMA_percent_error_prediction.png
    ├── ARIMA_predicted_vs_actual.png
    ├── net_worth_over_time.png
    ├── normalized_unemployment_net_worth.png
    ├── regression_predicted_vs_actual.png
    ├── rolling_correlation.png
    ├── unemployment_20-24.png
    ├── unemployment_histograms.png
    └── unemployment_over_time.png

```
## Section 3: Instructions for reproducing results
This section will cover the order in which code files may be executed or created if remaking from scratch. The organization of this repository will not be included in this section, as the layout is already described in detail in Section 2 above. Specific code chunks should be referenced for a detailed understanding of model creation and execution. All code contains some combination of in-line comments and headers.

### To Reproduce Results:
1. Download repository on a local/cloud machine and ensure all data files are copied correctly. Run `Downloading Data.ipynb` if image files are not already downloaded. This is also where other images could be substituted into the model.
2. If the processed data is downloaded proceed to step 3. If not, run `Scaling Images.ipynb` and check that the file names and relative path match your instance of the repository.
3. Run `Image Prediction.ipynb` to create the model that predicts time period.

### To Recreate Code and Model:
1. Start with

## References 
[1] Ludlow Museum fossils in Shropshire Project Data - data - Data Portal, https://data.nhm.ac.uk/dataset/ludlow-museum-fossils-in-shropshire-project-data (accessed Apr. 6, 2026). 
[2] GeeksforGeeks, “Python PIL: ImageOps.fit() method,” GeeksforGeeks, https://www.geeksforgeeks.org/python/python-pil-imageops-fit-method/  (accessed Apr. 8, 2026). 
[3] “Concepts,”Pillow(PILFork), https://pillow.readthedocs.io/en/stable/handbook/concepts.html#concept-filters (accessed Apr. 8, 2026). 
[4] K. Team, “Keras documentation: Image Classification via fine-tuning with EfficientNet,” Keras, https://keras.io/examples/vision/image_classification_efficientnet_fine_tuning/  (accessed Apr. 8, 2026). 
[5] Image augmentation for convolutional neural networks | by ODSC - Open Data Science | Medium, https://odsc.medium.com/image-augmentation-for-convolutional-neural-networks-18319e1291c  (accessed Apr. 8, 2026). 
[6] Efficientnetb0 architecture — stem layer | by Sandaruwan Herath | Data Science and Machine Learning | Medium, https://medium.com/image-processing-with-python/efficientnetb0-architecture-stem-layer-496c7911a62d  (accessed Apr. 3, 2026). 
