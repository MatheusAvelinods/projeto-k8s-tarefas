# Projeto Final: Sistema de Tarefas em Kubernetes

Este projeto consiste em uma aplicação de Lista de Tarefas distribuída em microsserviços, orquestrada pelo Kubernetes.

## 🏗 Arquitetura

A aplicação é composta por 3 serviços principais:
1.  **Frontend:** Desenvolvido em React, servido via Nginx (Multi-stage build).
2.  **Backend:** API REST desenvolvida em Node.js/Express.
3.  **Banco de Dados:** MongoDB.

## 📋 Pré-requisitos

* Docker Desktop (com Kubernetes habilitado)
* Kubectl
* Conexão com a internet (para baixar as imagens do Docker Hub)

## 🚀 Como Executar

1.  **Clone o repositório:**
    ```bash
    git clone https://github.com/MatheusAvelinods/projeto-k8s-tarefas
    cd projeto-kubernetes-final
    ```

2.  **Aplique os manifestos do Kubernetes:**
    Navegue até a pasta raiz do projeto e execute:
    ```bash
    kubectl apply -f k8s/
    ```

3.  **Verifique os Pods:**
    Aguarde até que todos os pods estejam com status `Running`:
    ```bash
    kubectl get pods
    ```

4.  **Acesse a Aplicação:**
    * **Frontend:** Abra seu navegador em `http://localhost` (ou `http://localhost:80`).
    * **Backend:** A API estará disponível em `http://localhost:3003`.

## 🛠 Tecnologias e Requisitos Atendidos

* [x] **DockerFiles:** Criados para Backend e Frontend.
* [x] **Multi-stage Build:** Utilizado no Dockerfile do Frontend.
* [x] **Docker Hub:** Imagens publicadas publicamente.
* [x] **Kubernetes Deployments & Services:** Arquivos na pasta `/k8s`.
* [x] **Variáveis de Ambiente:** Backend configurado via `MONGO_URI` e `PORT`.
* [x] **Persistência:** Banco de dados MongoDB integrado ao cluster.

## 📂 Estrutura de Pastas

* `/backend`: Código fonte da API Node.js.
* `/frontend`: Código fonte da interface React.
* `/k8s`: Manifestos Kubernetes (Deployments e Services).
