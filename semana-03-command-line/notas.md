# Semana 03 — Command Line & Shell

## Objetivo

Aprofundar o domínio da linha de comando (CLI), começando pelo **Windows Command Line (cmd.exe)**, entender os diferentes tipos de shell e sua importância para atuação em Cibersegurança/SOC, usando o TryHackMe como ambiente prático.

## Tarefas

- [ ] Completar a sala "Windows Command Line" no TryHackMe
- [ ] Documentar prática com evidências (screenshots)
- [ ] Atualizar glossario.md com novos termos
- [ ] Completar demais salas do módulo Command Line (Linux)

## Conteúdo teórico — Command Line / Shell

### O que é uma Shell?

A **shell** é o programa que atua como interface entre o usuário e o sistema operacional, interpretando comandos digitados e traduzindo-os em ações executadas pelo kernel. É através da shell que interagimos com o sistema via **CLI (Command Line Interface)** — uma alternativa totalmente baseada em texto à GUI (Graphical User Interface).

### CLI vs. GUI: por que a linha de comando importa em Cibersegurança

| Aspecto | GUI | CLI |
|---|---|---|
| Velocidade | Requer múltiplos cliques | Um comando resolve várias ações |
| Uso de recursos | Mais pesado (renderização gráfica) | Leve, ideal para servidores sem interface gráfica |
| Automação | Difícil de automatizar | Nativa via scripts |
| Ambientes reais de SOC/servidores | Raramente disponível | Praticamente onipresente |

Na prática profissional de SOC, administração de servidores e resposta a incidentes, a maioria dos sistemas **não tem interface gráfica** — o analista precisa navegar, investigar logs e agir exclusivamente via terminal. Por isso, fluência em CLI é um requisito não-negociável em vagas de Cibersegurança.

### O Command Prompt (cmd.exe)

O **cmd.exe** é o interpretador de linha de comando legado do Windows, presente desde o MS-DOS. Mesmo com o surgimento do PowerShell (mais moderno), o CMD continua relevante porque:
- Ainda é amplamente usado em ambientes corporativos legados
- É frequentemente o primeiro ponto de acesso em investigações forenses e resposta a incidentes em máquinas Windows
- Muitos scripts de automação antigos (`.bat`) dependem dele

### Comandos essenciais do Windows CLI (com equivalente Linux)

| Comando (Windows) | Função | Equivalente (Linux) |
|---|---|---|
| `dir` | Lista arquivos e pastas do diretório atual | `ls` |
| `cd` | Muda de diretório | `cd` |
| `cls` | Limpa a tela do terminal | `clear` |
| `copy` | Copia arquivos | `cp` |
| `move` | Move ou renomeia arquivos | `mv` |
| `del` | Apaga arquivos | `rm` |
| `mkdir` | Cria um novo diretório | `mkdir` |
| `rmdir` | Remove um diretório | `rmdir` |
| `type` | Exibe o conteúdo de um arquivo | `cat` |
| `whoami` | Mostra o usuário atualmente logado | `whoami` |
| `hostname` | Mostra o nome do computador na rede | `hostname` |
| `ipconfig` | Mostra a configuração de rede (IP, gateway, DNS) | `ifconfig` / `ip a` |
| `systeminfo` | Exibe informações detalhadas do sistema | `uname -a` |
| `tasklist` | Lista processos em execução | `ps` |
| `taskkill` | Encerra um processo pelo nome ou PID | `kill` |
| `netstat` | Exibe conexões de rede ativas | `netstat` |
| `ping` | Testa conectividade com um host | `ping` |
| `tracert` | Rastreia o caminho até um host na rede | `traceroute` |

**Por que essa tabela importa:** em investigações de segurança, é comum precisar identificar rapidamente processos suspeitos (`tasklist`), conexões de rede anômalas (`netstat`) ou configuração de rede de uma máquina comprometida (`ipconfig`) — todos comandos nativos do Windows CLI, sem precisar instalar nenhuma ferramenta extra.

### Shell Scripting — automatizando tarefas

Um script de shell é um arquivo de texto com uma sequência de comandos, executado automaticamente pela shell. No Windows, isso se traduz em arquivos `.bat` (Batch) para o CMD, ou scripts `.ps1` para o PowerShell (mais moderno e orientado a objetos).

### Por que isso é relevante para Blue Team / SOC

Analistas de segurança usam a linha de comando constantemente para:
- Investigar processos e conexões de rede em tempo real durante um incidente
- Automatizar coleta de evidências durante resposta a incidentes
- Executar comandos de triagem rápida em máquinas Windows comprometidas
- Escrever pequenos scripts que aceleram tarefas repetitivas de investigação

---

## Prática — TryHackMe

*(seção a preencher após a conclusão da sala, com screenshots e reflexões)*

---

## Dificuldades encontradas
