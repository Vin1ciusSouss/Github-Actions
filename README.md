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