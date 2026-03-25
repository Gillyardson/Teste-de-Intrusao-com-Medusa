# Teste-de-Intrusão-com-Medusa

🛡️Este projeto demonstra a execução de ataques de força bruta e password spraying em um ambiente controlado, 
focando na identificação de vulnerabilidades e implementação de defesas.

🏗️ 1. Configuração do Laboratório (Lab Setup)..

Para garantir a segurança, o ambiente é 100% isolado via VirtualBox/VMware.

•	Atacante: Kali Linux 🐉 (IP: 192.168.56.10)..
•	Alvo: Metasploitable 2 🎯 (IP: 192.168.56.11)..
•	Rede: Modo Host-Only (comunicação interna sem exposição à internet)..

⚔️ 2. Execução dos Ataques
📂 Ataque 01: Força Bruta em FTP
Utilizamos o Medusa para adivinhar a senha do serviço de transferência de arquivos.

•	Ferramenta: medusa com módulo -M ftp.
•	Estratégia: Testar a wordlist rockyou.txt contra o usuário msfadmin.

🌐 Ataque 02: Formulário Web (DVWA)
Foco em quebrar a autenticação de uma aplicação web vulnerável.
•	Diferencial: Configuração de cookies e identificação da mensagem de erro (Login failed) para validar o sucesso do ataque.

👥 Ataque 03: Password Spraying em SMB
Técnica furtiva para evitar bloqueio de contas.
•	Passo 1: Enumeração de usuários via nmap.
•	Passo 2: Testar uma única senha comum contra vários usuários simultaneamente.

📊 3. Validação dos Resultados
O sucesso é confirmado quando o Medusa retorna a flag [SUCCESS].
Alvo (Serviço)	Usuário	Wordlist	Resultado
FTP (21)	msfadmin	rockyou.txt	✅ Sucesso
HTTP (DVWA)	admin	custom.txt	✅ Sucesso
SMB (445)	user_list	spray_list	🔄 Variável

🛡️ 4. Medidas de Prevenção (Mitigação)
Para proteger sistemas reais contra essas técnicas, recomendamos:
•	🚫 Bloqueio de Conta: Impedir novas tentativas após 3-5 falhas.
•	🔐 MFA (Autenticação Multi-fator): A barreira mais eficaz contra roubo de senhas.
•	🔠 Complexidade: Exigir senhas fortes e únicas.
•	👁️ Monitoramento (SIEM): Alertar sobre picos de falhas de login.
•	🤖 CAPTCHA: Dificultar a automação por ferramentas como o Medusa.


[Teste de Intrusão o com Medusa.pdf](https://github.com/user-attachments/files/26252888/Teste.de.Intrusao.o.com.Medusa.pdf)
