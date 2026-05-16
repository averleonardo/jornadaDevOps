Documentação de causa raiz e resolução para falhas de login em instâncias Ubuntu recém-provisionadas.

## Troubleshooting: SSH Auth Resolution (Ubuntu Minimized)

## Diagnóstico
## 1. PasswordAuthentication desabilitado por padrão no sshd_config.
## 2. Conflito de Layout (US vs ABNT2) na criação da senha via console local.

## Configuração do Daemon
sudo nano /etc/ssh/sshd_config

## Ajustar diretivas para:
## PasswordAuthentication yes
## KbdInteractiveAuthentication yes
## UsePAM yes

## Reinicialização do Serviço
sudo systemctl restart ssh

## Redefinição de Credenciais
## (Evitar caracteres especiais devido ao conflito de layout no console local)
sudo passwd [usuario]

## Monitoramento de Logs (Real-time Debug)
sudo journalctl -u ssh -f
