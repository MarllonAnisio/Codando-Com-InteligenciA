---
tags: [llm, conceito, parte-1]
conceito_numero: 14
dificuldade: 🟡 Intermediário
aliases: [Temperatura, Amostragem, Sampling, Top-p, Top-k]
---

# 🔢 14 — Temperatura e Amostragem

> [!NOTE] Em uma frase só...
> A temperatura e as técnicas de amostragem são os controles que definem o nível de criatividade, previsibilidade e aleatoriedade nas respostas geradas por um modelo de inteligência artificial.

## Analogia do Professor
A temperatura é basicamente o "modo de humor" do seu modelo. Imagine a seguinte cena: uma temperatura baixa (próxima de 0) é como aquele auditor fiscal no primeiro dia de trabalho — formal, extremamente preciso, metódico e sem nenhuma surpresa ou brincadeira. Ele vai te dar exatamente o que você pediu da forma mais padrão possível.

Já uma temperatura alta (próxima de 1.0 ou mais) é como aquele seu colega de equipe no happy hour de sexta-feira depois de umas cervejas: muito animado, cheio de ideias criativas, conexões inusitadas e solto na fala, mas que às vezes pode acabar falando uma grande besteira! Ajustar a temperatura é escolher qual desses "profissionais" você quer que redija o seu texto no momento.

## 📖 O que é?
No mundo dos modelos de linguagem, não existe uma única resposta "certa" para uma frase. O modelo trabalha calculando probabilidades para a próxima palavra (ou token). A **amostragem (sampling)** é justamente o processo de selecionar qual será esse próximo token a partir de uma lista de vários candidatos prováveis.

A **Temperatura** é um parâmetro matemático (um número decimal geralmente entre 0.0 e 2.0) que ajusta diretamente essas probabilidades antes da escolha final.
- **Temperatura Baixa (Ex: 0.1 - 0.3):** Favorece fortemente as palavras mais prováveis. O texto fica focado, conservador, coerente e repetível.
- **Temperatura Alta (Ex: 0.8 - 1.5):** Aumenta a chance das palavras menos prováveis serem escolhidas. O texto fica mais variado, "criativo", surpreendente e, às vezes, um tanto maluco.

Além da temperatura, existem outros controles finos como o **Top-p (Nucleus Sampling)**, que restringe a escolha apenas a um subconjunto de tokens que, somados, atingem uma probabilidade cumulativa $p$, e o **Top-k**, que pega apenas os $k$ tokens com maior chance.

## Como funciona?
Quando você envia um prompt, a rede neural gera uma lista gigante de tokens possíveis e atribui um "score" a cada um.
1. **O Ajuste da Temperatura:** Essa lista de scores passa por uma função matemática (uma softmax com o parâmetro de temperatura). Se a temperatura for menor que 1, as diferenças entre os tokens muito prováveis e os pouco prováveis aumentam absurdamente (os fortes ficam mais fortes). Se for maior que 1, a distribuição achata, e as opções menos óbvias ganham espaço.
2. **Top-k entra em cena:** Imagine que o modelo corte fora da lista tudo o que estiver abaixo da posição $k$ (por exemplo, guarda só os 40 melhores).
3. **Top-p (Nucleus Sampling):** Em vez de pegar um número fixo de itens, o modelo seleciona os tokens do topo até que a soma de suas probabilidades dê o valor $p$ (ex: 0.9 ou 90% da probabilidade total).
4. **O Sorteio Final:** Dentro dessa seleção filtrada e re-pesada, o algoritmo joga um "dado" e escolhe o token vencedor. E assim, palavra por palavra, o texto nasce!

## No Mundo Real
Onde você como desenvolvedor vai usar isso na prática?
- **Gerando Código Fonte:** Você quer uma temperatura próxima de `0.0` ou `0.1`. Se o modelo tiver que escrever uma função em JavaScript, você quer a sintaxe exata e previsível, não um código "criativo" que vai estourar um erro de compilação.
- **Análise de Dados e Extração de Fatos:** Novamente, temperatura baixa. Você precisa que a resposta seja repetível e fiel à fonte.
- **Criação de Histórias, Marketing ou Brainstorming:** Aqui você pode aumentar a temperatura para `0.8` ou `0.9`. Você quer que o modelo proponha slogans inusitados, tramas não óbvias e abordagens que você não pensaria sozinho.
- **Chatbots conversacionais variados:** Geralmente ficam com uma temperatura média-alta (em torno de `0.7`) para soarem naturais e humanos, sem ficar repetindo a mesma estrutura frasal robótica o tempo todo.

## Limitações e Cuidados
> [!WARNING] Cuidado com o "excesso de criatividade"!
> Temperatura não é sobre ser mais ou menos "inteligente", é sobre o quão "arriscadas" são as escolhas de palavras.
- Uma temperatura **muito alta** (ex: 1.5) pode gerar textos completamente desconexos, inventar palavras (neologismos bizarros) e aumentar drasticamente as alucinações factuais.
- Se você usar uma temperatura alta combinada com tarefas factuais pesadas (como pedir um resumo de um artigo acadêmico sério), o modelo tem altíssima chance de delirar e te entregar ficção científica.
- Mudar Top-p e Temperatura ao mesmo tempo pode ser um caos de tunar. Muitos engenheiros preferem travar um (ex: Top-p = 1) e mexer só no outro para entender exatamente o que está mudando.

## Conceitos Relacionados
- [[08 - Modelo]]
- [[09 - Modelo de Linguagem]]
- [[15 - LLM]]
- [[22 - Alucinacao]]

## Resumo para o Dev Junior
- **Temperatura:** Controla o quão previsível ou surpreendente o modelo vai ser na hora de escolher a próxima palavra.
- **Amostragem (Sampling):** É o processo de jogar o "dado viciado" para escolher o token com base nas probabilidades geradas.
- **Para dev:** Vai pedir código, SQL, ou extração de JSON? Temperatura no `0.0`. Sem gracinhas!
- **Para criatividade:** Brainstorming, copywriting, ou ideias gerais? Temperatura no `0.8`. Deixa a IA viajar!
- **Top-p e Top-k:** Filtros extras que impedem o modelo de escolher as opções mais bizarras do fundo do barril de probabilidades, mesmo quando a temperatura está alta.
