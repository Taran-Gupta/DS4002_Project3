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
│   ├── images
│   ├── images_augmented
│   ├── personal images
│   ├── processed_images
│   ├── Data Appendix - MI3.pdf
│   ├── cleaned_data.csv
│   └── data.csv
│   └── failed_downloads.csv
│   └── fossils_with_paths.csv
│
├── SCRIPTS/
│   ├── Downloading Data.ipynb
│   ├── Model Prediction.ipynb
│   ├── Scaling Images.ipynb
│   ├── class_names.json
│   └── fossil_model.h5
│   └── fossil_model.keras
│   └── fossil_model_weights.h5
│
└── OUTPUT/
    ├── Accuracy and Loss with just head.png
    ├── Confusion Matrix.png
    ├── Fossil Period Histogram.png
    ├── Fossil Resizing.png
    ├── Per-Class Accuracy.png
    ├── Whole model training accuracy and loss.png


```
## Section 3: Instructions for reproducing results
This section will cover the order in which code files may be executed or created if remaking from scratch. The organization of this repository will not be included in this section, as the layout is already described in detail in Section 2 above. Specific code chunks should be referenced for a detailed understanding of model creation and execution. All code contains some combination of in-line comments and headers.

### To Reproduce Results:
1. Download repository on a local/cloud machine and ensure all data files are copied correctly. Run `Downloading Data.ipynb` if image files are not already downloaded. This is also where other images could be substituted into the model.
2. If the processed data is downloaded proceed to step 3. If not, run `Scaling Images.ipynb` and check that the file names and relative path match your instance of the repository.
3. Run `Image Prediction.ipynb` to create the model that predicts time period.

### To Recreate Code and Model:
1. Start with a data file containing information about all of your images - specifically time period, fossil type (if that is important to you), and some reference to the image, whether that is a URL or file path.
2. Perform basic data cleaning on the dataframe. Remove NAs and cast misspelled classes to the correct ones (including capitalizations). If needed, perform a similar aggregation as we did to combine periods if not enough data is present in any individual period. 
3. If images need to be downloaded, download images locally, assuming dataset is not too large. This may be the most time consuming process.
4. Next, perform pre-processing on the images to match the model. For EfficientNetB0, the model works best with RGB 224x224 images. Crop, resize, and pad images as needed to get images to fit these parameters. It is recommended to save new copies of all of these images so the originals are maintained.
5. Image augmentation can be pursued for 2 reasons: increase model robustness to specific paramters (ex. rotation, scaling, greyscale, noise) and balance out uneven class sizes. Be careful what augmentations are pursued - do not create too many augmented images that overrepresent data, and do not augment images in a way that may distort the model. If augmentation is undertaken, we recommend not using any of these images for data validation, as they are not original.
6. Define your model's parameters: image size (224) and batch size (between 8-512). Batch size determines model efficiency - use lower batch sizes if hardware is limited or for better generalization, though training will be slower.
7. Train/test split the data by creating tensorflow DataGenerators and view class names and number of batches to verify the setup.
8. Build the EfficientNetB0 model. You may choose to freeze the base layers and train just the head if pre-trained weights are used (ex. imagenet). Pre-trained weights speed up training and identification of features. Run either just the head or the full model (or both) for X number of epochs (number of forward and backward passes through the training weights), recording losses and accuracy for both the training and testing data. Implement a callback to prevent overfitting, which will stop the model training if accuracy decreases for X number of epochs and restore the best weights.
9. Calculate performance metrics such as confusion matrix; f1, precision, and recall; and per-class accuracy. Note any biases or uncertainties that may appear here (ex. difference in class size, difference in augmentation, complexity and uniqueness of features).
10. If you have your own supplementary images, pass in imagees to your model for prediction, ensuring the same pre-processing is used.

## References 
[1] Ludlow Museum fossils in Shropshire Project Data - data - Data Portal, https://data.nhm.ac.uk/dataset/ludlow-museum-fossils-in-shropshire-project-data (accessed Apr. 6, 2026). 
[2] GeeksforGeeks, “Python PIL: ImageOps.fit() method,” GeeksforGeeks, https://www.geeksforgeeks.org/python/python-pil-imageops-fit-method/  (accessed Apr. 8, 2026). 
[3] “Concepts,”Pillow(PILFork), https://pillow.readthedocs.io/en/stable/handbook/concepts.html#concept-filters (accessed Apr. 8, 2026). 
[4] K. Team, “Keras documentation: Image Classification via fine-tuning with EfficientNet,” Keras, https://keras.io/examples/vision/image_classification_efficientnet_fine_tuning/  (accessed Apr. 8, 2026). 
[5] Image augmentation for convolutional neural networks | by ODSC - Open Data Science | Medium, https://odsc.medium.com/image-augmentation-for-convolutional-neural-networks-18319e1291c  (accessed Apr. 8, 2026). 
[6] Efficientnetb0 architecture — stem layer | by Sandaruwan Herath | Data Science and Machine Learning | Medium, https://medium.com/image-processing-with-python/efficientnetb0-architecture-stem-layer-496c7911a62d  (accessed Apr. 3, 2026). 
