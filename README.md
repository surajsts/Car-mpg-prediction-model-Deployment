# Google-Cloud-Platform-Deployment

gcloud commands used:

1) 
gcloud builds submit --tag gcr.io/mldeployflask/continuous-deployment --project=mldeployflask

2) 
gcloud run deploy continuous-deployment --image gcr.io/mldeployflask/continuous-deployment --platform managed --project=mldeployflask --allow-unauthenticated --region us-east1

3) 
gcloud iam service-accounts list --project=mldeployflask  
(To view the service accounts associated with the project)

4) 
gcloud iam service-accounts keys create ./keys.json --iam-account github-actions@mldeployflask.iam.gserviceaccount.com
(To create key for the chosen google cloud service account, which will be used for Github CI/CD pipeline purposes)

Here, "mldeployflask" is the GCP project ID and "continuous-deployment" is the Cloud Run Service Name. 


![Github CICD] (https://github.com/surajsts/Car-mpg-prediction-model-Deployment/blob/05657204ec40cf088b73db41e2f9654cf2cbf1d9/Images/GithubCICD.png)
