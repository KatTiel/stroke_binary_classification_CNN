## Stroke Prediction :brain: - Binary Classification using a Convolutional Neuronal Network
The objective of this project was to develop a convolutional neural network (CNN) capable of predicting the likelihood of an ***impending*** stroke. 

It's crucial to note that this CNN predicts an ***imminent*** stroke based on the combination of all predictors right in that moment. However, it's important to understand that even if for example a young person has risk factors which significanty increase the risk of stroke, like obesity, smoking, and hypertension, they may still face a much higher risk of stroke as they age but might being predicted as "No Stroke" using this model. This is due to the fact that advancing age itself is a significant risk factor for stroke. (1) 

The predictions made by the model are not guaranteed and are based on probabilities. Encouraging a healthy lifestyle and and consultations with a primary care physician is always recommended as a preventive measure.

## How It Works
### Prerequisites 
- [Python 3.11](https://www.python.org/downloads/release/python-3110/)
- Jupyter Notebook ```pip install notebook ```
- [Required dependencies](https://github.com/KatTiel/stroke_binary_classification_CNN/blob/main/requirements.txt) ```pip install -r requirements.txt ```
- Stroke Prediction [Dataset](https://github.com/KatTiel/stroke_binary_classification_CNN/blob/main/0_data/healthcare-dataset-stroke-data.csv) (2)

### Data Set
The dataset used for this model contains 12 attributes of 5110 patients. 
Attributes:
- ID/Unique identifier
- Gender (M/F/O)
- age (y)
- hypertension (0/1)
- heart_disease (0/1)
- work_type (children/Govt_jov/Never_worked/Private/Self-employed)
- Residence_type (Rural/Urban)
- avg_glucose_level (mg/dl)
- bmi (kg/m2)
- smoking_status (formerly smoked/never smoked/smokes/Unknown)

- stroke (0/1) : Target variable

### Model Architecture

#### Strategies to Diminish Overfitting
##### Dropout
##### Early Stopping
##### Batch Normalization

### Performance Measurements
#### Accuracy
#### ROC-AUC-Curve
FP/Tp... what is more important

## License
[MIT](https://choosealicense.com/licenses/mit/)

## References 


(1) Leening M.J., Cook N.R., Ridker P.M. Should we reconsider the role of age in treatment allocation for primary prevention of cardiovascular disease? Eur. Heart J. 2017;38:1542–1547. doi: 10.1093/eurheartj/ehw287. [URL](https://pubmed.ncbi.nlm.nih.gov/27357357/).

(2) fedesorian. Stroke Prediction Dataset, Version 1. Retrieved 12/2023 from [URL](https://www.kaggle.com/datasets/fedesoriano/stroke-prediction-dataset) .

(3) Shu C, Zheng C, Luo D, Song J, Jiang Z, Ge L. Acute ischemic stroke prediction and predictive factors analysis using hematological indicators in elderly hypertensives post-transient ischemic attack. Sci Rep. 2024 Jan 6;14(1):695. doi: 10.1038/s41598-024-51402-2. PMID: 38184714; PMCID: PMC10771433. [URL](https://www.nature.com/articles/s41598-024-51402-2) .

() Mandrekar JN. Receiver operating characteristic curve in diagnostic test assessment. J Thorac Oncol. 2010 Sep;5(9):1315-6. doi: 10.1097/JTO.0b013e3181ec173d. PMID: 20736804. [URL](https://www.sciencedirect.com/science/article/pii/S1556086415306043#bib5) .

(4) Géron, A. (2019). Hands-on machine learning with Scikit-Learn, Keras and TensorFlow: concepts, tools, and techniques to build intelligent systems (2nd ed.). O’Reilly.
