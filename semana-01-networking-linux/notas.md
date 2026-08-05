# Semana 01 — Networking Fundamentals & Linux Commands

## Objetivo
Entender os conceitos básicos de redes de computadores e praticar comandos essenciais do Linux, usando o TryHackMe como ambiente prático.

## Tarefas

- [x] Completar sala "Intro to Networking" (ou similar) no TryHackMe
- [x] Completar sala "Linux Fundamentals" no TryHackMe
- [x] Anotar conceitos-chave (IP, portas, protocolos)
- [x] Praticar comandos Linux no terminal

## Conceitos aprendidos

### Endereço IP
Um endereço IP é o identificador único de um dispositivo dentro de uma rede — funciona como um "endereço postal" digital, permitindo que os dados saibam para onde devem ser enviados.

**Exemplo:** 192.168.1.10
Esse endereço identifica um dispositivo específico dentro de uma rede local.

---

### Portas
Enquanto o IP identifica o dispositivo, a **porta** identifica qual serviço/programa específico deve receber os dados dentro daquele dispositivo. Funciona como o "número do apartamento" dentro de um "prédio" (o IP).

**Formato:** `IP:PORTA`

**Exemplo:** 192.168.1.10:443

**Portas mais comuns:**

| Porta | Serviço | Função |
|-------|---------|--------|
| 80    | HTTP    | Navegação web (sem criptografia) |
| 443   | HTTPS   | Navegação web (com criptografia) |
| 22    | SSH     | Acesso remoto seguro a servidores |
| 21    | FTP     | Transferência de arquivos |

**Relevância para segurança:** boa parte do reconhecimento de rede (*network enumeration*) em pentest consiste em identificar quais portas estão abertas em um alvo e quais serviços rodam nelas — isso revela pontos de entrada possíveis.

---

### Protocolos: TCP vs UDP

Protocolos são as "regras" que definem como os dados trafegam pela rede.

**TCP (Transmission Control Protocol)**
- Orientado à conexão: faz um "aperto de mão" (*three-way handshake*) antes de transmitir
- Garante entrega e ordem correta dos dados
- Mais lento, porém confiável
- Usado em: navegação web (HTTP/HTTPS), e-mail, transferência de arquivos

**UDP (User Datagram Protocol)**
- Não orientado à conexão: envia os dados sem confirmação de entrega
- Mais rápido, porém sem garantias
- Usado em: streaming de vídeo, jogos online, chamadas de voz (VoIP)

**Analogia:** TCP é como enviar uma carta registrada, com confirmação de recebimento. UDP é como jogar um bilhete pela janela — mais rápido, mas sem garantia de que chegou ao destino.

---

### Resumo comparativo

| Característica | TCP | UDP |
|-----------------|-----|-----|
| Confiabilidade | Alta | Baixa |
| Velocidade | Mais lenta | Mais rápida |
| Conexão | Orientado à conexão | Sem conexão |
| Exemplo de uso | HTTP, HTTPS, FTP | Streaming, jogos online |

## 🖥️ Comandos praticados (Linux Fundamentals Part 1 — TryHackMe)

### Comandos básicos: whoami e echo
- `whoami` — identifica o usuário logado no sistema
- `echo "texto"` — exibe texto na tela, base para scripts e automações

![Whoami e Echo](./imagens/linux-fundamentals-03-whoami-echo.png)
*Prática dos comandos `whoami` (identificação do usuário logado) e `echo` (exibição de texto), fundamentos usados constantemente em scripts e automações de segurança.*

### Navegação de diretórios: pwd, ls, cd, cat
- `pwd` — mostra o diretório atual
- `ls` — lista o conteúdo do diretório
- `cd` — muda de diretório (`cd ..` sobe um nível; `cd` sozinho volta para home)
- `cat` — exibe o conteúdo de um arquivo

![Introdução aos comandos de navegação](./imagens/linux-fundamentals-04-comandos-navegacao-intro.png)
*Tabela introdutória dos 4 comandos essenciais de navegação no terminal Linux.*

![Primeira listagem de diretórios](./imagens/linux-fundamentals-05-ls-primeiro-resultado.png)
*Primeira execução do comando `ls`, revelando a estrutura de pastas do ambiente de laboratório.*

![Descoberta de senha via cat](./imagens/linux-fundamentals-06-cat-passwords-descoberta.png)
*Navegação até a pasta `folder1` e leitura do arquivo `passwords.txt` com o comando `cat`, revelando o conteúdo `password123`.*

![Navegação entre pastas e retorno ao home](./imagens/linux-fundamentals-07-navegacao-pastas-cd-home.png)
*Exploração das pastas folder1 a folder4, incluindo o aprendizado prático da sintaxe correta do comando `cd ..` (dois pontos) para retornar ao diretório pai, e do uso de `cd` sem argumentos para retornar diretamente ao diretório pessoal (home).*

### Busca de conteúdo com grep
- `grep "padrão" arquivo` — busca um padrão de texto dentro de um arquivo

![Descoberta de flag via grep](./imagens/linux-fundamentals-08-grep-flag-descoberta.png)
*Uso do comando `grep` para buscar o padrão de texto "THM" dentro do arquivo de log `access.log`, revelando a flag `THM{ACCESS}` — prática direta de análise de logs, técnica central em investigações de segurança.*

### Redirecionadores de saída: > e >>
- `>` — sobrescreve o conteúdo de um arquivo
- `>>` — adiciona conteúdo ao final do arquivo, preservando o que já existia

![Redirecionadores de saída](./imagens/linux-fundamentals-09-redirecionadores-echo.png)
*Demonstração prática da diferença entre os operadores de redirecionamento `>` (sobrescreve o arquivo) e `>>` (adiciona ao final, preservando conteúdo existente) — confirmado pela duplicação do texto "TryHackMe" no arquivo `thm` após o uso do `>>`.*

### Operadores de controle: & e &&
- `&` — executa um comando em segundo plano (background)
- `&&` — executa o segundo comando somente após o sucesso do primeiro

## Comandos praticados

Comandos de terminal Linux são a base de qualquer trabalho técnico em cibersegurança. Grande parte das ferramentas de análise, SIEMs, scripts de automação e distribuições ofensivas/defensivas (Kali, Wazuh, etc.) rodam sobre ambientes Linux e são operadas via linha de comando. Para um analista iniciante, dominar navegação e manipulação de arquivos não é opcional: é o que permite investigar logs, preservar evidências, automatizar tarefas repetitivas e entender o comportamento de invasores que também usam esses mesmos comandos.

Nesta etapa, pratiquei os seguintes comandos de navegação e manipulação de arquivos: `pwd`, `ls`, `ls -la`, `cd`, `mkdir`, `touch`, `cat`, `cp`, `mv`, `rm` e `echo` (com redirecionamento de saída).

- [x] Praticar comandos Linux de navegação e manipulação de arquivos

### Evidências da prática

![Navegação inicial](./imagens/01-linux-navegacao-inicial.png)
*Verificação inicial da estrutura de diretórios do usuário com `cd` (retorno à home) e `ls -la`, exibindo permissões, proprietário e arquivos ocultos (`.bash_history`, `.profile`, etc.). Praticar a leitura de metadados de arquivos é essencial para um analista de cibersegurança, pois artefatos e configurações maliciosas frequentemente residem em arquivos ocultos ou dependem de permissões mal configuradas.*

![Criação de diretório](./imagens/02-linux-mkdir.png)
*Criação do diretório `pratica-linux` com `mkdir`, confirmada com `ls`. Organização de diretórios é uma habilidade básica, mas fundamental para estruturar ambientes de teste, laboratórios e evidências durante investigações.*

![Navegação e criação de arquivo](./imagens/03-linux-cd-touch-lsla.png)
*Navegação até o novo diretório com `cd pratica-linux`, criação de arquivo vazio com `touch arquivo1.txt` e verificação com `ls -la`. O comando `touch` é amplamente usado para criar arquivos de teste e também aparece em técnicas de timestomping (manipulação de metadados de tempo), tema relevante em forense digital.*

![Escrita e leitura de arquivo](./imagens/04-linux-echo-cat.png)
*Uso de `echo` com redirecionamento (`>`) para escrever conteúdo em `arquivo1.txt`, seguido de `cat` para exibir o conteúdo. Redirecionamento de saída é a base para geração e manipulação de logs — competência essencial para quem pretende atuar com SIEM (Splunk, Wazuh) e análise de log em SOC.*

![Cópia de arquivo](./imagens/05-linux-cp.png)
*Cópia de arquivo com `cp arquivo1.txt arquivo2.txt`, validada com `ls -la`. Cópia de arquivos é rotina em coleta e preservação de evidências (cadeia de custódia), garantindo que o original não seja alterado durante a análise.*

![Renomeação de arquivo](./imagens/06-linux-mv.png)
*Renomeação/movimentação de arquivo com `mv arquivo2.txt arquivo-renomeado.txt`, confirmada com `ls -la`. Entender `mv` é importante para reconhecer também técnicas de evasão, já que atacantes frequentemente renomeiam arquivos maliciosos para mascarar sua real função.*

![Remoção de arquivo](./imagens/07-linux-rm.png)
*Remoção de arquivo com `rm arquivo-renomeado.txt`, confirmada com `ls -la`. Além da gestão de arquivos, compreender `rm` ajuda o analista a reconhecer indícios de anti-forense, como tentativas de exclusão de evidências por invasores.*

![Verificação final](./imagens/08-linux-pwd-verificacao-final.png)
*Verificação final do diretório de trabalho com `pwd`, listagem completa com `ls -la` e leitura de conteúdo com `cat arquivo1.txt`. Fecha o ciclo de prática confirmando domínio da navegação e manipulação básica do sistema de arquivos Linux — pré-requisito indispensável para qualquer atividade prática em SOC, pentest ou administração de sistemas.*

---

## ✅ Room concluída

Room **"Linux Fundamentals Part 1"** finalizada com sucesso — 5 tarefas completadas, 64 pontos, streak de 5 dias.

![Room Linux Fundamentals concluído](./imagens/linux-fundamentals-10-room-concluido.png)
*Confirmação oficial de conclusão da room "Linux Fundamentals Part 1" no TryHackMe: 5 tarefas completadas, 64 pontos conquistados e streak de 5 dias consecutivos de estudo.*

### Rede e diagnóstico

| Comando | Função |
|---------|--------|
| `ifconfig` ou `ip a` | Mostra as interfaces de rede e endereços IP da máquina |
| `ping IP_ou_dominio` | Testa se um host está acessível na rede |
| `whoami` | Mostra o usuário atual logado |
| `hostname` | Mostra o nome da máquina na rede |
| `netstat -tuln` | Lista portas abertas e conexões ativas na máquina |

---

### Permissões

| Comando | Função |
|---------|--------|
| `chmod +x arquivo` | Torna um arquivo executável |
| `sudo comando` | Executa um comando com privilégios de administrador |

---

### Exemplo prático

```bash
# Verificar meu IP na rede
ip a

# Testar se consigo alcançar outro dispositivo
ping 192.168.1.1

# Ver o que está rodando/aberto na minha máquina
netstat -tuln
```

**Observação:** esses comandos foram praticados no ambiente do TryHackMe / Kali Linux, seguindo os exercícios da sala de Linux Fundamentals.

## Prática — TryHackMe

### 🏆 Sala concluída: Offensive Security Intro
**Trilha:** Cyber Security 101 → Start Your Cyber Security Journey

**Progresso:** 4/4 tarefas concluídas | 40 pontos ganhos

**O que foi praticado:**
- Diferença entre segurança **ofensiva** (pensar como atacante) e **defensiva** (proteger sistemas)
- Uso da ferramenta `dirb` para descobrir páginas ocultas em um site (enumeração de diretórios)
- Exploração de uma vulnerabilidade real: acesso não autenticado a um painel administrativo (`/bank-transfer`) que permitia manipular saldos bancários
- Conceito de **"security through obscurity"** — esconder uma URL não é o mesmo que protegê-la; a correção correta é exigir autenticação (login)

**Flag conquistada:** `BANK-HACKED`
<img width="1355" height="648" alt="Prática - TryHackMe Sala Concluída - Offensive Security" src="https://github.com/user-attachments/assets/1e1118a0-975d-4bba-9850-750aa687ed67" />

**Reflexão:** essa foi minha primeira experiência prática de identificar e explorar uma vulnerabilidade real (mesmo que em ambiente simulado). Ficou claro como falhas simples de autenticação podem expor funcionalidades críticas de um sistema.

---
### 🛡️ Sala concluída: Introduction to Defensive Security
**Trilha:** Cyber Security 101 → Start Your Cyber Security Journey

**Progresso:** 5/5 tarefas concluídas | 40 pontos ganhos

**O que foi praticado:**
- Papel de um analista de **SOC (Security Operations Center)** — atuando na defesa de uma organização
- Identificação de um alerta de segurança: tentativas suspeitas de login (ataque de **brute-force**)
- **Contenção** do incidente: bloqueio da conta comprometida (`dave.saunders`) antes que o ataque fosse bem-sucedido
- Registro de **Threat Intelligence** (inteligência de ameaças) sobre o grupo atacante identificado (`ShadowFigures`)
- Elaboração de um **relatório de incidente** completo, formalizando o ocorrido

**Flag conquistada:** `THM{ACCOUNT-LOCKED}`

<img width="1353" height="647" alt="Prática - Introdução à Segurança Defensiva" src="https://github.com/user-attachments/assets/e235c118-1c9f-4d0e-bbba-aaa39aac0df2" />


**Reflexão:** essa sala me mostrou a outra face da segurança — em vez de atacar/explorar, o foco foi identificar, conter e documentar um ataque em andamento. Entendi na prática o ciclo de resposta a incidentes (identificar → conter → investigar → documentar), que é a base do trabalho de um analista SOC/Blue Team.

---

## Dificuldades encontradas
