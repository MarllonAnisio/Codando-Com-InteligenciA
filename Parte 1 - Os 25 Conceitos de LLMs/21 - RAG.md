---
tags: [llm, conceito, parte-1]
conceito_numero: 21
dificuldade: 🔴 Avançado
aliases: [Retrieval-Augmented Generation, Geração Aumentada por Recuperação]
---

# 🔢 21 — RAG (Retrieval-Augmented Generation)

> [!NOTE] Em uma frase só...
> RAG (Retrieval-Augmented Generation) é uma técnica de arquitetura que mistura um sistema de busca em bancos de dados externos com a capacidade de um LLM, permitindo que a IA baseie suas respostas em informações privadas, atuais e confiáveis, em vez de recorrer apenas à memória do seu treinamento antigo.

## Analogia do Professor
Pense que o LLM é aquele estudante brilhante no dia do ENEM. O problema é que o "ENEM" abrange assuntos que caíram nos jornais até 3 dias antes da prova, e o nosso aluno parou de estudar em 2023. Se cair uma pergunta hiper-recente na prova, ele vai chutar algo plausível (alucinar) e errar.

Como consertar isso? Transformando a prova normal em uma **Prova com Consulta**.
A técnica de RAG significa que, quando a pergunta cai na prova, o aluno não tenta responder usando sua memória frágil. Ele levanta, vai na enorme biblioteca do colégio, procura os livros mais relevantes sobre o assunto exato, volta para a carteira, abre as páginas que encontrou, lê os textos verídicos ali no momento, e **então** usa a sua inteligência brilhante para formular a resposta final baseada nesses livros abertos em cima da mesa. A resposta sai perfeita, embasada nas fontes e sem invencionices. Isso é o RAG em ação!

## 📖 O que é?
RAG (Retrieval-Augmented Generation) não é um modelo de IA novo, mas sim um *padrão de arquitetura de software* poderosíssimo e onipresente. Foi projetado para resolver os três maiores problemas nativos dos LLMs:
1. A **Alucinação** factual severa.
2. O **Corte Temporal** do conhecimento antigo.
3. A ignorância sobre dados fechados/privados corporativos que não estavam no treinamento original (a IA da OpenAI não sabe como funciona o manual de RH fechado do seu banco).

Ao invés de gastar dezenas de milhões de dólares fazendo *Fine-Tuning* para re-treinar a IA ensinando o manual do seu RH para ela (o que não garante o combate às alucinações), os devs usam o RAG: armazena-se a documentação numa base, recupera-se os parágrafos certos na hora da pergunta do usuário, e envia tudo no contexto pro LLM responder.

## Como funciona?
Para implementar RAG como desenvolvedor de aplicações inteligentes, você orquestra o seguinte fluxo:
1. **Ingestão (Preparação):** O seu documento PDF de regras é quebrado em pequenos pedaços (chunks). Passamos cada chunk por um modelo matemático para transformá-lo num vetor numérico complexo (usando [[12 - Embeddings]]). Salvamos esses números num **Banco de Dados Vetorial** (VectorDB).
2. **Busca (Retrieval):** O usuário digita: *"Quantos dias de atestado eu tenho direito?"*. Esse texto vira embedding. O banco de dados vetorial caça os 5 chunks do manual do RH que são matematicamente mais "parecidos em significado" com a pergunta (Busca Semântica).
3. **Geração (Augmented Generation):** O seu backend monta um super prompt: *"Baseado estritamente no texto a seguir [INSERE OS 5 CHUNKS AQUI], responda à pergunta: Quantos dias de atestado... Se não estiver no texto, diga que não sabe."*
4. O LLM mastiga tudo e cospe a resposta perfeita. E o melhor? Você pode botar um link de fonte apontando exatamente da onde ele tirou o trecho original!

## No Mundo Real
O RAG domina as ferramentas enterprise do planeta!
- Ferramentas como o **NotebookLM** da Google fazem um RAG brilhante em cima de PDFs acadêmicos enormes que você submete pra ele resumir.
- Bots de suporte de lojas online que vasculham o banco de dados de estoque do dia atual antes de dizer se o tênis Nike 42 ainda está disponível na filial de São Paulo.
- O **Perplexity AI** funciona assim! Em vez de um banco de dados vetorial fechado, a "biblioteca" que ele pesquisa em tempo real antes de responder o prompt é simplesmente o Google Search e a Internet aberta atual.

## Limitações e Cuidados
> [!WARNING] RAG não conserta documento lixo. (Garbage In, Garbage Out)
> O calcanhar de Aquiles dessa arquitetura é o motor de busca, não o modelo gerador em si!
- Se a sua etapa de Ingestão e Busca (Retrieval) no Banco Vetorial for falha e trouxer parágrafos irrelevantes sobre as "férias de funcionários terceirizados" ao invés do "atestado", o coitado do LLM vai basear sua resposta em documentos que não têm nada a ver, falhando em resolver a queixa do usuário.
- Chunking (como você quebra os textos originais) é vital. Cortar um artigo de lei ao meio por acidente estraga o sentido do vetor.
- Cuidado com custos. Passar um caminhão de documentos pesquisados via prompt gasta muita [[23 - Janela de Contexto]] a cada clique do usuário.

## Conceitos Relacionados
- [[12 - Embeddings]]
- [[15 - LLM]]
- [[20 - Prompt e Engenharia de Prompt]]
- [[22 - Alucinacao]]
- [[24 - Corte Temporal]]

## Resumo para o Dev Junior
- **Abreviação:** RAG = Retrieval-Augmented Generation. (Buscar, Anexar, Gerar).
- **Problema resolvido:** Traz a IA para o tempo real e permite o uso de documentos restritos corporativos sem custo gigante de treinamento.
- **Funcionamento:** O usuário pergunta → o backend pesquisa em banco de dados o conteúdo relevante (usando vetores) → anexa o resultado num super-prompt invisível → a IA lê tudo de uma vez e redige a resposta.
- **Transparência:** Essa abordagem permite citar bibliografias e fontes (citação de qual PDF originou a resposta), garantindo credibilidade técnica.
