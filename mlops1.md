# Machine Learning deployment and Re-Training deployment with CI/CD using Azure DevOps

## End to End - Model Building - Model Deployment and Retraining process

Azure machine learning services has end to end data science lifecycle process. Which means we can develop the model and then package it up for production. Then we can create model file and deploy as docker image with REST API. Then the model image can be deployed to Azure kubernetes container and deployed as REST API for other application to consume.

Here is the Data Science Application Life cycle process and the responsibility of Data Scientists and Machine learning or AI Engineer.

## Architecture

![alt text](https://github.com/balakreshnan/mlops2020/blob/master/images/mlops1.jpg "Architecture")

From Left to Right: Left side of the diagram is where Data engineer and data scientists work together or some times only Data scientists who does the data engineering. By looking at different data sources for a specific use case and then trying to find the proper features needed for the use case. Once the features are extracted then the data is labelled for prediction.

This process is repeated cyclic process until data scientists can find the right features and then validating different machine learning algorithm to find the algorithm that works for the use case. Usually this process can take lot of time. To increase the productivity of the trying different model and tuning it please try Azure Machine learning services — Automated ML option. Automated ML runs through various ski-kit algorithm and find the best model for the data set.

Once the best model is found now it is time to prepare for production. Usually the best model is stored as pickle file. For pickle file we need get that to the Machine learning or AI engineer to create the production deployment code.

To deploy the best model to production, need to write the scoring file which will do the data engineering automated tasks to create the proper data set used for the model. Then load the pickle file and then predict the results. Now the score file is built as Flask REST api so that any down stream system can consume the API.

To do the deployment we are going to use Azure DevOps. The source code created by ML/AI engineer and Data scientists are store in Github repository. So in this we can either implement continuous Integration and Continuous deployment.

Azure DevOps code is available here:
https://github.com/balakreshnan/mlops

First build the build pipeline by defining the pipeline yaml file. Then configure the build. Now for build select the repo where the code is stored. You can configure either if you want to do continuous build or trigger based on manual.

Next build the release pipeline. Follow the steps in this tutorial:
https://github.com/balakreshnan/mlops2020/tree/master/feb2020/lab-guide

The above example had 3 tasks one for updating python 3.6 and then Install all the dependent libraries or packages for the python. Final one to run bash script to run the deploy rest api script to create the rest api.

Now you can build and run the release pipeline and might take about 30 to 40 minutes each for build and release. Wait until the complete task is completed. Finally you should see the rest api url and then test. Also if you log into Azure machine learning services workspace you can see the REST API deployed in AKS cluster.

Now you can see how Build and deploy tasks are automated and made seamless for the machine learning model to be deployed and show value by other business application consumes using the REST API.

Rest API implementation will also record the score from inferencing and then send that to Event hub to save for future and also based on rules using Stream analytics we can enable a retraining process using Azure function to update the scoring code with some comment. Also Stream Analytics can store the data in Azure SQL for further Power BI reporting to watch for performance drift.

