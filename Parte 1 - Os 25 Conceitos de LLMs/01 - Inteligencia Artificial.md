---
tags: [llm, conceito, parte-1]
conceito_numero: 1
dificuldade: 🟢 Básico
aliases: [IA, Artificial Intelligence, AI]
---

# 01 — Inteligência Artificial

> [!NOTE] Em uma frase só...
> Inteligência Artificial é a área da computação que desenvolve sistemas capazes de imitar comportamentos associados à inteligência humana — como aprender, raciocinar, tomar decisões e resolver problemas.

## Analogia do Professor

Imagina um estudante com superpoderes . Esse estudante passou os últimos 70 anos lendo **milhões de livros, artigos, fóruns, Wikipedia, Reddit, código-fonte no GitHub, receitas culinárias, bulas de remédio, letras de música...**

Agora você chega pra ele e faz uma pergunta qualquer. Ele não "pensa" do jeito que um humano pensa — ele recupera padrões de tudo que já leu e monta uma resposta que faz sentido dado o contexto.

Esse estudante maníaco por leitura? É isso que a IA faz. Ela não "entende" no sentido humano — ela **reconhece padrões** em dados e os usa para gerar outputs úteis.

> [!TIP] Professor diz...
> Não confunda "IA entende" com "IA imita muito bem o entendimento". Essa distinção vai ser crucial quando você for depurar por que seu modelo gerou uma bobagem. 😅

## 📖 O que é?

Inteligência Artificial (IA) é um ramo da **ciência da computação** que estuda e desenvolve sistemas que conseguem realizar tarefas que, se feitas por humanos, consideraríamos inteligentes. Essas tarefas incluem:

- 🗣️ Compreender e gerar linguagem natural
- Reconhecer imagens, faces e objetos
- 🎮 Jogar e vencer humanos em jogos complexos (xadrez, Go, videogames)
- 🚗 Dirigir veículos de forma autônoma
- 🔬 Auxiliar no diagnóstico médico
- Escrever e revisar código

> [!IMPORTANT] Não é nova!
> A IA **não surgiu ontem**. O termo foi cunhado em **1956** na Conferência de Dartmouth por John McCarthy. O que mudou nos últimos anos foi: (1) **volume de dados** disponíveis, (2) **poder computacional** com GPUs, e (3) **novas arquiteturas** de redes neurais. Esses três fatores juntos criaram a explosão que vivemos hoje.

A IA ficou **acessível ao público geral** há cerca de 3-4 anos — principalmente com o lançamento do ChatGPT em novembro de 2022. Mas empresas e pesquisadores já usavam IA em produção muito antes disso.

## Como funciona?

No nível mais alto, o ciclo de vida de um sistema de IA é:

```
1. COLETA DE DADOS
 └─ Texto, imagens, vídeos, áudio, dados estruturados...

2. 🧹 PRÉ-PROCESSAMENTO
 └─ Limpeza, normalização, tokenização...

3. 🏋️ TREINAMENTO
 └─ O algoritmo aprende padrões dos dados

4. MODELO
 └─ Resultado do treinamento — contém o "conhecimento"

5. INFERÊNCIA
 └─ O modelo recebe uma entrada nova e gera uma saída
```

Há diferentes **paradigmas** dentro da IA:

| Abordagem | O que faz | Exemplo |
|---|---|---|
| **Machine Learning** | Aprende com dados | Filtro de spam |
| **Deep Learning** | Redes neurais profundas | Reconhecimento de voz |
| **LLMs** | Modelos de linguagem gigantes | ChatGPT, Gemini |
| **Visão Computacional** | Processa imagens/vídeos | Face ID |
| **IA Simbólica** | Regras explícitas (old school) | Sistemas especialistas |

## No Mundo Real

Você já usa IA todo dia — provavelmente sem perceber:

- 📱 **Teclado do celular** que sugere a próxima palavra? IA.
- 🎵 **Spotify/YouTube** recomendando músicas/vídeos? IA.
- 📸 **Filtros do Instagram/Snapchat** que reconhecem seu rosto? IA.
- 📧 **Gmail** separando spam de e-mails legítimos? IA.
- 🛒 **Amazon** sugerindo "quem comprou X também comprou Y"? IA.
- 🗺️ **Google Maps** prevendo o tempo de chegada? IA.
- 🏦 **Banco** bloqueando sua compra suspeita no exterior? IA (detecção de fraude).

E claro, o que mais interessa para este curso:
- **ChatGPT, Gemini, Claude, Copilot** — assistentes conversacionais baseados em LLMs.

## Limitações e Cuidados

> [!WARNING] A IA não é mágica — nem infalível!
> Um dos erros mais comuns de devs juniors é tratar a IA como uma "caixa preta que sempre acerta". Spoiler: **ela erra, e às vezes erra feio**. Entender *por que* ela erra é o que vai te diferenciar como desenvolvedor.

Principais limitações:

- **Não tem senso comum** — pode gerar respostas tecnicamente coerentes mas factualmente erradas
- **Não tem memória permanente** (por padrão) — cada conversa começa do zero
- **Reproduz vieses dos dados de treino** — se os dados têm preconceito, o modelo aprende o preconceito
- **Pode "alucinar"** — inventar fatos, referências, código que não existe
- **Corte de conhecimento** — não sabe de eventos após sua data de treino

> [!CAUTION] Dado ruim = Modelo ruim
> "Garbage in, garbage out" é uma das frases mais antigas e mais verdadeiras da computação. Em IA, isso é amplificado: se você treinar um modelo com dados enviesados ou de baixa qualidade, o modelo vai perpetuar esses problemas em escala.

## Conceitos Relacionados
[[02 - Aprendizado de Maquina]] [[04 - Redes Neurais Artificiais]] [[16 - IA Generativa]] [[06 - Treinamento]] [[08 - Modelo]]

## Resumo para o Dev Junior

- 🔑 IA **não é nova** — existe desde os anos 50, mas ganhou poder real com dados + GPUs + novas arquiteturas
- 🔑 IA **aprende padrões** a partir de dados, não segue regras explícitas (diferente do software tradicional)
- 🔑 IA **não "pensa"** como humano — ela reconhece padrões estatísticos em dados
- 🔑 Você já usa IA no dia a dia sem perceber — isso vai só aumentar na sua carreira
- 🔑 Como dev, você vai **integrar, avaliar e depurar** sistemas de IA — então entender os fundamentos é essencial
