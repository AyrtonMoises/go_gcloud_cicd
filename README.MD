
# GCloud Build CI/CD para GCloud Run
- Criar gatilho vinculado a repositorio para observar as alterações
- Possivel marcar somente ramificao X para acionar gatilho
- Interessante criar um gatilho para master e outro pra dev(com ramificacao invertida da branch),e escolher para dev a opcao para arquivo especifico (onde um sera pra prod e outro pra dev)
- No menu Historico e possivel acompanhar o status do pipeline

# Git Boas práticas
- Criado no repositorio uma rule para o branch master para fazer o merge
somente quando aprovado usando:
-Settings > Branches > Require status check to pass before merging >
Require branches to be up to date before merging > Selecionar gatilho criado no gbuild
para o branch development
-Então apos subir um codigo na branch dev com erro, e criar um pull request para fazer o merge na master, o app do gcloud no git vai bloquear pois teve erro(so admin consegue forçar)(se arrumar o erro, e voltar pra PR que deu erro ela vai estar disponivel pro merge)
-Apos dar o PR, o gatilho no gbuild para master sera acionado com a pipeline automaticamente