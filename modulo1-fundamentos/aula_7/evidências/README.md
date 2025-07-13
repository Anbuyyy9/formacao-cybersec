# 🕵️‍♂️ Lab da Aula 7: Análise de Tráfego com Wireshark

Este lab prático foi realizado como parte da formação em cibersegurança. O foco foi aprender a **capturar e analisar pacotes de rede** utilizando o Wireshark em um ambiente Docker com um servidor web e um contêiner Kali Linux.

## 🎯 Objetivos

- Instalar e configurar o Wireshark.
- Capturar o tráfego gerado por um servidor web local e Kali em Docker.
- Identificar o Three-Way Handshake (TCP).
- Analisar requisições HTTP (GET e POST).
- Observar tráfego DNS e ICMP.
- Aplicar filtros para refinar a análise.

## 🧪 Ambiente

- **Host:** Windows 11 com Docker Desktop e Wireshark instalados.
- **Contêineres Docker:**
  - `web-server-aula7` (porta 8080)
  - `kali-aula7`
- **Interface usada no Wireshark:** `vEthernet (Default Switch)` (para interceptar tráfego local entre containers).

## ⚙️ Tecnologias

- Docker
- Wireshark
- Kali Linux (em container)
- Servidor Web Python/Werkzeug

## 🔍 Atividades Realizadas

- Acesso ao servidor web via navegador (`localhost:8080`) e via `curl` no Kali.
- Captura e análise do Handshake TCP.
- Inspeção de requisições HTTP GET e POST.
- Verificação de dados sensíveis (usuário/senha) trafegando em texto claro.
- Análise de pacotes DNS (nslookup).
- Aplicação de filtros no Wireshark:
  - `tcp.port == 8080`
  - `http.request.method == "POST"`
  - `icmp`
  - `dns`

## 🧠 Aprendizado

Este lab demonstrou, na prática, como tráfegos comuns podem ser visualizados e analisados, reforçando a importância de protocolos seguros como HTTPS. Também permitiu observar a estrutura dos pacotes em profundidade.

## 🧹 Finalização

```bash
docker compose down
