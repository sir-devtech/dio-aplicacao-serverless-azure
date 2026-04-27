# dio-aplicacao-serverless-azure

# Sistema de Processamento Serverless com Azure Logic Apps e Functions

Este projeto demonstra a implementação de uma arquitetura serverless na Microsoft Azure para o processamento de dados de funcionários. A solução utiliza um fluxo de trabalho automatizado que recebe dados via HTTP, armazena-os em uma fila de mensagens e os processa utilizando uma Azure Function.

## 🏗️ Arquitetura do Projeto

A solução foi desenhada seguindo os princípios de escalabilidade e baixo custo (Pay-per-use):

1.  **Gatilho (HTTP Request):** Um endpoint que recebe um JSON com informações de funcionários (Nome e Profissão).
2.  **Orquestração (Azure Logic Apps):** Captura a requisição e encaminha o corpo da mensagem para uma fila.
3.  **Mensageria (Azure Queue Storage):** Atua como um buffer, garantindo que nenhuma mensagem seja perdida caso o volume de requisições aumente.
4.  **Processamento (Azure Function):** Uma função disparada automaticamente assim que uma nova mensagem chega à fila, pronta para realizar o processamento lógico.

## 🚀 Tecnologias Utilizadas

* **Microsoft Azure**
* **Azure Logic Apps** (Fluxo de Trabalho)
* **Azure Queue Storage** (Mensageria)
* **Azure Functions** (.NET 8 In-process)
* **JSON** (Formato de dados)

## 📸 Demonstração da Implementação

### 1. Fluxo no Logic App
O Logic App foi configurado para receber o JSON e conectar-se ao Storage Account para depositar a mensagem na fila.

*(Adicione aqui o print do seu Logic App salvo)*

### 2. Infraestrutura de Funções
Criação do Function App utilizando o plano de consumo (Serverless) para otimização de recursos.

*(Adicione aqui o print da tela de sucesso da criação do Function App)*

### 3. Trigger de Fila (Azure Function)
Implementação da função que monitora a `fila-funcionarios` em tempo real.

*(Adicione aqui o print do código da sua função no portal)*

## 🛠️ Como Executar

1.  Envie uma requisição POST para a URL gerada pelo Logic App.
2.  O corpo da requisição deve seguir este formato:
    ```json
    {
      "nome": "Seu Nome",
      "profissao": "Sua Profissão"
    }
    ```
3.  Monitore a Azure Function para visualizar o processamento da mensagem.

---
Desenvolvido por **Moisés Santos de Oliveira** no desafio de projeto da DIO.
