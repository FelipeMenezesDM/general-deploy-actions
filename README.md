# General Deploy Actions

## Descrição
Workflows para deploy de aplicações e infraestrutura em ambiente Cloud.

## Suporte
Atualmente os workflows estão disponíveis apenas para deploy no Google Cloud Plataform.

## Uso
Para utilizar, basta realizar sua injeção como um workflow reutilizável no projeto:

1. Crie os diretórios e o arquivo do workflow no seu projeto Laravel:
    ```
    .
    └── .github/
        └── workflows/
            └── custom-workflow.yml
    ```
2. Adicione o conteúdo no workflow do projeto:
    ```yaml
    name: Build and Deploy to GCP - DEV
    on:
      push:
        branches: develop
    jobs:
      ci-cd:
        name: CI/CD
        uses: felipemenezesdm/laravel-deploy-actions/.github/workflows/gcp-app-dev.yml@v1
        secrets: inherit
        with:
          service: ${{ github.event.repository.name }}
          sha: ${{ github.sha }}
    ```
