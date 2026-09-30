---
tags: [paper, referencia, parte-2, seguranca]
autores: [Pesquisadores em Segurança de Software]
ano: 2024
---

# Security Vulnerabilities in AI-Generated Code

> [!IMPORTANT] Por que este paper importa para você, dev?
> Enquanto o paper de Stanford focou no comportamento do desenvolvedor (Do Users Write More Insecure Code?), este estudo foca diretamente na máquina: ele investiga a taxonomia real dos bugs que as IAs geram. Para se tornar um engenheiro sênior de respeito, você precisa saber diagnosticar as doenças típicas que as ferramentas de IA injetam na sua base de código sem perceber.

## Analogia do Professor
Imagine que você tem um assistente de tradução incrivelmente fluente em mil idiomas. Ele aprendeu a traduzir lendo todo o acervo da internet, incluindo sites obscuros, fóruns desatualizados de 2005 e jornais sensacionalistas. Quando você pede a ele para redigir um contrato oficial em francês, ele escreve maravilhosamente bem, com uma gramática perfeita — mas ele casualmente usa gírias e expressões que seriam inaceitáveis num tribunal formal. O código gerado pelos LLMs é assim. Como eles foram treinados em repositórios antigos e cheios de gambiarras de segurança no GitHub, eles assimilaram as "gírias perigosas" do mundo da programação. O código funciona, mas carrega o karma e os bugs do passado da internet.

## O que investigou?
O estudo propôs uma análise sistemática e de larga escala das vulnerabilidades diretas presentes no código gerado pelos modelos de linguagem populares (como GPT-4, LLaMA, Claude, etc). O objetivo era catalogar os erros e criar um mapa de quais padrões de segurança são mais rotineiramente ignorados pelas IAs durante a geração de software e entender a causa raiz de tais vulnerabilidades aparecerem em códigos recém-escritos.

## 🔬 Como foi feito? (metodologia simples)
A equipe gerou automaticamente milhares de snippets e funções de código usando LLMs para diversas linguagens de programação (Python, C, JavaScript, Go). Em seguida, essas amostras foram submetidas a ferramentas rigorosas de análise estática e dinâmica de vulnerabilidades, além de auditorias manuais realizadas por especialistas em cibersegurança. O foco foi identificar a prevalência dos erros listados na famosa lista do OWASP Top 10.

## Descobertas que vão te surpreender (números)
A pesquisa mapeou um volume estarrecedor de código vulnerável saído da caixa. As vulnerabilidades mais comuns incluíram: uso de práticas de criptografia obsoletas (como MD5), exposição de dados sensíveis, falta severa de validação de inputs (Missing Input Validation) abrindo portas para injecções de comando e SQL, e implementação de fluxos de autenticação frouxos. Mais de 30% do código analisado em contextos sensíveis apresentou ao menos um erro grave que poderia ser facilmente explorado. A equação desastrosa é a combinação de uma IA que regurgita código legado vulnerável somada a um dev junior que confia cegamente no modelo e dá o deploy sem realizar as checagens necessárias.

## Citação marcante
*"LLMs otimizam para coerência estatística e completude funcional, mas a segurança raramente é a métrica principal no seu treinamento. O resultado é a automação escalável de padrões de segurança inseguros aprendidos do ecossistema legado de código aberto."*

## O que muda para você?
A postura adotada deve ser uma só: encare todo código gerado por inteligência artificial com a mesma suspeita que você teria do código de um estagiário brilhante no seu primeiro dia, com pressa e sem dormir. Ele pode funcionar perfeitamente, mas não deve ir para o branch `main` sem ser revisado.
Como agir:
1. Comece a integrar ferramentas automatizadas de análise, como linters de segurança (SonarQube, Semgrep, Bandit no Python) logo na etapa de pré-commit do código gerado por IA.
2. Pratique a engenharia de prompt para a segurança — no seu system prompt, adicione cláusulas como: "Atue como um arquiteto de segurança sênior. Adote princípios de Zero Trust e sanitize toda entrada de dados" ao pedir geração de rotas.

## Conceitos Relacionados
[[22 - Alucinacao]] | [[Do Users Write More Insecure Code with AI]] | [[20 - Prompt e Engenharia de Prompt]] | [[Debito Cognitivo]]
