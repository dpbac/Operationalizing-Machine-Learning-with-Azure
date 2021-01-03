<img align="left" width="100" height="75" src="https://github.com/dpbac/Optimizing-an-ML-Pipeline-in-Azure/blob/master/images/microsoft-azure-640x401.png">

# Operationalizing Machine Learning with Azure

## Overview

In this second project of the **Udacity Nanodegree program Machine Learning Engineer with Microsoft Azure** we configure a cloud-based machine learning production model, deploy it, and consume it.

As in the first project we use the `Bank Marketing dataset` which contains data collected during direct marketing campaigns (phone calls) of a Portuguese banking institution. 
This is a subset of the original public dataset available at [UCI Machine Learning repository]( https://archive.ics.uci.edu/ml/datasets/Bank+Marketing). In this website a detailed 
description of each feature can be found.

In the [first project]( https://github.com/dpbac/Optimizing-an-ML-Pipeline-in-Azure) the main goal was to Optimize an Azure ML pipeline Azure ML pipeline using the Python SDK and a 
provided Scikit-learn model and compare it to an Azure AutoML run.

In this new project we go further and not only obtain the best model using Azure Automated ML, but we configure a cloud-based machine learning production model, deploy it, 
and consume it.

The main steps performed in this project are:

![Architectural diagram showing main steps](https://github.com/dpbac/Operationalizing-Machine-Learning-with-Azure/blob/master/images/main_steps.JPG)
**Architectural diagram showing main steps performed in order to configure a cloud-based machine learning production model, 
deploy it, and consume it.**
source: Adapted from Nanodegree Program Machine Learning Engineer with Microsoft Azure

1. Authentication
2. Automated ML Experiment
3. Deploy the best model
4. Enable logging 
5. Swagger Documentation
6. Consume model endpoints
7. Create and publish a pipeline

## Architectural Diagram
*TODO*: Provide an architectual diagram of the project and give an introduction of each step. 
An architectural diagram is an image that helps visualize the flow of operations from start to finish. 
In this case, it has to be related to the completed project, with its various stages that are critical to the overall flow. 
For example, one stage for managing models could be "using Automated ML to determine the best model". 



## Key Steps
*TODO*: Write a short discription of the key steps. Remeber to include all the screenshots required to demonstrate key steps. 

### Step 1: Authenticatication

It was not necessary to perform this step since this project was developed using the VM provided by Udacity. 
By using the lab provide by Udacity, we are not authorized to create a security principal.

### Step 2: Automated ML Experiment

Having security is enabled and authentication is completed at the first step we create an experiment using `Automated ML`, 
configure a compute cluster, and use that cluster to run the experiment.

In this step we perform the following substeps:

1. Initialize workspace.

To start we need to initialize our workspace and create a Azule ML experiment.
It is important to asure that the config file is present at `.\config.json`. `config.json` can be downloaded from home of `Azure Machine Learning Studio`

The config.json can be downloaded in the overview of Azure portal.

![](https://github.com/dpbac/Operationalizing-Machine-Learning-with-Azure/blob/master/images/configure_json_edited.JPG)
**Where to obtain config.json**

2. Create an Azure ML experiment
3. Create or Attach an AmlCompute cluster
4. Load Dataset from https://automlsamplenotebookdata.blob.core.windows.net/automl-sample-notebook-data/bankmarketing_train.csv and make sure it is registered.

![](https://github.com/dpbac/Operationalizing-Machine-Learning-with-Azure/blob/master/images/registered_datasets.JPG)
**Registered datasets.**

5. Retrieve the best model.

When the Azure AutoML experiment is complete, we can retrieve the best model to use in the next step.

![](https://github.com/dpbac/Operationalizing-Machine-Learning-with-Azure/blob/master/images/experiment_completed.JPG)
**AutoML experiment completed**

![](https://github.com/dpbac/Operationalizing-Machine-Learning-with-Azure/blob/master/images/best_model.JPG)
**Best model**

From this last image we can see that the best model is `Voting Ensemble` with AUC weighted 0.9463.

### Step 3: Deploy the best model

In this step we select the best model and deploy it enabling authentication and using Azure Container Instance (ACI) (see image bellow).

![](https://github.com/dpbac/Operationalizing-Machine-Learning-with-Azure/blob/master/images/deploy_model.JPG)
**Deploying the best model**

![]()
**Model deployed with success**

Deploying the Best Model will allow to interact with the HTTP API service and interact with the model by sending data over POST requests.

### Step 4: Enable logging

In this step, we work on the logs.py provided and enable `Applications insights` using Azure SDK. 

This is a very important step since it allows to determine anomalities, irregularities and visualize the performance. 

![]()
**log.py 

### Step 5: Swagger Documentation



### Step 6: Consume model endpoints

### Step 7: Create and publish a pipeline


## Screen Recording
*TODO* Provide a link to a screen recording of the project in action. Remember that the screencast should demonstrate:

## Future work

