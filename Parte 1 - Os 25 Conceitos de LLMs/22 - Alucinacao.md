---
tags: [llm, conceito, parte-1]
conceito_numero: 22
dificuldade: 🟡 Intermediário
aliases: [Alucinação, Hallucination, Confabulação]
---

# 🔢 22 — Alucinação

> [!NOTE] Em uma frase só...
> Alucinação ocorre quando um modelo de linguagem gera com extrema confiança e naturalidade informações factualmente incorretas, inexistentes ou absurdas, apresentando-as como se fossem verdades absolutas.

## Analogia do Professor
Pense na Alucinação da IA como se fosse aquele colega de turma na época da escola que adorava aparecer e nunca ficava calado. Chega o dia do seminário de história, e ele não leu a matéria, não sabe absolutamente nada sobre a Revolução Francesa. O professor faz uma pergunta difícil, e o que ele faz? Em vez de dizer "Professor, infelizmente eu não estudei e não sei responder", ele enche o peito e inventa, na hora, toda uma teoria complexa de que Napoleão tinha um dragão de estimação chamado Roberto que o ajudava a vencer batalhas.
O pior de tudo? Ele fala isso com tanta eloquência, gramática perfeita, postura de intelectual e confiança inabalável, que parte da turma acaba acreditando na história do dragão Roberto. O modelo de inteligência artificial é exatamente esse colega "enrolador", operando com autoconfiança algorítmica.

## 📖 O que é?
No ecossistema dos Modelos de Linguagem de Grande Escala (LLMs), o termo "alucinar" (ou confabular) é técnico. Descreve o fenômeno inato onde o sistema retorna *outputs* que parecem plausíveis e coerentes linguisticamente, mas não são factualmente embasados nos dados da realidade.
Não é um "bug" de programação onde esqueceram um ponto e vírgula, é uma **característica intrínseca** da própria natureza probabilística dessas redes neurais. O modelo é projetado e otimizado matematicamente para ser fluente e completar o texto com as palavras mais estatisticamente aderentes. Como não possui "bom-senso", "raciocínio moral", ou um banco de dados relacional clássico de "fatos da vida" consultável em tempo real, sua prioridade é sempre **maximizar a coerência textual**, mesmo que o preço disso seja sacrificar a veracidade.

O LLM produzirá uma mentira com a exata mesma mecânica matemática que produz uma verdade factual incontestável. Ele não sabe que não sabe.

## Como funciona?
Muitos elementos do processamento intensificam ou reduzem a ocorrência das alucinações durante a fase de geração:
- Se o tópico da conversa teve uma raríssima cobertura no corpus gigantesco da internet (seus dados de treinamento base).
- Ambiguidades semânticas que ativam caminhos de rede incorretos e confundem o contexto geral.
- Configuração de [[14 - Temperatura e Amostragem]] elevada. Ao aumentar a Temperatura, você estimula o modelo a escolher tokens que estavam no fim da fila de probabilidade. Isso é mágico para a escrita criativa (histórias e brainstorms), mas mortal e desastroso se você precisa de exatidão matemática, citações bibliográficas reais ou de um código refatorado.
- Exigências estritas no Prompt (por exemplo: "Diga-me sim ou não!"), onde o modelo, mesmo incerto das possibilidades e contradições, se sentirá forçado estatisticamente a acatar a formatação do humano, tirando uma conclusão inventada do nada.

## No Mundo Real
Casos práticos onde a alucinação ataca e causa estragos (Atenção redobrada!):
- **O caso clássico dos "Papers" falsos:** Pesquisadores amadores e até advogados de fato (ocorreu um escândalo no mundo jurídico de Nova York) pediram ao ChatGPT para criar um documento de defesa com base em jurisprudências judiciais precedentes. O modelo inventou nomes de casos jurídicos perfeitamente estruturados e formatados do zero, citando juízes e datas que não existem.
- **Links "quebrados" fantasmagóricos:** O modelo cita uma suposta fonte incrível e passa um link em formato perfeito (`https://siteconhecido.com/docs/api-legal`). Quando o Dev vai clicar animado... Erro 404. O modelo não checou a internet viva, só fabricou algo semelhante a dezenas de URLs de treinamento.
- **Códigos com *Bugs* Invisíveis:** Você pede uma função Python, e a IA gera a função referenciando perfeitamente os métodos internos e atributos da biblioteca `pandas` ou `requests`. Tudo parece brilhante e sintaticamente lindo, mas o método referenciado simplesmente não existe no escopo real. A IA inventou a lib ou alucinou uma *feature* misturando ideias de diferentes linguagens no liquidificador dos pesos neurais.

## Limitações e Cuidados
> [!CAUTION] Ceticismo sempre. A IA erra e omite com "cara de paisagem".
> A principal lição de uso responsável e de segurança: nunca, sob nenhuma circunstância, terceirize completamente a aprovação de fatos e do conhecimento crítico para uma interface isolada de texto gerativo puro.
1. Combata as Alucinações com ferramentas poderosas de arquitetura de software, como o próprio [[21 - RAG]], fundamentando as respostas em blocos e parágrafos ancorados fisicamente da sua base corporativa.
2. Force a citação (quando usando modelos conectivos com a web, exija hyperlinks que existam, para validação externa rigorosa e manual sua antes da aprovação).
3. Reduza sua barra de temperatura (`temperature = 0.0` ou `0.1`) e defina os System Prompts rígidos, declarando as cláusulas *"Se você não encontrar a exata e incontestável resposta nas fontes a seguir listadas, não ouse adivinhar e declare francamente 'não tenho essa informação'."*

## Conceitos Relacionados
- [[09 - Modelo de Linguagem]]
- [[15 - LLM]]
- [[21 - RAG]]
- [[24 - Corte Temporal]]
- [[25 - Vies Algoritmico]]

## Resumo para o Dev Junior
- **A IA mente bem:** Ela é excelente em completar frases gramaticais com estatística, não em atuar como bibliotecária ou consultora da enciclopédia da verdade. Quando espremida e na dúvida, ela optará pela mentira convincente.
- **Tipos Frequentes de Alucinação:** Invenções completas e mirabolantes (bibliografias, links fantasma 404, metodologias falsas na API e datas esquisitas do calendário).
- **Controle Técnico:** Como o Dev entra nessa história? Nós limitamos a loucura injetando textos blindados no prompt (RAG), baixando os parâmetros da Temperatura da requisição e testando com firmeza as funções e respostas dadas em compiladores (Nunca lance código no "Ctrl+C/Ctrl+V" para produção no escuro).
