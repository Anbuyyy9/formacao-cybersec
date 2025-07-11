# 🧠 Relatório de Reconhecimento – Lab

## 🧩 Alvo
O alvo está no container `lab_target`, simula um servidor web com Python/Werkzeug.

## 🎯 Vetor Inicial
O primeiro passo foi um `ping` para confirmar se o host estava ativo na rede Docker.

## 🔍 Ferramentas e Resultados

### 1. ping -c1 lab_target
Confirmou que o alvo responde a ICMP.

### 2. nmap -sS -sV -O lab_target
Identificou:
- Porta 80 aberta
- Serviço HTTP rodando Werkzeug/2.3.0
- SO presumido: Linux

### 3. curl -I http://lab_target/
Revelou cabeçalhos HTTP:
- Server: Werkzeug/2.3.0
- Python/3.11

### 4. gobuster dir ...
Foram descobertos diretórios ocultos:
- `/secret`

## 🧭 Próximos Passos
- Verificar o conteúdo de `/secret`
- Realizar fuzzing nos parâmetros, tentar detectar vulnerabilidades web


🔒 Conclusão sobre /secret
Teste	Resultado
RCE (os.popen)	❌ Não
XSS (<script>)	❌ Não
Interpretação matemática	❌ Não
Reflected Input	✅ Sim (mas inofensivo aqui)

