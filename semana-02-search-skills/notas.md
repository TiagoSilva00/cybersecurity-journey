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

## Próximas tarefas (em andamento)
- [ ] Tarefa 3 — VirusTotal (TryDetectMe)
- [ ] Tarefa 4 — Bancos de dados de vulnerabilidades (CVE)
- [ ] Tarefa 5 — Documentação Técnica (MAN)
