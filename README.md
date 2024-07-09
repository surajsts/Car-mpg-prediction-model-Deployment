# Google-Cloud-Platform-Deployment

<h3> Project Objective:</h3>

<img align="right" alt="Coding" width="400" src="https://github.com/surajsts/Car-mpg-prediction-model-Deployment/blob/bd191274d3a9650e6af6d50f297838c80bb2e419/Images/mlops.png">

The project aims to focus on Unsupervised Learning approach to increase the model efficiency <br>
and the core MLOps life cycle concepts (excluding monitoring and retraining concepts) which includes: <br>

- Data Preprocessing<br>
- Model Training <br>
- Model Validation<br>
- Model Packaging (using pickle files and docker images for encapsulation) <br>
- CI/CD Pipelines with conditional trigger for deployment (Github)<br>
- Model Deployment using Google Artifact Registry for saving the Docker images <br>
  and Google Cloud Run to deploy the dockerized model.<br>

<h6> Unsupervised Learning algorithms like K-Means and DBSCAN clustering is performed and interesting relationships between the features (miles per gallon (mpg), weight of car, Horse power) is found. Regression model is trained using original dataset along with the feature labels obtained from the Unsupervised learning models and comparison of various models is done. Finally the best model is saved for the deployment purposes.</h6>

<h3> Google Cloud Services used:</h3>

- Google Cloud Run <br>
- Artifact Registry <br>
- Cloud Storage (Buckets) <br>

<h4> gcloud commands used: </h4>

1)  gcloud builds submit --tag gcr.io/mldeployflask/continuous-deployment --project=mldeployflask <br>

2)  gcloud run deploy continuous-deployment --image gcr.io/mldeployflask/continuous-deployment --platform managed --project=mldeployflask --allow-unauthenticated --region us-east1 <br>

3)  gcloud iam service-accounts list --project=mldeployflask  

(To view the service accounts associated with the project)

4)  gcloud iam service-accounts keys create ./keys.json --iam-account github-actions@mldeployflask.iam gserviceaccount.com

(To create key for the chosen google cloud service account, which will be used for Github CI/CD pipeline purposes)

Here, "mldeployflask" is the GCP project ID and "continuous-deployment" is the Cloud Run Service Name. 

<h4> Github CI/CD pipeline: </h4>

![Github CICD](https://github.com/surajsts/Car-mpg-prediction-model-Deployment/blob/05657204ec40cf088b73db41e2f9654cf2cbf1d9/Images/GithubCICD.png)

<h4> Conditional Deployment: </h4>

Conditional deployment of the ML model is ensured to prevent the deployment of the model in the CI/CD pipeline unless the commit message begins with "[deploy-now]" string.
 
![Cond deploy](https://github.com/surajsts/Car-mpg-prediction-model-Deployment/blob/8ac8ff0369fd51d0c2aa8f6e3c3ae563268aa3d1/Images/ConditionalDeployment.png)



<h4> Google Cloud Run Service: </h4>

The "continuous-deployment-cicd" is the cloud run service, after the successful deployment of the   

![Cloud Run](https://github.com/surajsts/Car-mpg-prediction-model-Deployment/blob/8ac8ff0369fd51d0c2aa8f6e3c3ae563268aa3d1/Images/CloudRunService.png)

<h4> Deployed Model: </h4>

