# Semana 01 — Networking Fundamentals & Linux Commands

## Objetivo
Entender os conceitos básicos de redes de computadores e praticar comandos essenciais do Linux, usando o TryHackMe como ambiente prático.

## Tarefas
## Tarefas

- [x] Completar sala "Intro to Networking" (ou similar) no TryHackMe
- [x] Completar sala "Linux Fundamentals" no TryHackMe
- [x] Anotar conceitos-chave (IP, portas, protocolos)
- [ ] Praticar comandos Linux no terminal

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

## Comandos praticados

### Navegação e arquivos

| Comando | Função |
|---------|--------|
| `pwd` | Mostra o diretório (pasta) atual |
| `ls` | Lista arquivos e pastas do diretório atual |
| `ls -la` | Lista incluindo arquivos ocultos e detalhes (permissões, tamanho, data) |
| `cd nome_pasta` | Entra em uma pasta |
| `cd ..` | Volta um nível na hierarquia de pastas |
| `mkdir nome_pasta` | Cria uma nova pasta |
| `touch arquivo.txt` | Cria um arquivo vazio |
| `cat arquivo.txt` | Mostra o conteúdo de um arquivo |
| `rm arquivo.txt` | Remove um arquivo |
| `cp origem destino` | Copia um arquivo |
| `mv origem destino` | Move ou renomeia um arquivo |

---

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
