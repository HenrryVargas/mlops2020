# Module 5 - The base experiment (without AML)

## About
This module covers an entire model training experiment - notebook, 01-ml-trials-manual.ipynb uploaded in the previous section.  The code is from my data scientist contact - Michael Kareev.<br>

A data scientist would build their experiment as depicted in this module, in a Jupyter notebook.  In the next module, we will learn how to integrate this exact experiment, with Azure Machine Learning.  Eventually, we will learn to package this into a DevOps build pipeline.  This module merely demonstrates a base experiment and traces the lifecycle of model development.<br>

Once again- this module does not touch Azure Machine Learning.  Its a plain experiment in Python, in a Jupyter notebook, to be run in the Notebook VM.

<br> Scroll below to learn the type of experiment it is and more about the dataset and use case.  You could skip executing this altogether, and just read the code and move to the next module.

<br><br>Dedicate 30 minutes for this module if you want to understand, or 15 if you want to execute, and your focus is mostly on the DevOps component.
<br><br>About scikit-learn: https://scikit-learn.org/stable/

## 1.0. About the dataset, framingham.csv
The dataset is framingham.csv, you downloaded it in section 2;  Its a popular Kaggle open dataset.<br>
https://www.kaggle.com/amanajmera1/framingham-heart-study-dataset

**Attributes/columns:** <br><br>
male: 0 = Female; 1 = Male<br>
age: Age at exam time<br>
education: 1 = Some High School; 2 = High School or GED; 3 = Some College or Vocational School; 4 = college<br>
currentSmoker: 0 = nonsmoker; 1 = smoker<br>
cigsPerDay: number of cigarettes smoked per day (estimated average)<br>
BPMeds: 0 = Not on Blood Pressure medications; 1 = Is on Blood Pressure medications<br>
prevalentStroke<br>
prevalentHyp<br>
diabetes: 0 = No; 1 = Yes<br>
totChol in mg/dL<br>
sysBP in mmHg<br>
diaBP in mmHg<br>
BMI: Body Mass Index calculated as: Weight (kg) / Height(meter-squared)<br>
heartRate: Beats/Min (Ventricular)<br>
glucose in mg/dL<br><br>

TenYearCHD - Did the person get heart disease in the 10 years study period? <br>
label; 0 = No for heart disease, 1 = Yes for heart disease;<br>

## 2.0. About the use case - Coronary Heart Disease Prediction
Given a set of attributes, predict whether a person is at risk of heart disease.

## 3.0. About the experiment
The data scientist first prepares the data/data engineers, then runs an ML algorithm to train the model.
The experiment is supervised learning, classification type, leveraging Scikit-Learn library.  It uses the RandomForest classifier algorithm.  

## 4.0. Why this notebook?
This notebook introduces the Jupyter notebook on Azure; Typically, a data scientist would run experiments here, and then collabnorate with the DevOps engineer for operationalizing the pipelines and the model as a REST service.  In the next module, you will learn how to take the code and integrate with Azure Machine Learning.<br>

## 5.0. Execute the notebook
1. Navigate to your Azure Machine Learning instance on the Azure portal
2. Click on "Compute" in the left navigation panel
3. Click on Jupyter service
4. Then click on the first notebook

The instructor will talk through how to use Jupyter notebook.<br>
The focus is not the ML experiment as much as how to integrate with Azure Machine Learning and Azure DevOps - bear this in mind.<br>

## 6.0. Notebook review part 1 - load necessary packages

![dse1-1](../images/0001-run-experiment-01.png)
<br>
<hr>
<br>

## 7.0. Notebook review part 2 - data engineering

![dse1-10](../images/0001-run-experiment-10.png)
<br>
<hr>
<br>

## 8.0. Notebook review part 3 - model training

![dse1-2](../images/0001-run-experiment-02.png)
<br>
<hr>
<br>

## 9.0. Notebook review part 4 - feature importance

![dse1-3](../images/0001-run-experiment-03.png)
<br>
<hr>
<br>


## 10.0. Notebook review part 5 - rerun with important features only from #9
![dse1-4](../images/0001-run-experiment-04.png)
<br>
<hr>
<br>

## 11.0. Notebook review part 6 - the metrics we need
![dse1-5](../images/0001-run-experiment-05.png)
<br>
<hr>
<br>

## 12.0. Notebook review part 7 - the metrics from the model training
![dse1-6](../images/0001-run-experiment-06.png)
<br>
<hr>
<br>

## 13.0. Notebook review part 8 - persist the model
![dse1-7](../images/0001-run-experiment-07.png)
<br>
<hr>
<br>

## 14.0. Notebook review part 9 - load model and run a prediction
![dse1-8](../images/0001-run-experiment-08.png)
<br>
<hr>
<br>


## 15.0. Notebook review part 10 - run multiple predictions in a call, including as called by REST service when we operationalize it
![dse1-9](../images/0001-run-experiment-09.png)
<br>
<hr>
<br>

## Recap
Its a wrap for this module.  In this module you learned to (1) a simple machine lerarning experiment - supervised learning - binary classification, (2) you learned to execute it in Jupyter notebook service, and (3) you learned how a data scientist starts off building an experiment.  Its a precursor to how to integrate an experiment with Azure Machine Learning for various ML functions.

## Next steps
Move to the next module -> data scientist trials continued, this time, with AML integration.




