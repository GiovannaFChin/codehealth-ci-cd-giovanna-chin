# CodeHealth - sistema web de agendamento médico
O CodeHealth é um sistema web de agendamento médico que tem como objetivo oferecer uma plataforma segura e eficiente para marcação de consultas, gerenciamento de pacientes e integração com profissionais de saúde.

Para garantir qualidade, agilidade e confiabilidade nas entregas, a equipe adotou uma cultura DevOps, implementando um pipeline automatizado de Integração Contínua (CI) e Entrega Contínua (CD).

## Objetivos do Pipeline

Automatizar o processo de build, teste e deploy.

Detectar falhas precocemente por meio de testes automatizados.

Manter a consistência entre os ambientes (desenvolvimento, homologação e produção).

Garantir entregas contínuas e seguras com rollback rápido em caso de falhas.

## Pipeline de CI/CD (Fluxo Resumido)
1️. Integração Contínua (CI)

Evento de gatilho: push ou pull request para o branch develop ou main.

Etapas:

1.Checkout do código
O código é baixado do repositório para o ambiente de build.

2.Instalação de dependências
Instala bibliotecas conforme o requirements.txt (backend) e package.json (frontend).

3.Execução dos testes automatizados
Roda testes unitários e de integração com relatório de cobertura.

4.Análise de qualidade de código
Usa ferramentas como flake8 (Python) e eslint (JavaScript) para manter padrões.

5.Build da aplicação
Gera a imagem Docker da aplicação.

2. Entrega Contínua (CD)

Evento de gatilho: merge no branch main com pipeline de CI bem-sucedido.

Etapas:

1.Push da imagem Docker para o Docker Hub ou GitHub Container Registry.

2.Deploy automatizado em ambiente de homologação (staging).

3.Testes de smoke para verificar se o deploy foi bem-sucedido.

4.Deploy em produção (manual approval stage).

