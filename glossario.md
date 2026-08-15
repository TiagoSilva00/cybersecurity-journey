# 📖 Glossário de Cibersegurança

Vocabulário técnico (inglês/português) que venho aprendendo ao longo da jornada. Organizado por categoria para facilitar consulta.

## 🔐 Fundamentos e Ativos

| Termo (EN) | Tradução/Significado |
|---|---|
| Asset | Ativo — qualquer coisa de valor para uma organização (dados, sistemas, hardware, reputação, pessoas) |
| Data | Dado — informação bruta, sem contexto (ex: uma sequência de números) |
| Information | Informação — dado com contexto e significado (ex: "este número é o CPF do cliente X") |
| System | Sistema — conjunto de componentes (hardware + software) que processam informação |
| Service | Serviço — funcionalidade oferecida por um sistema (ex: e-mail, login, banco de dados) |
| Threat | Ameaça — qualquer coisa com potencial de causar dano |
| Vulnerability | Vulnerabilidade — uma fraqueza que pode ser explorada |
| Risk | Risco — probabilidade de uma ameaça explorar uma vulnerabilidade, multiplicada pelo impacto |

## 🛡️ Tríade CIA & Gestão de Acesso (IAM)

| Termo (EN) | Tradução/Significado |
|---|---|
| Confidentiality | Confidencialidade — garantir que só quem deve acessar a informação, acessa |
| Integrity | Integridade — garantir que a informação não foi alterada indevidamente |
| Availability | Disponibilidade — garantir que o sistema/informação estará acessível quando necessário |
| IAM (Identity and Access Management) | Gestão de Identidade e Acesso — conjunto de processos para controlar quem acessa o quê |
| Authentication | Autenticação — provar que você é quem diz ser (senha, biometria, token) |
| Authorization | Autorização — definir o que uma identidade autenticada pode fazer |
| MFA (Multi-Factor Authentication) | Autenticação Multifator — exigir mais de um fator de prova de identidade |
| Principle of Least Privilege | Princípio do Privilégio Mínimo — dar a cada usuário/sistema só o acesso estritamente necessário |
| Access Control | Controle de Acesso — mecanismos que aplicam as regras de quem acessa o quê |

## 🌐 Redes

| Termo (EN) | Tradução/Significado |
|---|---|
| IP Address | Endereço IP — identificador de um dispositivo na rede |
| Port | Porta — identifica um serviço específico dentro de um dispositivo |
| Handshake | "Aperto de mão" — processo de estabelecer conexão (ex: TCP) |
| DNS (Domain Name System) | Sistema de Nomes de Domínio — "tradutor" que converte nomes (ex: google.com) em endereços IP |
| DHCP (Dynamic Host Configuration Protocol) | Protocolo que atribui endereços IP automaticamente aos dispositivos numa rede |
| TCP (Transmission Control Protocol) | Protocolo de transmissão confiável, com verificação de entrega |
| UDP (User Datagram Protocol) | Protocolo de transmissão rápido, sem garantia de entrega |

## 💻 Terminal Linux — Comandos e Operadores

| Termo (EN) | Tradução/Significado |
|---|---|
| pwd | Print Working Directory — mostra o diretório atual |
| ls | List — lista o conteúdo de um diretório |
| ls -la | Listar detalhado (com ocultos) — exibe todos os arquivos, incluindo ocultos, com permissões, dono e data |
| cd | Change Directory — muda de diretório |
| cat | Concatenate — exibe o conteúdo de um arquivo |
| mkdir | Make Directory — cria um novo diretório |
| touch | Cria um arquivo vazio |
| cp | Copy — copia arquivos/pastas |
| mv | Move — move ou renomeia arquivos/pastas |
| rm | Remove — remove arquivos/pastas |
| echo | Exibir texto / redirecionar saída – exibe texto; com `>` grava a saída em um arquivo |
| > (redirect) | Redireciona a saída de um comando, sobrescrevendo um arquivo |
| >> (append) | Redireciona a saída de um comando, adicionando ao final de um arquivo |
| & | Executa um comando em segundo plano (background) |
| && | Executa o próximo comando somente após o sucesso do anterior |
| permissions (rwx) | Permissões — controlam quem pode ler, escrever ou executar um arquivo/diretório |

## 🔴 Segurança Ofensiva / Defensiva

| Termo (EN) | Tradução/Significado |
|---|---|
| Offensive Security | Segurança Ofensiva — pensar como atacante para achar falhas |
| Defensive Security | Segurança Defensiva — proteger e responder a ataques |
| SOC (Security Operations Center) | Centro de Operações de Segurança — equipe que monitora e responde a incidentes |
| Threat Intelligence | Inteligência de Ameaças — informações sobre grupos/atacantes conhecidos |
| Brute-force | Força bruta — tentar várias combinações (senhas) até acertar |
| Bruteforcing | Ato de realizar um ataque de força bruta |
| Phishing | Golpe via mensagem (e-mail, SMS) para roubar credenciais ou instalar malware |
| Social Engineering | Engenharia Social — manipulação psicológica para obter acesso ou informação |
| Privilege Escalation | Escalonamento de Privilégios — transformar um acesso limitado em um acesso maior |
| Lateral Movement | Movimentação Lateral — avançar de um sistema comprometido para outros na mesma rede |
| Data Exfiltration | Exfiltração de Dados — retirar dados roubados do ambiente da vítima |
| Cyber Kill Chain | Modelo que descreve as etapas de um ataque, do reconhecimento até o objetivo final |
| MITRE ATT&CK | Base de conhecimento que cataloga táticas e técnicas reais usadas por atacantes; referência padrão da indústria |

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
| Static Analysis | Análise Estática — inspeção de um malware sem executá-lo (código, strings, hashes) |
| Dynamic Analysis | Análise Dinâmica — observação do comportamento de um malware durante sua execução, geralmente em sandbox |

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

## 🔎 Detecção e Monitoramento (SOC)

| Termo (EN) | Tradução/Significado |
|---|---|
| Event | Evento — qualquer ocorrência registrável em um sistema (ex: um login) |
| Alert | Alerta — um evento que atende a uma regra suspeita e merece atenção |
| SIEM (Security Information and Event Management) | Ferramenta que coleta e correlaciona logs de várias fontes para gerar alertas |
| False Positive | Falso Positivo — um alerta que parecia malicioso, mas não era |
| Log | Registro histórico de eventos em um sistema |

## 🚨 Resposta a Incidentes

| Termo (EN) | Tradução/Significado |
|---|---|
| Incident Response | Resposta a Incidentes — processo estruturado para lidar com um incidente de segurança |
| Preparation | Preparação — 1ª fase da resposta a incidentes: ferramentas, políticas e treinamento definidos antes de qualquer incidente ocorrer |
| Detection and Analysis | Detecção e Análise — 2ª fase: identificar que um incidente está ocorrendo e entender sua natureza |
| Containment, Eradication and Recovery | Contenção, Erradicação e Recuperação — 3ª fase: conter o dano, eliminar a causa raiz e restaurar sistemas afetados |
| Post-Incident Activity | Atividades Pós-Incidente — 4ª fase: documentação de lições aprendidas e melhorias no processo |
| Incident | Incidente — um alerta confirmado como uma ameaça real |

## 💾 Continuidade e Recuperação

| Termo (EN) | Tradução/Significado |
|---|---|
| Backup | Cópia de segurança dos dados — só tem valor se funcionar quando restaurado |
| Disaster Recovery (DR) | Recuperação de Desastres — plano para restaurar sistemas após um desastre |
| Business Continuity (BC) | Continuidade de Negócios — plano mais amplo para manter a organização funcionando durante uma crise |
| RTO (Recovery Time Objective) | Por quanto tempo a organização pode ficar sem o sistema |
| RPO (Recovery Point Objective) | Quanto de dado (em tempo) a organização pode se dar ao luxo de perder |

## ⚖️ Governança, Risco e Conformidade (GRC)

| Termo (EN) | Tradução/Significado |
|---|---|
| GRC (Governance, Risk and Compliance) | Governança, Risco e Conformidade — área que trata de políticas, riscos e obrigações legais |
| LGPD (Lei Geral de Proteção de Dados) | Legislação brasileira central sobre coleta, uso, armazenamento e compartilhamento de dados pessoais |
| Accountable | Responsável formal por um ativo ou tipo de informação dentro da organização |

## 📚 Documentação Técnica

| Termo (EN) | Tradução/Significado |
|---|---|
| Man Page (Manual Page) | Documentação oficial de um comando/ferramenta, acessível via `man <comando>` no Linux |
| Synopsis | Seção de uma man page que mostra a sintaxe completa de uso de um comando |
| Terminal | Interface baseada em texto que permite ao usuário interagir com o sistema operacional via comandos |

## 🛠️ Ferramentas

| Termo (EN) | Tradução/Significado |
|---|---|
| dirb | Ferramenta que descobre páginas ocultas em sites |
| Gobuster | Ferramenta de enumeração de diretórios e arquivos ocultos em aplicações web via brute-force |
| nc (netcat) | Ferramenta de linha de comando para conexões TCP/UDP arbitrárias, port scanning e transferência de dados |
| GitHub | Plataforma de hospedagem de código, usada também como fonte de PoCs e pesquisas de segurança |
| grep | Comando de busca de padrões de texto dentro de arquivos, essencial para análise de logs |

## 📌 Termos gerais

| Termo (EN) | Tradução/Significado |
|---|---|
| Flag | "Bandeira" — código que comprova que você completou um desafio |
| Room (TryHackMe) | Sala — módulo de aprendizado sobre um tema específico |
| Path (TryHackMe) | Trilha — sequência de salas organizadas por tema |
| Admin Panel | Painel Administrativo — página de gerenciamento de uma aplicação web, geralmente oculta e não indexada publicamente |
