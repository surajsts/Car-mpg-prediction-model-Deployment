# Google-Cloud-Platform-Deployment

<h2> Project Objective:</h2>

<img align="right" alt="Coding" width="400" src="https://github.com/surajsts/Car-mpg-prediction-model-Deployment/blob/bd191274d3a9650e6af6d50f297838c80bb2e419/Images/mlops.png">

The project aims to focus on Unsupervised Learning approach to increase the model efficiency <br>
and the core MLOps life cycle concepts (excluding monitoring and retraining) that includes: <br>

- Data Preprocessing<br>
- Model Training <br>
- Model Validation<br>
- Model Packaging (using pickle files and docker images for encapsulation) <br>
- CI/CD Pipelines with conditional trigger for deployment (Github)<br>
- Model Deployment using Google Artifact Registry for saving the Docker images <br>
  and Google Cloud Run to deploy the dockerized model.<br>

<h4> Unsupervised Learning algorithms like K-Means and DBSCAN clustering is performed and interesting relationships between the features (miles per gallon (mpg), weight of car, Horse power) is found. Regression model is trained using original dataset along with the feature labels obtained from the Unsupervised learning models and comparison of various models is done. Finally the best model is saved for the deployment purposes.</h4>

<h2> Google Cloud Services used:</h2>

- Google Cloud Run <br>
- Artifact Registry <br>
- Cloud Storage (Buckets) <br>

<!-- <h3> gcloud commands used: </h3>

1)<h4>  gcloud builds submit --tag gcr.io/mldeployflask/continuous-deployment --project=mldeployflask <h4> <br>

2) <h4> gcloud run deploy continuous-deployment --image gcr.io/mldeployflask/continuous-deployment --platform managed --project=mldeployflask --allow-unauthenticated --region us-east1 <h4><br>

3)<h4>  gcloud iam service-accounts list --project=mldeployflask  <h4>

  (To view the service accounts associated with the project)

4) <h4> gcloud iam service-accounts keys create ./keys.json --iam-account github-actions@mldeployflask.iam gserviceaccount.com <h4>

  (To create key for the chosen google cloud service account, which will be used for Github CI/CD pipeline purposes)

Here, <strong>mldeployflask</strong> is the GCP project ID and <strong>continuous-deployment</strong> is the Cloud Run Service Name.  -->

<h3>GCloud Commands Used:</h3>

<ul>
  <li>
    <strong>Submit Build to Google Container Registry:</strong>
    <pre><code>gcloud builds submit --tag gcr.io/mldeployflask/continuous-deployment --project=mldeployflask</code></pre>
  </li>

  <li>
    <strong>Deploy to Google Cloud Run:</strong>
    <pre><code>gcloud run deploy continuous-deployment --image gcr.io/mldeployflask/continuous-deployment --platform managed --project=mldeployflask --allow-unauthenticated --region us-east1</code></pre>
  </li>

  <li>
    <strong>List Service Accounts:</strong>
    <pre><code>gcloud iam service-accounts list --project=mldeployflask</code></pre>
    <p>(To view the service accounts associated with the project)</p>
  </li>

  <li>
    <strong>Create Service Account Key:</strong>
    <pre><code>gcloud iam service-accounts keys create ./keys.json --iam-account github-actions@mldeployflask.iam.gserviceaccount.com</code></pre>
    <p>(To create a key for the chosen Google Cloud service account, which will be used for GitHub CI/CD pipeline purposes)</p>
  </li>
</ul>

<p>Here, <strong>mldeployflask</strong> is the GCP project ID and <strong>continuous-deployment</strong> is the Cloud Run Service Name.</p>




<h2> Github CI/CD pipeline: </h2>



![Github CICD](https://github.com/surajsts/Car-mpg-prediction-model-Deployment/blob/05657204ec40cf088b73db41e2f9654cf2cbf1d9/Images/GithubCICD.png)




<h2> Conditional Deployment: </h2>



Conditional deployment of the ML model is ensured to prevent the deployment of the model in the CI/CD pipeline unless the commit message begins with <strong> "[deploy-now]" </strong> string.
 

![Cond deploy](https://github.com/surajsts/Car-mpg-prediction-model-Deployment/blob/8ac8ff0369fd51d0c2aa8f6e3c3ae563268aa3d1/Images/ConditionalDeployment.png)




<h2> Google Cloud Run Service: </h2>



The <strong>"continuous-deployment-cicd" </strong> is the cloud run service, after the successful deployment.


![Cloud Run](https://github.com/surajsts/Car-mpg-prediction-model-Deployment/blob/8ac8ff0369fd51d0c2aa8f6e3c3ae563268aa3d1/Images/CloudRunService.png)




<h2> Deployed Model: </h2>



![Cloud Run](https://github.com/surajsts/Car-mpg-prediction-model-Deployment/blob/ef707f59b1d54d81fa7f57d4dde8a2a8e57cabd5/Images/DeployedModel.png)