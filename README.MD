
# GCloud Build
- Criar gatilho vinculado a repositorio para observar as alterações
- Possivel marcar somente ramificao main para acionar gatilho
- No menu Historico e possivel acompanhar o status do pipeline
- Interessante criar um gatilho para master e outro pra dev(ramificacao invertida),
e escolher opcao para arquivo especifico (onde um sera pra prod e outro pra dev)

# Git Boas práticas
- Criado no repositorio uma rule para o branch master para fazer o merge
somente quando aprovado usando:
Settings > Branches > Require status check to pass before merging >
Require branches to be up to date before merging > Selecionar gatilho criado no gbuild