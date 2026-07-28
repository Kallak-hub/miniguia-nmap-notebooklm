# Miniguia de Estudos - Nmap com NotebookLM

## Desafio DIO - NotebookLM

Este repositório foi desenvolvido como parte do desafio da DIO, utilizando o **NotebookLM** como ferramenta de aprendizagem ativa.

---

# Objetivo

O tema escolhido para este estudo foi o **Nmap (Network Mapper)**, uma das principais ferramentas utilizadas para descoberta de hosts, mapeamento de portas e auditoria de segurança.

Os objetivos deste projeto foram:

* Aprender os principais recursos do Nmap;
* Compreender o funcionamento do **Nmap Scripting Engine (NSE)**;
* Explorar diferentes técnicas de varredura de portas;
* Utilizar o NotebookLM para consolidar conhecimentos a partir da documentação oficial.

---

# Fontes utilizadas

Durante o estudo foram adicionadas ao NotebookLM fontes oficiais e materiais técnicos, entre elas:

* Manual Oficial do Nmap
* Documentação Oficial do Nmap Scripting Engine (NSE)
* Artigos técnicos sobre técnicas de Scan
* Documentação sobre detecção de serviços e sistemas operacionais

---

# Engenharia de Prompts

## Prompt 1

> Faça uma busca e adicione os manuais oficiais do Nmap, documentação NSE e artigos sobre tipos de scan.

### Resultado

O NotebookLM localizou a documentação oficial e utilizou essas fontes como base para responder às perguntas posteriores.

---

## Prompt 2

> Como funcionam os scripts NSE para automação de segurança?

### Resposta resumida

O NotebookLM explicou que o Nmap possui uma arquitetura modular composta por:

* Descoberta de Hosts
* Varredura de Portas
* Detecção de Serviços
* Identificação de Sistema Operacional
* Nmap Scripting Engine (NSE)

Também apresentou os principais tipos de scan:

* TCP SYN Scan (-sS)
* TCP Connect (-sT)
* UDP Scan (-sU)
* NULL, FIN e Xmas Scan
* Idle Scan (-sI)

Sobre o NSE, explicou que os scripts são escritos em **Lua** e organizados em categorias como:

* auth
* discovery
* vuln
* exploit

Além disso, mostrou técnicas de evasão de firewall utilizando:

* Fragmentação (-f)
* Decoys (-D)
* Spoof de endereço MAC
* Ajuste da porta de origem
* Templates de tempo (-T0 até -T5)

### Cicatriz (Troubleshooting)

Durante essa resposta, o NotebookLM utilizou um identificador genérico (**CVE-2021-XXXXX**) como exemplo de vulnerabilidade.

Esse comportamento demonstrou que, embora a IA compreenda bem o conteúdo dos documentos, ainda pode utilizar exemplos genéricos quando a pergunta é muito ampla.

Para obter respostas mais precisas, foi necessário solicitar exemplos concretos e consultar novamente a documentação oficial.

---

## Prompt 3

> Como posso executar todos os scripts da categoria "vuln"?

### Resposta resumida

O NotebookLM respondeu corretamente que o comando é:

```bash
nmap --script vuln <alvo>
```

Também explicou recursos importantes do NSE, como:

* Combinações booleanas:

```bash
nmap --script "vuln and safe"
```

```bash
nmap --script "vuln and not dos"
```

* Uso do parâmetro:

```bash
--script-args
```

* Atualização da base de scripts:

```bash
nmap --script-updatedb
```

Além disso, reforçou que os scripts de vulnerabilidade devem ser utilizados apenas em ambientes autorizados.

### Cicatriz (Troubleshooting)

O NotebookLM afirmou que:

> "Os scripts NSE não rodam em um ambiente isolado (sandbox)."

Embora a ideia geral esteja correta, essa frase pode causar confusão.

Uma explicação mais precisa seria:

> Os scripts do NSE são executados diretamente pelo Nmap e interagem com o alvo de acordo com sua finalidade. Alguns scripts são classificados como **intrusive** ou **dos**, pois podem gerar maior impacto no serviço analisado, razão pela qual devem ser utilizados apenas em ambientes autorizados.

Esse exemplo mostra que o NotebookLM compreendeu corretamente os manuais estudados, mas ainda apresenta pequenas limitações na forma de comunicar conceitos técnicos de maneira totalmente precisa.

---

# Miniguia de Estudos

## O que é o Nmap?

O Nmap é uma ferramenta de código aberto utilizada para:

* Descobrir hosts ativos
* Identificar portas abertas
* Detectar serviços
* Identificar sistemas operacionais
* Automatizar auditorias utilizando scripts NSE

---

## Principais tipos de Scan

| Tipo              | Finalidade                                |
| ----------------- | ----------------------------------------- |
| TCP SYN (-sS)     | Scan rápido e discreto                    |
| TCP Connect (-sT) | Utilizado sem privilégios administrativos |
| UDP (-sU)         | Descoberta de serviços UDP                |
| NULL / FIN / Xmas | Técnicas de evasão de firewall            |
| Idle (-sI)        | Scan utilizando um host "zumbi"           |

---

## Glossário

**Host** — Computador conectado à rede.

**Porta** — Canal lógico utilizado pelos serviços de rede.

**Scan** — Processo de descoberta de portas e serviços.

**Fingerprint** — Técnica utilizada para identificar sistemas operacionais e aplicações.

**NSE** — Nmap Scripting Engine, mecanismo de automação baseado em scripts Lua.

**Lua** — Linguagem utilizada para desenvolver scripts do NSE.

---

# Prompts reutilizáveis

* Explique este conceito como se eu fosse iniciante.
* Faça um resumo em tópicos.
* Crie uma tabela comparativa dos tipos de scan.
* Explique quando utilizar cada categoria do NSE.
* Gere um mapa mental sobre o assunto.
* Crie perguntas para revisão.
* Gere flashcards para memorização.
* Mostre exemplos práticos utilizando comandos do Nmap.

---

# Conclusão

O NotebookLM demonstrou ser uma excelente ferramenta para organizar e sintetizar informações técnicas a partir da documentação oficial. Durante os testes, foi possível perceber que a qualidade das respostas melhora significativamente quando são utilizados prompts específicos e objetivos.

Também foi observado que, embora a IA apresente respostas tecnicamente consistentes, ainda pode utilizar exemplos genéricos ou simplificar alguns conceitos. Por isso, é importante validar as informações com a documentação oficial, especialmente em temas relacionados à cibersegurança.

Este projeto reforçou a importância da engenharia de prompts e da análise crítica das respostas geradas por IA, transformando o NotebookLM em um apoio valioso para estudos e revisões técnicas.
