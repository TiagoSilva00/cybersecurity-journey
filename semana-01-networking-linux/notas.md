# Semana 01 — Networking Fundamentals & Linux Commands

## Objetivo
Entender os conceitos básicos de redes de computadores e praticar comandos essenciais do Linux, usando o TryHackMe como ambiente prático.

## Tarefas
- [ ] Completar sala "Intro to Networking" (ou similar) no TryHackMe
- [ ] Completar sala "Linux Fundamentals" no TryHackMe
- [ ] Anotar conceitos-chave (IP, portas, protocolos)
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
(lista de comandos + o que cada um faz)

## Dificuldades encontradas
