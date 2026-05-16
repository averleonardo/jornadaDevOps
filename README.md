# Minha Jornada DevOps

Repositório dedicado ao registro de estudos, laboratórios e automações.

## Aula 01: Fundamentos e Linux

### Aula 01: Introdução ao Mundo DevOps e Virtualização
- **Conceito:** Aprendi que DevOps é uma cultura de integração entre Dev e Ops para maior agilidade e segurança.
- **Laboratório:** Instalação do VirtualBox e criação da primeira VM com Ubuntu Server (Ubuntu 25.04).
- **Configurações da VM:**
  - CPU: 2 vCPUs
  - RAM: 4096 MB
  - Disco: 25GB (LVM habilitado)

### Aula 02: Fundamentos de Linux e Acesso Remoto
Nesta etapa, explorei a arquitetura do Linux e a importância da escalabilidade em ambientes corporativos.

- **Conceitos Chave:**
  - **Kernel:** O núcleo do sistema operacional.
  - **Escalabilidade de Recursos:** Capacidade de aumentar recursos (CPU/RAM) de um servidor existente.
  - **SSH (Secure Shell):** Protocolo padrão para administração remota de servidores.

- **Mão na Massa:**
  1. Configuração da placa de rede da VM para permitir comunicação com o host.
  2. Identificação do endereço IP através do comando: `ip address`.
  3. Acesso remoto via terminal Windows (CMD) usando o comando:
     ```bash
     ssh usuario@192.168.x.x
     ```
**Resolução de Problemas:**
  Durante a configuração do acesso remoto, enfrentei o erro `Permission Denied`. O processo de correção foi documentado detalhadamente no arquivo específico deste repositório:
  - [Consulte aqui o Guia de Correção: FIX-SSH-PERMISSION-DENIED.md](./FIX-SSH-PERMISSION-DENIED.md)

- **Resultado:** Ambiente de laboratório acessível remotamente
