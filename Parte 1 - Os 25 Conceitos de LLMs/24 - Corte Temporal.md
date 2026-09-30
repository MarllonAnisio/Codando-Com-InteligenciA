---
tags: [llm, conceito, parte-1]
conceito_numero: 24
dificuldade: 🟢 Básico
aliases: [Knowledge Cutoff, Data de Corte, Limite de Conhecimento]
---

# 🔢 24 — Corte Temporal (Knowledge Cutoff)

> [!NOTE] Em uma frase só...
> O Corte Temporal (ou Knowledge Cutoff) é a data limite exata no calendário em que ocorreu a finalização do processo de treinamento original de um modelo de linguagem; o modelo é completamente "cego" para eventos, tecnologias ou notícias que ocorreram no mundo a partir dessa data.

## Analogia do Professor
Imagine um cientista brilhante e inteligentíssimo que passou a vida inteira devorando o acervo de todas as bibliotecas da cidade. O problema? No último dia do ano de 2023, ele foi escalado para uma expedição na Antártica, onde morou numa base isolada por dois anos, completamente sem acesso ao Wi-Fi, às notícias e ao WhatsApp.

Quando ele finalmente voltar da viagem e você puxar assunto com ele sobre "quem ganhou as eleições do mês passado" ou "o que você achou do lançamento do novo iPhone", o cientista brilhante vai ficar olhando com cara de paisagem ou pior... por orgulho intelectual, vai tentar "chutar" baseando-se no que ele sabia de 2 anos atrás!
A Inteligência artificial não é diferente: ela aprendeu a ler e a entender o padrão do mundo num momento exato, o treinamento foi desligado pelos engenheiros, e o cérebro dela congelou na história naquele instante temporal específico.

## 📖 O que é?
A fase de [[06 - Treinamento]] dos LLMs custa dezenas de milhões de dólares e dura meses inteiros dentro de data centers em grandes conglomerados de tecnologia (OpenAI, Google, Anthropic). Quando se atinge um nível satisfatório de acerto na rede neural, cria-se o "Checkpoint" e finaliza-se a etapa.

Todos os bilhões de sites da internet que foram injetados no corpus (o conhecimento ingerido da máquina) pertenciam à data em que o Web Crawler varreu aquelas páginas do ar. Logo:
- Se um determinado framework JavaScript famoso ganhou a versão pesada `14` seis meses **após** esse Cutoff, as lógicas, as APIs alteradas, as sintaxes exclusivas que se extinguiram... tudo aquilo que foi substituído na atualidade, não é sabido pela IA. Ela continuará sugerindo a velha sintaxe ultrapassada da versão `13`, te causando dor de cabeça com os erros de compilação da IDE na sua máquina!

Os painéis das interfaces modernas geralmente indicam de antemão: *"Model GPT-4 original — Knowledge Cutoff: April 2023"*.

## Como funciona?
Na fase da [[19 - Inferencia]] (quando nós usamos o bot online em chat), o modelo recebe sua requisição crua, mas ele se fundamenta única e exclusivamente nas conexões estatísticas cristalizadas do período da criação em Data Center.
Se você perguntar algo moderno como *"Resume os fatos da guerra que explodiu ontem"*, dois cenários catastróficos ocorrem:
1. O modelo admite que não sabe por causa do Corte (O System Prompt da OpenAI por exemplo forçava o modelo a avisar o ano do treinamento para o usuário explicitamente e parar por ali).
2. O modelo tentará "Adivinhar" com extrema convicção. Com base no texto provável gerado na amostragem (causando a temida [[22 - Alucinacao]]).

## No Mundo Real
Qual a relevância do Corte Temporal para nós programadores profissionais?
- **Libs que mudam todo dia:** Documentações de TypeScript, NextJS com a revolução do *App Router* e o React Native envelhecem muito rápido. A IA é teimosa ao extremo sugerindo formas defasadas. Você perderá dias debugando código descontinuado gerado por inteligência artificial, apenas porque não se tocou da data do Cutoff do modelo do mês!
- **Surgimento dos Agentes (Tools):** Foi justamente o trauma do Corte Temporal que forçou o mercado tecnológico a não se contentar só com LLMs puros. Desenvolveram o famoso ecossistema do ChatGPT conectado à web aberta (*Web Browsing tools*) e o Perplexity (Um bot que funciona injetando nas memórias os sites da primeira página do Google do dia de hoje para que ele gere o resumo sem defasagem temporal).

## Limitações e Cuidados
> [!IMPORTANT] Fique sempre de olho nas versões quando codificar!
> Não espere que a IA de texto seja um oráculo das breaking-changes da semana passada.
- **Não aceite cegamente o código:** No ecossistema frontend principalmente, confirme na documentação oficial na web paralela antes de dar aquele *install* de uma Lib maluca na máquina.
- **RAG como o Salvador da Pátria:** Se o desenvolvedor precisa que a resposta cubra os dados modernos, o profissional deverá embutir o PDF mais novo no prompt de forma local. Ele usa as técnicas avançadíssimas do [[21 - RAG]] antes de permitir que o modelo apenas "pesque" as respostas mortas e amargas das profundezas da sua memória neural de anos passados.

## Conceitos Relacionados
- [[15 - LLM]]
- [[21 - RAG]]
- [[22 - Alucinacao]]
- [[23 - Janela de Contexto]]

## Resumo para o Dev Junior
- **A Data-Limítrofe:** Cutoff / Corte Temporal refere-se à exata data final em que o "cérebro matemático" parou de absorver dados do mundo. Depois disso, há um vácuo.
- **Alucinação na Inércia:** Pela falta da fonte na sua base para os fatos pós-corte, há fortíssima chance de o LLM mentir sobre eventos hiper-atuais, só para tentar completar sua frase na coerência estatística!
- **Combate de Ferramentas Ativas:** Quando exigido modernidade, integre na aplicação mecanismos que deem acesso extra (Tools) a APIs vivas, buscas web, ou envie documentação por PDF anexado nos turnos de chat.
