# 📦 Projeto Docker Lab #6: Explorando a Rede – Infraestrutura e Comandos Essenciais

Este projeto contém o ambiente Docker para o **Laboratório #6** da Formação CyberSec. O foco é entender como funcionam comandos de rede essenciais em um ambiente isolado e simulado.

---

## 🎯 Objetivos do Lab

- Utilizar comandos como `ping`, `traceroute` e `dig` dentro de um container Kali Linux.
- Simular resolução de nomes via DNS customizado com CoreDNS.
- Entender a infraestrutura e a comunicação de rede entre containers Docker.

---

## 📋 Pré-requisitos

- [Docker Desktop](https://www.docker.com/products/docker-desktop) (Windows/macOS) ou Docker Engine (Linux)
- [Git](https://git-scm.com/downloads)
- [WSL 2](https://learn.microsoft.com/pt-br/windows/wsl/install) (para usuários Windows sem Docker Desktop)

---

## 🚀 Setup do Lab

```bash
# Clone o repositório principal do curso (caso ainda não tenha)
git clone https://github.com/Kensei-CyberSec-Lab/formacao-cybersec.git

# Navegue até o diretório da aula
cd formacao-cybersec/modulo1-fundamentos/aula_6

# Construa a imagem do Kali Linux e suba o ambiente
docker compose up --build -d

# Verifique se os containers estão rodando
docker ps
    