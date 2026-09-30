---
tags: [paper, referencia, parte-2, deep-learning]
autores: [Ashish Vaswani, Noam Shazeer, Niki Parmar, Jakob Uszkoreit, Llion Jones, Aidan N. Gomez, Łukasz Kaiser, Illia Polosukhin]
ano: 2017
---

# Attention Is All You Need

> [!IMPORTANT] Por que este paper importa para você, dev?
> Esse paper é o "Big Bang" do ecossistema de Inteligência Artificial moderno! Foi aqui que nasceu a arquitetura **Transformer**, que hoje alimenta absolutamente TODOS os grandes modelos do planeta: ChatGPT, Gemini, Claude, LLaMA, etc. Se você quer entender de tecnologia hoje, conhecer o Transformer é o equivalente a um mecânico de automóveis entender como funciona o motor a combustão.

## Analogia do Professor
Imagine que, antes deste paper, traduzir uma frase grande com as redes neurais antigas era como ouvir um longo recado em um telefone sem fio. O sistema lia a primeira palavra, ia guardando a informação sequencialmente, lia a segunda, a terceira... e quando chegava no final de um parágrafo enorme, ele frequentemente "esquecia" o que a primeira palavra significava, perdendo o sentido geral da frase (isso era o limite das Redes Neurais Recorrentes - RNNs). O mecanismo de Atenção (*Attention*) introduzido neste paper transformou o telefone sem fio em uma reunião onde a IA consegue olhar para TODAS as palavras do recado de uma vez só. Ela calcula instantaneamente quais partes do parágrafo têm mais relação umas com as outras — tudo em paralelo, como um leitor dinâmico incrivelmente eficiente.

## O que investigou?
A equipe de pesquisadores do Google Brain e Google Research (composta por cientistas brilhantes, incluindo os nomes lendários Vaswani, Shazeer e Polosukhin) queria resolver os problemas de lentidão e perda de contexto de memória que afligiam as arquiteturas de deep learning na época, focando em tradução automática. Eles queriam responder a seguinte pergunta: podemos eliminar as tradicionais arquiteturas de processamento sequencial (RNNs e CNNs) e usar APENAS um mecanismo chamado "Atenção" para construir um modelo focado em linguagens?

## 🔬 Como foi feito? (metodologia simples)
Eles projetaram uma nova rede neural totalmente diferente. Propuseram que, ao invés de ler um texto numa linha de tempo sequencial travada, a IA poderia calcular vetorialmente (matemática pura de matrizes) o nível de relevância (atenção) que cada palavra de um texto tem em relação a todas as outras palavras daquele texto. Introduziram inovações como *Self-Attention*, *Multi-Head Attention* (atenção múltipla com diferentes focações) e *Positional Encoding* (marcar posições temporalmente na matemática). Depois, testaram sua nova arquitetura — chamada **Transformer** — em bases massivas de tradução em vários idiomas, como do Inglês para o Alemão e para o Francês.

## Descobertas que vão te surpreender (números)
Os resultados quebraram completamente os recordes do Estado da Arte (SOTA) da época em processamento de linguagem natural. Além de atingir pontuações inigualáveis de acerto nas traduções (score BLEU incrível), a grande surpresa era a **velocidade**! Como a arquitetura do Transformer permitia que todos os dados fossem processados de forma completamente paralela nas GPUs (ao invés de um após o outro), os custos e tempos de treinamento despencaram de semanas com modelos inferiores para frações desse tempo, possibilitando treinar modelos numa escala massiva e sem precedentes. O paper se tornou histórico: tem bem mais de 100.000 citações no mundo científico hoje.

## Citação marcante
*"Propomos o Transformer, um modelo de arquitetura simples baseado unicamente em mecanismos de atenção, dispensando completamente as estruturas de recorrência e convoluções... Nossos experimentos mostram que esses modelos são de qualidade superior, além de serem mais paralelizáveis e requerem significativamente menos tempo para treinar."*

## O que muda para você?
Muda o seu entendimento base de como o universo da IA funciona hoje sob o capô. A "Janela de Contexto" que você vê ao usar o ChatGPT, a noção de "Tokens", a "Atenção" aos seus prompts longos... tudo isso deriva puramente dos mecanismos descritos neste artigo. A partir de hoje, você vai deixar de enxergar o ChatGPT como uma magia insondável e passar a respeitá-lo como o que ele realmente é: uma complexa calculadora vetorial em alta dimensão de probabilidades construída sob a majestosa arquitetura dos Transformers.

## Conceitos Relacionados
[[11 - Transformer]] | [[13 - Autoatencao]] | [[12 - Embeddings]] | [[15 - LLM]]
