# Web Chat 🗨️

Este projeto é uma aplicação interativa de chat em tempo real construída com Ruby on Rails (API) e Vue.js (Frontend) e orquestrada via Docker Compose.

## Propósito

Fornecer uma plataforma de comunicação em tempo real, permitindo que usuários troquem mensagens de forma interativa.

## Arquitetura

O projeto é composto por três partes principais:

* **[Chat API](https://github.com/weslley6216/chat_api):**
  * Uma API RESTful construída com Ruby on Rails, responsável pela lógica de negócios e persistência de dados.
* **[Chat Frontend](https://github.com/weslley6216/chat_frontend):**
  * Uma aplicação web construída com Vue.js, que fornece a interface de usuário para o chat.
* **Web Chat (Módulo Git):**
  * Este repositório, que orquestra a execução da API e do Frontend via Docker Compose.

O fluxo de dados é o seguinte:

1. O Frontend se comunica com a API para autenticação e obtenção de dados.
2. A comunicação em tempo real é feita via WebSockets, utilizando Action Cable.

## Configuração e Execução

1. Certifique-se de ter o Docker instalado localmente.
2. Clone este repositório:

    ```bash
    git clone git@github.com:weslley6216/web_chat.git
    ```

3. Navegue até o diretório do projeto:

    ```bash
    cd web_chat
    ```

4. Execute o seguinte comando para inicializar os submodules:

    ```bash
    git submodule update --init --recursive
    ```

5. Copie o arquivo `.env.example` para `.env` para configurar as variáveis de ambiente:

    ```bash
    cp .env.example .env
    ```

6. Execute o projeto com Docker Compose:

    ```bash
    docker compose up
    ```

## Chat em Tempo Real

Para testar a funcionalidade de chat em tempo real, siga os passos abaixo:

1. Abra o navegador em uma janela normal e acesse:

    ```bash
    http://localhost:4000
    ```

2. Faça login com o seguinte usuário:

    ```bash
    username: alice
    password: 123456
    ```

3. Abra uma aba anônima ou outro navegador de sua preferência e também acesse:

    ```bash
    http://localhost:4000
    ```

4. Faça login com o seguinte usuário:

    ```bash
    username: bob
    password: 123456
    ```

5. Comece a trocar mensagens entre os usuários para testar a comunicação em tempo real.

## Criação de Usuário

Caso deseje criar um novo usuário para testes, siga os passos abaixo:

1. Abra o navegador e acesse a página de registro:

    ```bash
    http://localhost:4000/register
    ```

2. Preencha o formulário de registro com os dados desejados e clique em "Register".
3. Após o registro, o login será realizado automaticamente.
4. Ao clicar em "Novo Chat", será exibida uma lista de usuários previamente cadastrados via seeds.
5. Selecione o usuário desejado da lista para iniciar um novo bate-papo.

## Comandos Adicionais

Após rodar um `docker compose up`, abra uma nova instância no terminal e execute um dos passos abaixo:

* **Executar testes RSpec (API):**

    ```bash
    docker compose exec chat_api rspec
    ```

* **Executar testes Vitest (Frontend):**

    ```bash
    docker compose exec chat_frontend yarn test
    ```

* **Abrir um shell Bash na API:**

    ```bash
    docker compose exec chat_api bash
    ```

* **Abrir um shell Bash no Frontend:**

    ```bash
    docker compose exec chat_frontend bash
    ```

## Informações Adicionais

Para obter informações detalhadas sobre dependências de desenvolvimento, endpoints da API, tecnologias do frontend, testes e implantação, futuras funcionalidades, consulte os READMEs específicos dos seguintes projetos:

* **[Chat API](https://github.com/weslley6216/chat_api)**
* **[Chat Frontend](https://github.com/weslley6216/chat_frontend)**
