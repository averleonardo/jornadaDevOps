# Minha Jornada DevOps

Repositório dedicado ao registro de estudos, laboratórios e automações.

### Introdução ao Mundo DevOps e Virtualização
- **Conceito:** Aprendi que DevOps é uma cultura de integração entre Dev e Ops para maior agilidade e segurança.
- **Laboratório:** Instalação do VirtualBox e criação da primeira VM com Ubuntu Server (Ubuntu 25.04).
- **Configurações da VM:**
  - CPU: 2 vCPUs
  - RAM: 4096 MB
  - Disco: 25GB (LVM habilitado)

### Fundamentos de Linux e Acesso Remoto

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

### Navegação e Gerenciamento de Arquivos no CLI

- **Comandos Praticados:**
  - `pwd`: Exibe o caminho completo (Path) do diretório atual.
  - `ls -la`: Lista todos os arquivos, incluindo ocultos, com detalhes de permissões, tamanho e proprietário.
  - `cd [diretório]`: Navegação entre pastas do sistema.

- **Informação:**
  - Arquivos ocultos no Linux começam com um ponto (`.`). Eles geralmente guardam configurações críticas de perfil (como o `.bashrc` ou chaves SSH).
  - A flag `-l` é vital para troubleshooting de permissões, permitindo identificar rapidamente se um serviço tem acesso de leitura/escrita em um diretório.
 
- ### Comandos Essenciais e Gestão de Privilégios (SUDO)

- **Comandos de Gerenciamento:**
  - `mkdir [nome]`: Criação de novos diretórios.
  - `history`: Exibe o histórico de comandos.
  - `sudo`: Permite executar tarefas com privilégios de administrador (root).
  - `apt update`: Sincroniza os repositórios para verificar atualizações de segurança e software.

- **Informação:**
  O Shell atua como uma camada de proteção entre o usuário e o Kernel. Ele interpreta os comandos e garante que apenas instruções válidas sejam processadas.

- **Aprendizado sobre Segurança:**
  Entendi a diferença entre o usuário comum (`$`) e o superusuário (`#`). O uso do `sudo` deve ser consciente, seguindo o princípio do privilégio mínimo para evitar alterações acidentais no sistema.

### Manipulação de Arquivos e Edição de Texto

- **Comandos de Manipulação:**
  - `touch [arquivo.txt]`: Criação rápida de arquivos vazios.
  - `nano`: Editor de texto via terminal, essencial para alterar arquivos de configuração.
  - `tar -czf`: Utilizado para compactação de volumes e criação de backups.
  - `mv` / `cp`: Comandos para movimentação e cópia de arquivos/diretórios.

- **Redirecionamento de Saída (I/O Redirection):**
  Pratiquei a diferença crucial entre os operadores de escrita, fundamental para automação de scripts e logs:
  - `>` (**Sobrescrever**): Substitui todo o conteúdo do arquivo pelo novo texto.
  - `>>` (**Anexar**): Adiciona o novo texto ao final do arquivo, preservando os dados existentes.

- **Gestão de Riscos (Remoção Definitiva):**
  No Linux Server, a remoção é definitiva (não existe lixeira). O uso do comando `rm` exige atenção redobrada:
  - `rm [arquivo]`: Remove um arquivo específico.
  - `rmdir [diretório]`: Remove apenas diretórios que estejam **completamente vazios**.
  - `rm -r [diretório]`: Remoção **recursiva**, deletando o diretório e todo o seu conteúdo interno.
  
  **Boa prática:** Sempre valide o diretório atual com o comando `pwd` antes de executar uma remoção recursiva para evitar deleções acidentais em caminhos errados.


  ### Desafio Prático.Estruturação de Projetos:
Simulação de estruturação de diretórios para um aplicativo educacional em ambiente de Software House.

- **Cenário:** Criação de estrutura hierárquica e movimentação de arquivos fonte e testes.
- **Resolução do Problema:**
  - Utilização do `mkdir -p` para criação de pastas aninhadas (`app/src` e `app/tests`) em um único comando, garantindo que os diretórios "pai" fossem gerados automaticamente.
  - Uso do comando `mv` para organizar arquivos `.py` conforme a arquitetura proposta.

- **Informação:**
  A organização lógica de diretórios (src, tests, docs) é um padrão de mercado que facilita a implementação de esteiras de **CI/CD**, permitindo que ferramentas automatizadas saibam exatamente onde encontrar o código e os testes.


### Aula 07: Filtros e Wildcards (Coringas) no CLI
Aprendi a utilizar metacaracteres para filtrar saídas do comando `ls` para lidar com grandes volumes de dados.

- **Comandos Praticados:**
  - `*` (Asterisco): Representa qualquer quantidade de caracteres. Ex: `ls arc*` traz `arcf1`, `arcf40`, etc.
  - `?` (Interrogação): Representa exatamente um caractere curinga.
  - `[ ]` (Colchetes): Permite definir um intervalo. Ex: `ls data[1-5]` listaria data1 até data5.

- **Informação:**
  Essa técnica é utilizada em scripts de limpeza de logs (ex: `rm log_2024*.log`) ou em backups automáticos de arquivos com extensões específicas.
