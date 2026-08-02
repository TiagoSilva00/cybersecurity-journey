# Semana 02 — Search Skills & OSINT

## 🎯 Objetivo da semana
Desenvolver habilidades de busca e reconhecimento (OSINT) essenciais em cibersegurança, através do room "Habilidades de Busca" (Search Skills) do TryHackMe, trilha Cyber Security 101.

## 🔗 Room
[Search Skills — TryHackMe](https://tryhackme.com/room/searchskills)

---

## Tarefa 2 — Reconhecimento com Shodan (via TryScanMe)

**O que foi praticado:**
- Uso de um motor de busca especializado em dispositivos conectados à internet (Shodan), simulado via ambiente TryScanMe
- Pesquisa por banner de serviço (`apache`) para identificar servidores expostos publicamente
- Análise de metadados retornados por um scan de reconhecimento: IP, geolocalização, ISP, portas abertas, versão de software, certificado SSL/TLS
- Correlação entre endereço IP e domínio associado, como parte de um processo de OSINT (Open Source Intelligence)

**Conceito-chave:** Ferramentas como o Shodan permitem mapear ativos expostos na internet (servidores, IoT, sistemas industriais) antes mesmo de qualquer interação direta — uma etapa fundamental da fase de reconhecimento em testes de segurança, também usada por defensores para identificar exposição não intencional da própria infraestrutura.

**Evidência:**

![Introdução à Tarefa 2 - Shodan](./imagens/search-skills-tarefa02-shodan-intro.png)
*Tela inicial da Tarefa 2 do room, introduzindo o uso do Shodan como ferramenta de reconhecimento.*

![Busca no TryScanMe por apache](./imagens/search-skills-tarefa02-tryscanme-resultado.png)
*Reconhecimento de infraestrutura via motor de busca especializado (TryScanMe/Shodan): identificação de servidor Apache 2.4.58 exposto publicamente, incluindo portas abertas, certificado SSL e domínio associado ao IP consultado.*

---

## Tarefa 3 — VirusTotal (TryDetectMe)

**O que foi praticado:**
- Uso do VirusTotal, plataforma que agrega mais de 70 mecanismos de antivírus e verificadores de reputação em uma única interface, para análise de arquivos, URLs, domínios e hashes suspeitos
- Envio e análise de um arquivo malicioso simulado (`invoice_payment.exe`) — nome típico de engenharia social usado em campanhas de phishing (fatura/pagamento como isca)
- Interpretação do Community Score e da taxa de detecção entre motores de segurança (52 de 72 fornecedores sinalizaram o arquivo como malicioso)
- Leitura de rótulos de ameaça atribuídos por diferentes vendors, reconhecendo a família de malware AgentTesla (infostealer/RAT usado para roubo de credenciais)
- Compreensão da limitação da ferramenta: o VirusTotal não é infalível, mas serve como recurso de consenso da comunidade para triagem rápida de arquivos e links suspeitos

**Conceito-chave:** O VirusTotal é uma ferramenta essencial na fase de análise/triagem de um SOC — permite verificar rapidamente se um arquivo, hash ou URL é conhecido como malicioso, sem necessidade de executá-lo em ambiente isolado. A convergência de múltiplos vendors com rótulos similares reforça a confiabilidade da identificação da ameaça.

**Evidência:**

![VirusTotal - Análise de arquivo](./imagens/search-skills-tarefa03-virustotal-analise.png)
*Análise de um arquivo suspeito (arquivo de teste EICAR) no VirusTotal, evidenciando o uso da plataforma para consolidar resultados de múltiplos mecanismos de antivírus em uma única interface, permitindo triagem rápida de arquivos potencialmente maliciosos através do consenso entre diferentes fornecedores de segurança.*

![VirusTotal - Detecção de malware AgentTesla](./imagens/search-skills-tarefa03-virustotal-deteccoes.png)
*Resultado da análise do arquivo `invoice_payment.exe` — um nome característico de técnica de engenharia social (isca de fatura/pagamento) — mostrando detecção por 52 de 72 fornecedores de segurança (Community Score -15) e identificação convergente da ameaça como pertencente à família de malware AgentTesla (infostealer/trojan usado para roubo de credenciais), reforçando a confiabilidade da classificação através do consenso entre múltiplos vendors (Microsoft, Kaspersky, Norton, Malwarebytes, ESET-NOD32, entre outros).*

---

## Tarefa 4 — Bancos de Dados de Vulnerabilidades (CVE)

**O que foi praticado:**
- Exploração do NVD (National Vulnerability Database), mantido pelo NIST, como fonte oficial de consulta de vulnerabilidades catalogadas
- Leitura e interpretação de uma entrada CVE real (`CVE-2025-55182`), incluindo descrição técnica, datas de publicação/atualização, e organização responsável pela divulgação (CNA)
- Compreensão do padrão de nomenclatura `CVE-<ANO>-<NÚMERO>`, identificador único usado entre fornecedores, pesquisadores e ferramentas de segurança
- Interpretação do sistema de pontuação CVSS (Common Vulnerability Scoring System), com os fatores: Impacto, Complexidade e Disponibilidade
- Leitura do Vector String CVSS, que decompõe a pontuação em métricas técnicas específicas
- Análise de uma vulnerabilidade crítica real (score 10.0 CRITICAL) em React Server Components — RCE pré-autenticação por desserialização insegura
- Exploração da seção de Referências de uma CVE (advisories, patches, Exploit-DB, Snyk) e da tabela de produtos afetados
- Introdução ao conceito de CPE (Common Platform Enumeration)

**Conceito-chave:** O CVE funciona como uma "linguagem comum" entre toda a comunidade de segurança, permitindo que fornecedores, pesquisadores e times de resposta a incidentes se refiram exatamente à mesma vulnerabilidade. O CVSS complementa isso fornecendo critério objetivo de priorização, essencial para times de SOC decidirem o que corrigir primeiro.

**Evidência:**

![NVD - Detalhe da CVE-2025-55182](./imagens/search-skills-tarefa04-nvd-cve-detail.png)
*Consulta à entrada CVE-2025-55182 no National Vulnerability Database (NIST), evidenciando uma vulnerabilidade crítica (CVSS 10.0) de execução remota de código pré-autenticação em React Server Components, causada por desserialização insegura de payloads HTTP em endpoints de Server Functions.*

![CVSS - Conceitos e exemplo prático](./imagens/search-skills-tarefa04-cvss-conceitos.png)
*Estudo dos componentes de uma entrada CVE — formato de identificador, fatores de pontuação CVSS (impacto, complexidade, disponibilidade) e exemplo prático de vulnerabilidade em Apache WebPortal, incluindo produtos afetados, referências oficiais (advisory, patch) e identificadores CPE das versões vulneráveis.*

## Tarefa 5 — Documentação Técnica (MAN)

**O que foi praticado até aqui:**
- Introdução ao conceito de documentação oficial de produtos e ferramentas como fonte mais confiável de informação técnica, superior a tutoriais de terceiros
- Exploração das Linux Man Pages, sistema de documentação nativo do Linux acessível via `man <comando>`
- Execução prática do comando `man nc` em ambiente simulado de terminal, navegando pela estrutura padrão de uma man page:
  - **NAME** — identificação e propósito da ferramenta
  - **SYNOPSIS** — sintaxe completa de uso, incluindo todas as flags/opções disponíveis (`-i interval`, `-p source_port`, `-w timeout`, `-X proxy_protocol`, entre outras)
  - **DESCRIPTION** — explicação detalhada da ferramenta `nc` (netcat), incluindo seus casos de uso: conexões TCP/UDP, port scanning, suporte a IPv4/IPv6

**Conceito-chave:** Documentação oficial (como as man pages) é a fonte primária e mais confiável para entender o funcionamento real de uma ferramenta, especialmente durante troubleshooting — deve ser sempre a primeira consulta, não a última, antes de recorrer a tutoriais externos que podem estar desatualizados.

**Evidência:**

![Introdução às Man Pages](./imagens/search-skills-tarefa05-man-pages-intro.png)
*Introdução ao conceito de documentação técnica oficial (Man Pages do Linux), destacando sua confiabilidade como fonte primária de consulta para troubleshooting e uso correto de ferramentas de linha de comando.*

![Execução prática de man nc](./imagens/search-skills-tarefa05-man-nc-output.png)
*Execução do comando `man nc` em ambiente prático simulado, exibindo a estrutura padrão de uma man page do Linux: seção NAME (identificação da ferramenta netcat), SYNOPSIS (sintaxe completa com flags disponíveis) e DESCRIPTION (funcionalidades como conexões TCP/UDP e port scanning).*

---

## Próximas tarefas (em andamento)
- [ ] Tarefa 6 — GitHub

