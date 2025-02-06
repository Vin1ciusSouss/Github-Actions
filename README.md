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
