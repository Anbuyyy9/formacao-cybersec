🛡️ Conclusão do Laboratório - Desafio CTF: Invasão à Kensei Corp


🧠 Visão Geral

Este laboratório simula um cenário realista de um pentest interno, em que fui desafiado a aplicar uma metodologia de varredura profissional para descoberta de hosts e serviços expostos, seguida por um desafio CTF com cinco flags distribuídas pela rede da Kensei Corp. O objetivo foi aplicar técnicas de reconhecimento, enumeração e exploração básica, reforçando práticas essenciais de um analista Red Team.

🧭 Etapas Realizadas

🔎 Reconhecimento e Enumeração de Hosts

Identificação de redes:

Verifiquei que o container atacante estava conectado às redes DMZ (172.18.0.0/24) e Rede Interna (172.19.0.0/24).

Utilizei o comando ifconfig para validar os IPs atribuídos.

Descoberta de hosts ativos:

Com o nmap -sn, identifiquei quais IPs estavam ativos nas duas redes.

Resultado armazenado via grep "Up" para facilitar a triagem.

Scan de portas e serviços com RustScan:

Para os hosts identificados, utilizei o RustScan com o parâmetro -A (scan completo via Nmap).

Resultados documentados nos arquivos scan_dmz.nmap e scan_interna.nmap.

🚩 Caça às Flags - Desafio CTF

✅ Flag 1: Web Server (DMZ)
Serviço HTTP encontrado na porta 80.

Com o curl, inspecionei o conteúdo da página inicial.

A flag estava embutida no código-fonte HTML.

✅ Flag 2: Mail Server (DMZ)
Porta 25 (SMTP) respondendo com banner de boas-vindas.

Conexão via nc revelou a flag na mensagem do banner.

✅ Flag 3: Fileshare Server (Rede Interna)
Serviço SMB identificado.

Acesso via smbclient (sem autenticação).

Localizei a flag no diretório oculto .secreto dentro do compartilhamento public.

✅ Flag 4: Database Server (Rede Interna)
MySQL exposto com login root e senha em branco.

Naveguei pelo banco com SHOW DATABASES, USE, e SELECT até localizar a flag armazenada em uma tabela.

✅ Flag 5: Dev Machine (Rede Interna)
Porta 1337 oculta identificada via rustscan com range completo.

Conexão via nc revelou a última flag em uma mensagem ao estilo "leet".

🧩 Ferramentas Utilizadas

Ferramenta	            Função
ifconfig	            Identificar interfaces de rede
nmap	                Descoberta de hosts (-sn)
rustscan	            Scan rápido e completo de portas
curl	                Análise de respostas HTTP
nc / telnet	            Interação com portas abertas
smbclient            	Enumeração e acesso a compartilhamentos SMB
mysql	                Acesso e exploração de banco de dados

🏁 Conclusão
Finalizei com sucesso todas as etapas do laboratório e capturei as 5 flags do desafio CTF. Esse exercício reforçou minha habilidade de:

Identificar ativos expostos e suas vulnerabilidades.

Navegar entre redes simuladas com múltiplos serviços.

Aplicar a lógica de exploração baseada em enumeração técnica.

A prática reforça um ponto importante: um bom pentest começa com uma excelente fase de reconhecimento. A disciplina na coleta e análise de dados é o que torna um ataque possível — e, mais importante, determinável e rastreável em ambientes reais.

