# 📖 Glossário de Cibersegurança

Vocabulário técnico (inglês/português) que venho aprendendo ao longo da jornada. Organizado por categoria para facilitar consulta.

## 🌐 Redes

| Termo (EN) | Tradução/Significado |
|---|---|
| IP Address | Endereço IP — identificador de um dispositivo na rede |
| Port | Porta — identifica um serviço específico dentro de um dispositivo |
| Handshake | "Aperto de mão" — processo de estabelecer conexão (ex: TCP) |

## 🔴 Segurança Ofensiva / Defensiva

| Termo (EN) | Tradução/Significado |
|---|---|
| Offensive Security | Segurança Ofensiva — pensar como atacante para achar falhas |
| Defensive Security | Segurança Defensiva — proteger e responder a ataques |
| SOC (Security Operations Center) | Centro de Operações de Segurança — equipe que monitora e responde a incidentes |
| Threat Intelligence | Inteligência de Ameaças — informações sobre grupos/atacantes conhecidos |
| Brute-force | Força bruta — tentar várias combinações (senhas) até acertar |
| Bruteforcing | Ato de realizar um ataque de força bruta |

## 🔍 OSINT & Reconhecimento

| Termo (EN) | Tradução/Significado |
|---|---|
| OSINT (Open Source Intelligence) | Inteligência de Fontes Abertas — coleta de informações públicas para investigação |
| Shodan | Motor de busca especializado em dispositivos conectados à internet (servidores, IoT, sistemas industriais) |
| Banner (HTTP Banner) | Cabeçalho de resposta de um servidor que revela informações como software e versão em uso |
| Reconnaissance (Recon) | Reconhecimento — fase de coleta de informações sobre um alvo antes de qualquer ataque/análise |

## 🦠 Malware & Análise de Ameaças

| Termo (EN) | Tradução/Significado |
|---|---|
| VirusTotal | Plataforma que agrega mais de 70 mecanismos de antivírus para análise de arquivos, URLs e hashes |
| Hash | Sequência única gerada a partir de um arquivo, usada para identificá-lo sem expor seu conteúdo |
| Malware | Software malicioso, termo genérico para vírus, trojans, spyware, etc. |
| Trojan | Malware disfarçado de programa legítimo para enganar a vítima |
| Infostealer | Tipo de malware focado em roubar credenciais e dados sensíveis |
| Community Score | Pontuação de reputação de um arquivo/URL no VirusTotal, baseada no consenso de detecções |

## 🛡️ Vulnerabilidades & CVE

| Termo (EN) | Tradução/Significado |
|---|---|
| CVE (Common Vulnerabilities and Exposures) | Identificador único e padronizado para uma vulnerabilidade conhecida |
| CVSS (Common Vulnerability Scoring System) | Sistema de pontuação de severidade de uma vulnerabilidade (0 a 10) |
| NVD (National Vulnerability Database) | Base de dados oficial do NIST para consulta de vulnerabilidades catalogadas |
| CNA (CVE Numbering Authority) | Organização autorizada a atribuir identificadores CVE |
| CWE (Common Weakness Enumeration) | Classificação padronizada de tipos de falhas de software (ex: SQL Injection) |
| CPE (Common Platform Enumeration) | Identificador padronizado para nomear versões específicas de software/hardware afetadas |
| Vector String (CVSS) | Notação técnica que decompõe a pontuação CVSS em métricas específicas (ex: AV:N/AC:L) |
| Exploit | Código ou técnica usada para explorar uma vulnerabilidade |
| PoC (Proof of Concept) | Código de demonstração que prova que uma vulnerabilidade pode ser explorada |
| RCE (Remote Code Execution) | Execução Remota de Código — permite que um atacante execute comandos em um sistema remoto |
| SQL Injection | Falha que permite injetar comandos SQL maliciosos através de campos de entrada não sanitizados |
| Patch | Correção de software aplicada para eliminar uma vulnerabilidade |
| Advisory | Comunicado oficial de um fornecedor sobre uma vulnerabilidade e sua correção |

## 📚 Documentação Técnica

| Termo (EN) | Tradução/Significado |
|---|---|
| Man Page (Manual Page) | Documentação oficial de um comando/ferramenta, acessível via `man <comando>` no Linux |
| Synopsis | Seção de uma man page que mostra a sintaxe completa de uso de um comando |

## 🛠️ Ferramentas

| Termo (EN) | Tradução/Significado |
|---|---|
| dirb | Ferramenta que descobre páginas ocultas em sites |
| nc (netcat) | Ferramenta de linha de comando para conexões TCP/UDP arbitrárias, port scanning e transferência de dados |
| GitHub | Plataforma de hospedagem de código, usada também como fonte de PoCs e pesquisas de segurança |

## 📌 Termos gerais

| Termo (EN) | Tradução/Significado |
|---|---|
| Flag | "Bandeira" — código que comprova que você completou um desafio |
| Room (TryHackMe) | Sala — módulo de aprendizado sobre um tema específico |
| Path (TryHackMe) | Trilha — sequência de salas organizadas por tema |
