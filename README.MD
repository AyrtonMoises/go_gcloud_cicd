
# GCloud Build CI/CD para GCloud Run


## Habilitando acesso do GCloud Build ao GCloud Run para implantar projeto  
```
gcloud run services add-iam-policy-binding [CLOUD_RUN_SERVICE_NAME] \ 
  --member=serviceAccount:[CLOUD BUILD SERVICE ACCOUNT EMAIL] \
  --role=roles/run.admin \
  --project=$PROJECT \
  --region=$REGION
```
```
gcloud iam service-accounts add-iam-policy-binding [SERVICE ACCOUNT THAT CLOUD RUN RUNS AS] \
  --member=serviceAccount:[CLOUD BUILD SERVICE ACCOUNT] \
  --role roles/iam.serviceAccountUser
  --project=$PROJECT \
  --region=$REGION
```
