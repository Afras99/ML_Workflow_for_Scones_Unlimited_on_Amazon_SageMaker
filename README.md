# ML Workflow for Scones Unlimited on Amazon SageMaker

Welcome to the ML Workflow for Scones Unlimited project! As a Machine Learning Engineer at Scones Unlimited, you'll be embarking on a journey to build an image classification model that can distinguish between bicycles and motorcycles. This model will have a multitude of applications, from optimizing delivery routes to identifying defects in products. With the power of AWS SageMaker, Lambda functions, and Step Functions, you'll create an end-to-end ML workflow that's scalable, efficient, and dependable. 🛠️📷

## Getting Started

* Proceed with the project within the [jupyter notebook](SconesUnlimited.ipynb).

### Dependencies

```
Python 3.8
scikit-learn latest
```

### Installation
For this project, it is highly recommended to use Sagemaker Studio from the course provided AWS workspace. This will simplify much of the installation needed to get started.

For local development, you will need to setup a jupyter lab instance.
* Follow the [jupyter install](https://jupyter.org/install.html) link for best practices to install and start a jupyter lab instance.
* If you have a python virtual environment already installed you can just `pip` install it.
```
pip install jupyterlab
```

## Project Overview 📋

In this project, I've designed and implemented a scalable image classification model using Amazon SageMaker. My goal was to create a workflow that can distinguish between bicycles and motorcycles, thus aiding Scones Unlimited in assigning delivery professionals to appropriate orders. The project unfolds in several key steps:

### Step 1: Data Staging 📂

- Set up a SageMaker Studio workspace.
- Prepared and loaded the data into SageMaker.
- Ensured the data is preprocessed and ready for training.

### Step 2: Model Training and Deployment 🚀

- Trained a machine learning model on SageMaker.
- Deployed the trained model as an API endpoint.
- Constructed an API endpoint that's linked to the deployed model.

### Step 3: Lambdas and Step Function Workflow ⚙️

- Developed three Lambda functions to orchestrate the workflow:
  1. Retrieve image data as an event.
  2. Perform image classification.
  3. Filter out low-confidence inferences.
- Created a Step Function to weave the Lambdas into a seamless workflow.

### Step 4: Testing and Evaluation 🧪

- Rigorously tested and evaluated the performance of your ML workflow.
- Ensured the classification model achieves a test accuracy above **94%**.

### Step 5: Cleanup Cloud Resources ♻️

- Wraped up the project by cleaning up unnecessary cloud resources.

## Skills Applied 🧠

Throughout this project, I've applied the following skills:

- Utilized SageMaker Studio for a productive ML environment.
- Trained and deployed ML models on SageMaker.
- Created and managed AWS Lambda functions.
- Designed and implemented Step Functions to compose Lambda workflows.
- Monitored and evaluated model performance using SageMaker Model Monitor.
- Visualized and interpreted Model Monitor data.

----
1. The **Serialize Image Data Lambda Function** takes the address of an image hosted in S3, then serializes and returns a JSON
object.
2. The **Infer Serialized Image Data** takes the JSON object returned from 1 and passes it to an end point and collectd the result
as a JSON Object.
3. The **Filter Results Lambda Function** takes the inference data from 2 and filters only the images that meet the defined threshold.  

## Step Functions Output Graph
![](https://github.com/Arnit9/ML-Workflow-for-Scones-Unlimited-on-Amazon-SageMaker/blob/master/images/stepfunction-graph.png)

## Step Function Table View Output
![](https://github.com/Arnit9/ML-Workflow-for-Scones-Unlimited-on-Amazon-SageMaker/blob/master/images/stepfunction-tableview.png)

---
Feel free to connect for any inquiries or insights. Happy building and scone-classifying! 🥐🤖
