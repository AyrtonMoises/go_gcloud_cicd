
# GCloud Build CI/CD para GCloud Run

## GCloud Build
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


## Git Boas práticas
- Criado no repositorio uma rule para o branch master para fazer o merge
somente quando aprovado usando:
-Settings > Branches > Require status check to pass before merging >
Require branches to be up to date before merging > Selecionar gatilho criado no gbuild
para o branch development
-Então apos subir um codigo na branch dev com erro, e criar um pull request para fazer o merge na master, o app do gcloud no git vai bloquear pois teve erro(so admin consegue forçar)(se arrumar o erro, e voltar pra PR que deu erro ela vai estar disponivel pro merge)
-Apos dar o PR, o gatilho no gbuild para master sera acionado com a pipeline automaticamente
- Boa pratica tambem limitar o push para master somente via pull request nas configurações
do repositório