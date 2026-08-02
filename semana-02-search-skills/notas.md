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

## Próximas tarefas (em andamento)
- [ ] Tarefa 4 — Bancos de dados de vulnerabilidades (CVE)
- [ ] Tarefa 5 — Documentação Técnica (MAN)
