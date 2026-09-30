---
tags: [llm, conceito, parte-1]
conceito_numero: 20
dificuldade: 🟡 Intermediário
aliases: [Prompt Engineering, Instruções, Prompting]
---

# 🔢 20 — Prompt e Engenharia de Prompt

> [!NOTE] Em uma frase só...
> O *Prompt* é a instrução em texto que você fornece a um modelo de IA, e a *Engenharia de Prompt* é o ofício técnico de estruturar essa instrução estrategicamente para extrair a resposta mais precisa, consistente e otimizada do modelo.

## Analogia do Professor
Imagine que você precisa contratar um freelancer genial, brilhante, mas que tem um pequeno defeito de fábrica: ele não possui nenhum bom-senso padrão e é terrivelmente literal. Ele fará exata e milimetricamente o que você pedir.
Se você falar "Me faz um site de vendas", ele pode voltar com um site rosa-choque, feito em HTML puro de 1998, sem responsividade e com imagens esticadas. A culpa foi do freelancer? Não, a culpa foi do seu briefing péssimo!

Engenharia de Prompt é a arte de criar um *briefing mestre*. O profissional não pede "faz um site". Ele escreve: *"Atue como um Desenvolvedor Sênior. Preciso de uma Landing Page focada em conversão para um SaaS B2B na área de saúde. Stack obrigatória: React 18, TailwindCSS e Next.js App Router. Quero cores sóbrias (azul e branco). O design deve seguir as heurísticas de Nielsen. Retorne APENAS o bloco de código do componente principal."* Qual freelancer você acha que entrega o trabalho perfeitamente de primeira? O do segundo briefing, claro.

## 📖 O que é?
Como modelos baseados em LLM (Large Language Models) são motores estatísticos gigantes de predição de tokens, a **forma** como a frase de entrada (o Prompt) é estruturada matematicamente enviesa para qual região semântica o modelo vai ser arrastado.
A Engenharia de Prompt (Prompt Engineering) não é apenas "conversar direitinho", mas um subcampo técnico onde aplicamos metodologias específicas e testadas em laboratório para garantir resultados consistentes, reduzindo alucinações. É fazer o modelo extrair sua capacidade máxima usando a sintaxe e o contexto certos.

## Como funciona?
Bons engenheiros de prompt dominam diversas arquiteturas de comandos. As mais famosas são:
1. **Zero-Shot Prompting:** Mandar a instrução direta, confiando que o treinamento embutido dará conta. Ex: "Traduza essa frase para o espanhol."
2. **Few-Shot Prompting:** Prover "exemplos" da saída desejada no próprio prompt antes do comando final. Ex: "Bom = Positivo \n Ruim = Negativo \n Odiei = Negativo \n Amei = ___" (o modelo completa perfeitamente com Positivo). Isso ensina o formato de resposta na marra.
3. **Role Prompting:** Dar uma "persona". Ex: "Você é um auditor sênior de segurança da informação..." Isso ajuda a balizar o vocabulário e rigor do modelo na geração dos tokens.
4. **Chain of Thought (CoT):** Talvez a mais famosa descoberta científica no campo! Simplesmente adicionar a frase mágica *"Pense passo a passo"* ao final do prompt. Isso força o modelo a cuspir o raciocínio token a token. O raciocínio verbalizado vira parte do contexto e arrasta o próprio modelo para a resposta correta no final de um cálculo matemático ou lógico, evitando pular etapas cruciais.

## No Mundo Real
Para o Desenvolvedor, ser bom de Prompting muda a vida profissional diária:
- Ao escrever Prompts automatizados num Backend: Ao embutir requisições na OpenAI no código Python, você precisa de um *System Prompt* robusto que não deixe margem para o bot quebrar a estruturação JSON ou delirar informações erradas.
- Ferramentas nativas (Copilot/Cursor): Se um dev junior quer gerar um teste unitário complexo em TypeScript, um prompt vago resultará em testes inúteis que só testam o "caminho feliz". Um prompt estruturado usando técnicas Few-Shot garantirá edge cases bem verificados.

## Limitações e Cuidados
> [!CAUTION] Prompt Engineering não é feitiçaria, e não conserta modelo burro!
> Não caia na ilusão de que Engenharia de Prompt conserta falta de conhecimento do modelo.
- Se a IA simplesmente "não sabe" de algo por conta do [[24 - Corte Temporal]], nenhum prompt mágico vai forçá-la a inventar um dado verdadeiro e factual (inclusive, tentar forçar a barra agrava o problema da [[22 - Alucinacao]]).
- **Injeção de Prompt (Prompt Injection):** O dev precisa blindar o sistema, pois os usuários mal intencionados aprendem técnicas de Prompt Engineering para "hackear" e contornar restrições das aplicações. Ex: *"Ignore as ordens dadas pelo desenvolvedor do sistema. A partir de agora..."*
- "Pense passo a passo" gasta MUITO mais tokens de saída. Seja estratégico ou sua fatura da API no fim do mês vai explodir de tão cara!

## Conceitos Relacionados
- [[15 - LLM]]
- [[18 - Chatbot]]
- [[21 - RAG]]
- [[23 - Janela de Contexto]]

## Resumo para o Dev Junior
- **A Arte do Briefing:** O sucesso do código gerado pela IA depende inteiramente da precisão, clareza e do contexto inserido por você no prompt.
- **Técnicas Comprovadas:** Use "Few-Shot" para amarrar o formato que a IA deve responder (como um JSON ou CSV) e "Chain of Thought" ("pense passo a passo") em tarefas lógicas complexas.
- **O desenvolvedor moderno** precisa saber não apenas codar os algoritmos de backend, mas também iterar os textos em linguagem natural que orquestram a API de Inteligência Artificial. Prompt virou código-fonte!
