# Minha Jornada DevOps

Repositório dedicado ao registro de estudos, laboratórios e automações.

### Aula 01: Introdução ao Mundo DevOps e Virtualização
- **Conceito:** Aprendi que DevOps é uma cultura de integração entre Dev e Ops para maior agilidade e segurança.
- **Laboratório:** Instalação do VirtualBox e criação da primeira VM com Ubuntu Server (Ubuntu 25.04).
- **Configurações da VM:**
  - CPU: 2 vCPUs
  - RAM: 4096 MB
  - Disco: 25GB (LVM habilitado)

### Aula 02: Fundamentos de Linux e Acesso Remoto

- **Conceitos:**
  - **Kernel:** O núcleo do sistema operacional.
  - **Escalabilidade de Recursos:** Capacidade de aumentar recursos (CPU/RAM) de um servidor existente.
  - **SSH (Secure Shell):** Protocolo padrão para administração remota de servidores.

- **Comandos Praticados:**
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

### Aula 03: Navegação e Gerenciamento de Arquivos no CLI

- **Comandos Praticados:**
  - `pwd`: Exibe o caminho completo (Path) do diretório atual.
  - `ls -la`: Lista todos os arquivos, incluindo ocultos, com detalhes de permissões, tamanho e proprietário.
  - `cd [diretório]`: Navegação entre pastas do sistema.

- **Informação:**
  - Arquivos ocultos no Linux começam com um ponto (`.`). Eles geralmente guardam configurações críticas de perfil (como o `.bashrc` ou chaves SSH).
  - A flag `-l` é vital para troubleshooting de permissões, permitindo identificar rapidamente se um serviço tem acesso de leitura/escrita em um diretório.
 
- ### Aula 04: Comandos Essenciais e Gestão de Privilégios (SUDO)

- **Comandos de Gerenciamento:**
  - `mkdir [nome]`: Criação de novos diretórios.
  - `history`: Exibe o histórico de comandos.
  - `sudo`: Permite executar tarefas com privilégios de administrador (root).
  - `apt update`: Sincroniza os repositórios para verificar atualizações de segurança e software.

- **Informação:**
  O Shell atua como uma camada de proteção entre o usuário e o Kernel. Ele interpreta os comandos e garante que apenas instruções válidas sejam processadas.

- **Aprendizado sobre Segurança:**
  Entendi a diferença entre o usuário comum (`$`) e o superusuário (`#`). O uso do `sudo` deve ser consciente, seguindo o princípio do privilégio mínimo para evitar alterações acidentais no sistema.
