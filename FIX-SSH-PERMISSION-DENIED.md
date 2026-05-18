# FIX: Resolução de Falhas de Autenticação SSH (Ubuntu Server)

Documentação de causa raiz e resolução para falhas de login em instâncias Ubuntu recém-provisionadas.

### Erro Identificado
Ao tentar o acesso remoto via SSH, o servidor retorna a mensagem `Permission denied (publickey,password)`, impedindo a conexão mesmo com as credenciais teoricamente corretas.

### Causa Raiz
O problema geralmente ocorre devido a dois fatores combinados em instalações limpas do Ubuntu Server:
1. **Configuração de Segurança:** Por padrão, o daemon do SSH pode vir configurado para aceitar apenas chaves públicas, bloqueando a autenticação por senha (`PasswordAuthentication no`).
2. **Conflito de Layout de Teclado:** Divergência entre o layout do console local (comumente US) e o teclado físico (ABNT2) no momento da criação da senha, resultando em caracteres incorretos na base de dados.

### Solução

#### 1. Ajuste no Daemon do SSH
Acesse o console local da VM e edite o arquivo de configuração do serviço:
!```bash
sudo nano /etc/ssh/sshd_config

#### 2. Configuração das Diretrizes
Certifique-se de que as seguintes linhas estejam configuradas como yes:

PasswordAuthentication yes

KbdInteractiveAuthentication yes

UsePAM yes

#### 3. Reinicialização do Serviço
Aplique as alterações reiniciando o daemon para que as novas regras entrem em vigor:

Bash
sudo systemctl restart ssh
#### 4. Redefinição de Credenciais
Para mitigar erros de layout de teclado, redefina a senha utilizando caracteres simples:

Bash
sudo passwd [seu_usuario]
#### 5. Monitoramento de Logs (Real-time Debug)
Caso o erro persista, utilize o comando abaixo para monitorar as tentativas de login em tempo real:

Bash
sudo journalctl -u ssh -f
