---
tags: [llm, conceito, parte-1]
conceito_numero: 23
dificuldade: 🟡 Intermediário
aliases: [Context Window, Janela de Memória]
---

# 🔢 23 — Janela de Contexto (Context Window)

> [!NOTE] Em uma frase só...
> A Janela de Contexto é o limite máximo estrito de "memória de trabalho" de um modelo de linguagem, definindo a quantidade máxima de tokens (entrada do usuário + histórico + saída gerada) que ele consegue processar simultaneamente em uma única requisição.

## Analogia do Professor
Pense na Janela de Contexto como a bancada de trabalho de um desenvolvedor ou a mesa de estudos do aluno. O tamanho dessa mesa determina a quantidade de apostilas físicas que você consegue deixar abertas ali em cima ao mesmo tempo para consultar de uma vez só enquanto resolve a prova do ENEM.

Se a sua mesa for pequenininha (uma janela curta), você não consegue abrir 10 livros. Terá que fechar o livro de Matemática para abrir espaço e colocar o de Física. Mas, na hora que for resolver a equação da prova, você pode esquecer a fórmula porque guardou o livro. Quando um modelo "esquece" do que você disse no começo de uma conversa gigante, é exatamente porque o histórico estourou a capacidade da mesa, e a interface apagou o começo do papo para liberar espaço para as falas mais recentes. Quanto maior a Janela, maior a "mesa"!

## 📖 O que é?
Como discutimos, os LLMs (como GPT ou Gemini) são, por natureza, *stateless* (não armazenam estado permanente a cada interação). A única maneira de eles parecerem ter memória é o chatbot reempacotar todo o histórico da conversa toda vez e mandar junto com o seu próximo prompt.
Mas devido à arquitetura original do [[11 - Transformer]], esse repasse não pode ser infinito. O mecanismo matemático que cruza a atenção entre as palavras (*Self-Attention*) possui um custo computacional absurdo que crescia quadraticamente no passado.
Isso criou o limite de capacidade de leitura contínua, conhecido como **Context Window**, medido em Tokens. O que ocupa o espaço da janela:
- O System Prompt escondido.
- Todo o histórico empilhado das mensagens.
- Os anexos, códigos ou PDFs (se usando técnicas de [[21 - RAG]]).
- O espaço reservado para a saída em si que ele vai gerar como resposta.

A evolução foi gigantesca. Em 2022, o limite usual era de apenas 4.000 tokens. Hoje (2024+), modelos como o Gemini 1.5 Pro possuem uma janela assustadora de **1 MILHÃO a 2 MILHÕES de tokens**. Isso significa poder colocar livros completos, bases inteiras de código C++ e vídeos na "bancada" de uma só vez!

## Como funciona?
Quando o pacote atinge o número limite da infraestrutura da API do provedor (ex: 128k no GPT-4 Turbo):
1. A interface de desenvolvimento obrigatoriamente fará um *truncamento* (corte de dados), geralmente ejetando do fundo do histórico as conversas mais antigas.
2. A consequência direta é que a IA de repente "perde" a referência do seu nome dito na primeira mensagem ou esquece de usar aquela variável global específica declarada nas 100 primeiras linhas do seu super código colado.
3. Além disso, existe um fenômeno de engenharia de IA famoso apelidado de *"Lost in the Middle"* (Perdido no Meio). Mesmo com mesas imensas, o modelo às vezes lê muito bem e lembra o que está no exato começo da janela e no exato final da janela. Mas aquela informação pontual jogada no meio do textão gigantesco tem enorme chance de ser completamente ignorada, prejudicando a extração do fato.

## No Mundo Real
O limite dita o comportamento em design de produto:
- **Resumos longos:** Num escritório jurídico com 80 processos anexados, o desenvolvedor precisa programar o particionamento do banco e aplicar o sumário em partes antes de mandar o PDF, caso o limite do modelo de mercado mais barato acabe cedo.
- **Análise de Repositório Inteiro:** No caso do Gemini e Claude Opus, devs estão zipando a pasta `src/` de uma aplicação inteira construída em Node, enviando e escrevendo no chat: "Onde nesse balaio eu estou tomando memory leak?". A janela imensa permite refatoração arquitetônica contextual.

## Limitações e Cuidados
> [!CAUTION] Preço astronômico em grandes Janelas. O limite importa!
> Janela de Contexto gigantesca é incrível, mas cobra a conta. Literalmente!
- Nas chamadas de API, **cobra-se por Token trafegado!** Se o seu histórico de Chat atingir 100 mil tokens e você não limpar ou criar sumarizações ativas no backend, o usuário apenas digitando "Ok, concordo", vai estar re-trafegando todos aqueles milhares de palavras na rede para o modelo processar novamente. É a falência veloz do seu SaaS em infraestrutura.
- Quando a janela estoura o limite do provedor e você não tratou com try/catch no código, a API retornará o clássico e tenebroso "HTTP 400 - Context Length Exceeded", deixando a tela na cara do cliente.

## Conceitos Relacionados
- [[10 - Token]]
- [[18 - Chatbot]]
- [[19 - Inferencia]]
- [[20 - Prompt e Engenharia de Prompt]]
- [[24 - Corte Temporal]]

## Resumo para o Dev Junior
- **A Bancada:** A "Janela de Contexto" é a capacidade limite da memória temporária na hora de processar aquele único turno do diálogo, medida em blocos textuais (Tokens).
- **Inchaço Constante:** Todo arquivo, system prompt e a própria resposta anterior gastam esse precioso espaço. E como desenvolvedor, seu trabalho será podar dinamicamente essa árvore.
- **Evolução:** Saímos de pequenas janelas de 4 mil no GPT-3.5 para escalas avassaladoras de 1 milhão com o Gemini. Isso muda totalmente o paradigma: permite dar um Ctrl+C no seu sistema inteiro, não apenas numa pequena *function*.
- **Custos Ocultos:** Janelas lotadas atrasam consideravelmente o processamento (*Inference Latency*) e são caras na fatura final da Cloud API, então não dissemine dados à toa.
