## Stroke Prediction :brain: - Binary Classification Model using a Convolutional Neuronal Network
The objective of this project was to develop a convolutional neural network (CNN) capable of predicting the likelihood of an ***impending*** stroke. 

It is crucial to note that this CNN predicts an ***imminent*** stroke based on the combination of all predictors right in that moment. However, it is important to understand that even if for example a young person has risk factors which significanty increase the risk of stroke, like obesity, smoking, and hypertension, they may still face a much higher risk of stroke as they age but might being predicted as "No Stroke" using this model. This is due to the fact that advancing age itself is a significant risk factor for stroke. (1) 

The predictions made by the model are not guaranteed and are based on probabilities. Encouraging a healthy lifestyle and and consultations with a primary care physician is always recommended as a preventive measure.

## Prerequisites 
- [Python 3.11](https://www.python.org/downloads/release/python-3110/)
- Jupyter Notebook ```pip install notebook ```
- [Required dependencies](https://github.com/KatTiel/stroke_binary_classification_CNN/blob/main/requirements.txt) ```pip install -r requirements.txt ```
- [Stroke Prediction Dataset](https://github.com/KatTiel/stroke_binary_classification_CNN/blob/main/0_data/healthcare-dataset-stroke-data.csv) (2)

## Dataset
The dataset used for this model contains 12 attributes of 5110 patients. It was split into a **training set** (80%, 3927 records), a **validation set** (10%, 491 records) and a **test set** (10%, 491 records).

*Attributes:*
- id
- gender (M/F/O)
- age (y)
- hypertension (0/1)
- heart_disease (0/1)
- work_type (children/Govt_jov/Never_worked/Private/Self-employed)
- Residence_type (Rural/Urban)
- avg_glucose_level (mg/dl)
- bmi (kg/m2)
- smoking_status (formerly smoked/never smoked/smokes/Unknown)

*Target variable:*
- stroke (0/1)

## Features
Data exploration revealed that the dataset exhibits a significant imbalance of the target variable, with only 4% of individuals experiencing a stroke. To address this issue, a performance metric other than accuracy was chosen. Additionally, it was observed that hypertension and heart disease were notably underrepresented in the dataset. The choice of features for predictions was based on empirical studies that have identified these factors as significant contributors to stroke risk (3, 4).

*Selected predictors:*
- age
- hypertension
- heart_disease
- avg_glucose_level
- bmi
- smoking status 

## Strategies to Diminish Overfitting
To avoid overfitting of the model, the following aspects were added:

### Dropout
Randomly selected neurons are dropped out or ignored with a certain probability. This encourages generalization as the network does not rely too heavily on individual neurons.

### Early Stopping
During training, the model's performance on the validation set is monitored. The training is stopped and the weights are restored when the performance on the validation set diminishes. This prevents the model from learning noise in the training data (5).

## Performance Measurements
### Binary Accuracy
<img width="161" alt="" src="https://github.com/KatTiel/stroke_binary_classification_CNN/assets/76701992/7417c4b4-09d8-4dba-bb11-8e9e9dbebc1e">

Initially, binary accuracy served as an intital performance marker for the ***validation*** set:

:arrow_right: Best *Validation* Accuracy: 0.9532

However, due to the dataset's imbalance, acccuracy proved inadequate as a performance measure. Instead, a Receiver Operating Characteristic (ROC) Curve was employed, with the Area Under the ROC Curve (AUC) serving as the performance indicator.

### ROC AUC
<img width="261" alt="" src="https://github.com/KatTiel/stroke_binary_classification_CNN/assets/76701992/0db359eb-5339-43c4-b493-3fea771dbfdf">

AUC = Area under the ROC curve, quantifies overall performance of a binary classifier

:arrow_right: AUC-Score of the predicted ***test*** data classes: 0.88 :heavy_exclamation_mark:

An AUC-Score of 0.8-0.9 is considered excellent (6).

The choice of the ROC curve as a performance parameter was based on the fact that 'when you care more about the false negatives than the false positives, you should prefer the ROC curve'(5,  p.117). 
The potential, detrimental consequences of overlooking the risk of an impending stroke were deemed more severe than the psychological impact of incorrect, false-positive predictions. However, it is essential to emphasize that the psychological consequences of the latter should not be underestimated. Hence, it is important to communicate that this model provides probabilities rather than certainties, ensuring users understand its limitations.

## License
[MIT](https://choosealicense.com/licenses/mit/)

## References 
(1) Leening M.J., Cook N.R., Ridker P.M. Should we reconsider the role of age in treatment allocation for primary prevention of cardiovascular disease? Eur. Heart J. 2017;38:1542–1547. [doi: 10.1093/eurheartj/ehw287.](https://pubmed.ncbi.nlm.nih.gov/27357357/)

(2) fedesorian. Stroke Prediction Dataset, Version 1. Retrieved 12/2023 from [Kaggle.](https://www.kaggle.com/datasets/fedesoriano/stroke-prediction-dataset)

(3) Shu C, Zheng C, Luo D, Song J, Jiang Z, Ge L. Acute ischemic stroke prediction and predictive factors analysis using hematological indicators in elderly hypertensives post-transient ischemic attack. Sci Rep. 2024 Jan 6;14(1):695. [doi: 10.1038/s41598-024-51402-2.](https://www.nature.com/articles/s41598-024-51402-2)

(4) Boehme AK, Esenwa C, Elkind MS. Stroke Risk Factors, Genetics, and Prevention. Circ Res. 2017 Feb 3;120(3):472-495.  [doi: 10.1161/CIRCRESAHA.116.308398.](https://pubmed.ncbi.nlm.nih.gov/28154098/)

(5) Géron, A. (2019). Hands-on machine learning with Scikit-Learn, Keras and TensorFlow: concepts, tools, and techniques to build intelligent systems (2nd ed.). O’Reilly.

(6) Mandrekar JN. Receiver operating characteristic curve in diagnostic test assessment. J Thorac Oncol. 2010 Sep;5(9):1315-6.  [doi: 10.1097/JTO.0b013e3181ec173d.](https://www.sciencedirect.com/science/article/pii/S1556086415306043#bib5)

