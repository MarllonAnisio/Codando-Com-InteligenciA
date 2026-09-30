---
tags: [uso-responsavel, parte-2, template, gemini]
aliases: [Questionário, Template de Estudo]
---

# Template: Questionário com Gemini

## Analogia do Professor

Pensa num teste de direção. Você pode estudar o manual do DETRAN inteiro — mas a prova real é sentar no carro e mostrar que sabe dirigir.

Questionários são seu simulado pessoal. Com a IA, você tem um examinador infinitamente paciente, que cria questões novas toda vez, nunca repete a prova e te explica tudo errado que você marcar.

Use isso a seu favor.

---

## Como Usar Este Template

```
INSTRUÇÕES DE USO:
━━━━━━━━━━━━━━━━━

1. Abra o Gemini (gemini.google.com)
2. Copie o template que se encaixa no que você quer praticar
3. Substitua os campos entre [COLCHETES]
4. Cole no chat e pressione Enter
5. Interaja — não aceite passivamente!
6. Ao final, anote o que errou para revisar depois

 CRÍTICO: Verifique as respostas em fontes oficiais.
 A IA pode errar. Você precisa saber quando ela erra.
```

---

## Template 1: Questionário de Múltipla Escolha

**Quando usar:** Revisão rápida de conceitos, preparação para provas

```
════════════════════════════════════════════════════
TEMPLATE 1 — MÚLTIPLA ESCOLHA COM GABARITO EXPLICADO
════════════════════════════════════════════════════

Você é um professor especialista em [ÁREA — ex: LLMs e IA Generativa].

Crie um questionário de [NÚMERO — ex: 8] questões de múltipla
escolha sobre o tema: [TÓPICO — ex: Mecanismo de Self-Attention
em Transformers].

Para cada questão, siga EXATAMENTE este formato:

---
**Questão [N]:** [Enunciado claro e objetivo]

A) [Alternativa]
B) [Alternativa]
C) [Alternativa]
D) [Alternativa]

<spoiler>
**Resposta:** [Letra]
**Por que está certa:** [Explicação detalhada]
**Por que as outras estão erradas:**
- A) [Explicação]
- B) [Explicação]
- C) [Explicação]
</spoiler>
---

Nível de dificuldade: [BÁSICO / INTERMEDIÁRIO / AVANÇADO]
Público: estudante de TI com conhecimento básico de programação

Foco nas questões: compreensão conceitual e aplicação prática,
não memorização de fórmulas ou siglas.
════════════════════════════════════════════════════
```

---

## 🏛️ Template 2: Modo Socrático (Professor que Pergunta, não Responde)

**Quando usar:** Estudo profundo de um conceito novo, sessões de aprendizado ativo

```
════════════════════════════════════════════════════
TEMPLATE 2 — MODO SOCRÁTICO
════════════════════════════════════════════════════

Você é um professor socrático especialista em [ÁREA].

Seu objetivo é me ajudar a aprender [CONCEITO] através
de perguntas — nunca de respostas diretas.

SUAS REGRAS RÍGIDAS:
1. NUNCA dê a resposta antes de eu tentar
2. Se eu errar, diga apenas "não está correto" + dê 1 dica
3. Se eu acertar, aprofunde com uma questão mais complexa
4. Se eu ficar travado por mais de 2 tentativas, dê uma dica maior
5. No final (quando eu pedir "encerrar"), dê um resumo do que aprendi

MEU CONTEXTO:
- Nível: [INICIANTE / INTERMEDIÁRIO / AVANÇADO]
- O que já sei sobre o tema: [DESCREVA BREVEMENTE]
- O que quero entender: [OBJETIVO ESPECÍFICO]

Comece com a primeira pergunta — uma que teste o que eu
já sei sobre o tema antes de avançar.
════════════════════════════════════════════════════
```

---

## 💼 Template 3: Simulador de Entrevista Técnica

**Quando usar:** Preparação para entrevistas de emprego, estágio, processo seletivo

```
════════════════════════════════════════════════════
TEMPLATE 3 — SIMULADOR DE ENTREVISTA TÉCNICA
════════════════════════════════════════════════════

Você é um entrevistador técnico sênior de uma empresa
de tecnologia fazendo uma entrevista para vaga de
[CARGO — ex: Desenvolvedor Júnior / Estagiário de TI].

TEMA DA ENTREVISTA: [TÓPICO — ex: conceitos básicos de IA,
programação orientada a objetos, banco de dados]

INSTRUÇÕES:
- Faça uma pergunta por vez
- Aguarde minha resposta
- Avalie minha resposta com notas de 1-5 e feedback honesto
- Varie entre perguntas conceituais e práticas
- Inclua pelo menos 1 pergunta de comportamento/situação
- No final (quando eu disser "encerrar"), dê um feedback geral

COMPORTAMENTO ESPERADO:
- Seja profissional mas não intimidador
- Se minha resposta for parcial, faça perguntas de aprofundamento
- Se eu claramente não souber, passe para o próximo tema

Comece com uma pergunta de quebra-gelo sobre minha experiência.
════════════════════════════════════════════════════
```

---

## 🧩 Template 4: Gerador de Casos Práticos

**Quando usar:** Aplicar conceitos em situações reais, conectar teoria e prática

```
════════════════════════════════════════════════════
TEMPLATE 4 — CASOS PRÁTICOS E CENÁRIOS REAIS
════════════════════════════════════════════════════

Você é um arquiteto de software sênior e mentor técnico.

Crie [NÚMERO — ex: 3] cenários reais de problema que um
desenvolvedor júnior poderia encontrar no trabalho,
envolvendo o conceito de [CONCEITO].

Para cada cenário:
1. **Contexto:** Descreva a situação (empresa, sistema, problema)
2. **O Problema:** O que está errado ou precisa ser resolvido
3. **Sua Missão:** O que o dev júnior precisa fazer
4. **Pergunta:** Como você abordaria esse problema?

Depois que eu responder cada cenário, avalie minha resposta
e mostre como um dev sênior abordaria o mesmo problema.

Nível: desenvolvedor com [TEMPO] de experiência em [LINGUAGEM/ÁREA]
════════════════════════════════════════════════════
```

---

## Exemplo de Output Esperado — Template 1

Exemplo real de resultado ao usar o Template 1 para "Self-Attention":

```
Questão 1: O que o mecanismo de Self-Attention permite
que um modelo Transformer faça que as RNNs tradicionais
têm dificuldade?

A) Processar sequências de forma paralela, analisando
 as relações entre todos os tokens simultaneamente

B) Memorizar sequências mais longas usando células LSTM
 avançadas

C) Gerar texto mais rápido por usar menos parâmetros
 que redes recorrentes

D) Processar imagens e texto ao mesmo tempo usando
 atenção cruzada obrigatória

Resposta: A
Por que está certa: O Self-Attention calcula relações
entre TODOS os pares de tokens de uma só vez (paralelismo),
enquanto RNNs processam token por token em sequência...
```

---

## Usando com Senso Crítico

> [!WARNING]
> **Questões geradas por IA podem ter erros!**
>
> Antes de "gravar" uma resposta na memória:
> 1. Verifique em fontes primárias (documentações, livros, papers)
> 2. Discuta com colegas ou professores questões que parecem estranhas
> 3. Se o gabarito não fizer sentido, questione — a IA pode ter errado

> [!TIP]
> **Tip pro:** Use o mesmo conceito em duas ferramentas diferentes (Gemini e ChatGPT) e compare as questões geradas. Isso te dá uma visão mais ampla e revela inconsistências.

---

## 🔁 Ciclo de Revisão Recomendado

```
SEMANA 1: Estuda conceito → Usa Template 1 (fixação inicial)
SEMANA 2: Revisão → Usa Template 2 (aprofundamento socrático)
SEMANA 3: Preparação → Usa Template 3 (simulação de entrevista)
PRÉ-ENTREVISTA: Usa Template 4 (casos práticos)
```

---

## Conexões Importantes

- [[Ferramentas - NotebookLM Gemini ChatGPT]] — Entenda melhor cada ferramenta
- [[Como Estudar Com IA (Do Jeito Certo)]] — O fluxo completo de estudo com IA

---

*Parte 2 do curso Codando Com InteligenciA — IFPB*
