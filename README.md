# GitHub Actions

## O que é o GitHub Actions?

GitHub Actions é uma plataforma de integração contínua e entrega contínua (CI/CD) 
que permite automatizar a sua compilação, testar e pipeline de implantação. É 
possível criar fluxos de trabalho que criam e testam cada pull request no seu 
repositório, ou implantar pull requests mesclados em produção.

- [Documentação GitHub Actions](https://docs.github.com/pt/actions)
- [Documentação Workflows](https://github.com/actions/starter-workflows)

## Estrutura básica de uma pipeline

- Name (opcional): Nome que irá aparecer na interface web do Github Actions
- Run-name (opcional): Nome que irá aparecer quando a pipe for executada
- On: Gatilho para execução da pipeline
- Jobs: Ações que serão executadas quando a pipeline for trigada.
- env (opcional): Variáveis de ambiente
- [Explicação no workflow:](https://docs.github.com/pt/actions/writing-workflows/about-workflows) learn-github-actions.yml

## Sintaxe de variáveis

- ${{  }}                   --> Sintaxe de variáveis
- ${{ github.actor }}       --> Nome de usuário: viniciusSouss                   
- ${{ github.event_name }}  --> Trigger [on]: push, cron, workflow_dispatch, etc
- ${{ runner.os }}          --> Sistema operacional configurado em “runs-on”
- ${{ github.ref }}         --> Branch de referência
- ${{ github.repository }}  --> Nome do repositório
- ${{ github.workspace }}   --> Lista os arquivos do repositório
- ${{ job.status }}         --> Status do job: success, fail


## Gatilhos de execução
- [Documentação](https://docs.github.com/en/actions/writing-workflows/choosing-when-your-workflow-runs/triggering-a-workflow#using-events-to-trigger-workflows)

#### Gatilho: Push
    - O que é push? 
        É um comando fundamental para enviar seus commits locais para um repositório remoto.

#### Exemplos: 
- 1_basic_on_push.yml
- 2_branch_on_push.yml
- 3_branch_ignore_on_push.yml
- 4_path_on_push.yml
- 5_on_push.yml

#### Observações importantes
- "branches" e "branches-ignore" não podem ser configurados no mesmo arquivo .yml


#### Gatilho: Pull Request
    - O que é Pull request? 
        É a solicitação para merge do código. Durante o pull request pode acontecer a revisão do código levando a alteração de parte do código proposto.

#### Exemplos:
- 1_basic_on_pull_request.yml
- 2_branch_on_pull_request.yml
- 3_type_on_pull_request.yml
- 4_on_pull_request.yml

Opções de "paths" e "branches-ignore" também pode ser usadas aqui.

#### Observações importantes
- Para testar você pode criar outra branch local fazer um commit e depois abrir o Pull Request via GitHub.
- Para testar você pode fazer uma alteração diretamente no GitHub e na hora de salvar escolha a opção de criar outra branch e abrir PR.

#### Gatilho: Workflow dispatch
    - O que é workflow dispatch? 
        É um trigger que permite que um fluxo de trabalho seja disparado manualmente.

#### Exemplos:
- 1_basic_on_workflow_dispatch.yml
- 2_input_choice_on_workflow_dispatch.yml
- 3_input_string_on_workflow_dispatch.yml
- 4_input_bool_on_workflow_dispatch.yml
- 5_on_workflow_dispatch.yml

#### Observações importantes
- Para executa-lo você precisa entrar no GitHub Action e acioná-lo manualmente.

#### Gatilho: Cron Job
    - O que é Cron Job? 
        É um trigger que permite que você agenda a execução de um fluxo de trabalho.

#### Exemplos:
- 1_on_cron.yml

#### Legenda

- minute (0 - 59)
- hour (0 - 23)
- day of the month (1 - 31)
- month (1 - 12 or JAN-DEC)
- day of the week (0 - 6 or SUN-SAT)


#### Observações importantes
- Horário utilizado é UTC (horário do Brasil + 3 horas)
- Use para auxiliar na montagem do cron job: [CronJob Guru](https://crontab.guru/)
- Horário não será exato, depende da disponibilidade do GitHub Actions

#### Gatilho: Workflow run
- [Workflow dispatch documentação](https://docs.github.com/pt/actions/writing-workflows/choosing-when-your-workflow-runs/events-that-trigger-workflows#workflow_run)

#### O que é Workflow run
    É a um trigger que permite que a execução de um fluxo de trabalho seja triggado por meio de outro fluxo de trabalho.
    
#### Exemplos
- 1_basic_on_workflow_run.yml
- 2_types_on_workflow_run.yml
- 3_branch_on_workflow_run.yml
- 4_workflows_on_workflow_run.yml

#### Observações importantes
- Não é possível usar workflow_run para encadear mais de três níveis de fluxos de trabalho
- Podemos usar o filtros para especificar os branches em que o fluxo de trabalho de gatilho precisa ser executado para disparar o fluxo de trabalho:
    - branches
    - branches-ignore


## Configurando variáveis no repositório do GitHub
- [Variáveis](https://docs.github.com/pt/actions/writing-workflows/choosing-what-your-workflow-does/store-information-in-variables)

#### O que é uma varíavel de repositório?
- É uma varíavel configurada no repositório do Github e todos os workflows conseguem utilizada.
- Como esta variável não é protegida, é possível ver seus valor no log de execução

#### Configuração
- Setting
- Secrets and variables
- Actions

#### Exemplos
- 1_config_variaveis_gha.yml