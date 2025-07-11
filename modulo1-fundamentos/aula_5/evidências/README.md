🧠 Relatório de Reconhecimento – Lab 5

🕉 Alvo

O alvo está no container lab_target, que simula um servidor Apache com arquivos e diretórios acessíveis via HTTP.

🎯 Vetor Inicial

O reconhecimento começou com uma requisição curl simples para confirmar se o servidor estava online e responderia a conexões HTTP.

🔍 Ferramentas e Resultados

1. curl lab_target

Confirmou que o alvo responde com página ativa.
Resultado:

<html><body><h1>It works!</h1></body></html>

2. gobuster dir -u http://lab_target/ -w /usr/share/wordlists/dirb/common.txt -t 20

Foram descobertos diretórios e arquivos:

/index.html (200 OK)

/vault (301 Redirect)

/vault/flag.txt (200 OK)

3. curl -i http://lab_target/vault/flag.txt

Flag descoberta:

FLAG-{RECON-STARTS-WITH-OSINT}

4. Validação da flag com hash SHA256

echo -n "FLAG-{RECON-STARTS-WITH-OSINT}" | sha256sum

Hash gerado:

967e3e3cc8ac1556182724c32115a85745db159c147dd32f7d13313fad0febb3

🗺️ Análise

O diretório /vault redirecionava corretamente, e o arquivo flag.txt continha a flag principal do lab. O reconhecimento inicial foi suficiente para localizar a vulnerabilidade de exposição direta da flag.

🔢 Conclusão

Neste desafio foi possível:

Confirmar a existência do alvo com curl

Enumerar diretórios com gobuster

Descobrir e validar uma flag real exposta via HTTP

🔒 Flag capturada com sucesso!

FLAG-{RECON-STARTS-WITH-OSINT}