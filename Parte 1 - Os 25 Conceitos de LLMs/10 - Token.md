---
tags: [llm, conceito, parte-1]
conceito_numero: 10
dificuldade: 🟡 Intermediário
aliases: [Tokens, Tokenização]
---

# 🔢 10 — Token

> [!NOTE] Em uma frase só...
> O token é a unidade fundamental e atômica de texto que um modelo de linguagem consegue ler, processar e gerar — podendo ser uma palavra inteira, um pedaço de palavra, ou apenas uma vírgula.

## Analogia do Professor
Pense em tokens como as **sílabas** na mente de uma criança que está dando os primeiros passos na alfabetização infantil 🧒. Quando a criança olha para a página e tenta ler a palavra "gato", ela ainda não tem a fluência veloz para ler o bloco completo instantaneamente. Ela olha e processa separadamente em blocos sonoros: "ga" e "to", e logo após junta os dois no cérebro para extrair o sentido do pequeno animal. O nosso assombroso LLM faz a mesma coisa! Ele não possui olhos para ler "Inconstitucionalissimamente" como você. Na engrenagem interna do seu motor numérico triturador de textos, ele quebra tudo isso em pequenos pedaços fáceis de digerir: `[In][constitu][cional][issima][mente]`. Ele lê e cospe o texto pedaço por pedaço, como as sílabas da criança. A diferença é que a máquina faz isso para os milhões de palavras de todos os livros que já existiram na história, repetidamente e milhares de vezes em um único segundo!

## 📖 O que é?
No grandioso ecossistema dos Modelos de Linguagem, a máquina não faz ideia do que são "letras" em ASCII ou "palavras soltas" nos dicionários da nossa gramática. Tudo precisa ser convertido para uma lista colossal de fragmentos organizados chamados **Tokens**.
A Tokenização é esse processo fundamental mecânico de fatiar e destruir qualquer input gigantesco que você digitar no prompt (ou que o modelo estiver gerando na saída) em unidades discretas de processamento que serão posteriormente convertidas em números de IDs e inseridas na engrenagem pesada do algoritmo.
Esses tokens podem assumir formatos bizarros e incrivelmente variados:
- Palavras super curtas ou incrivelmente comuns muitas vezes viram um único token ("Eu", "gosto").
- Espaços em branco muitas vezes se unem ao começo da palavra seguinte (" de").
- Sinais minúsculos de pontuação crua e obscura (como "?", "!", ou colchetes) ganham os seus IDs próprios independentes para que a máquina saiba do fim de um ciclo ou do assombro.
- Palavras robustas da nossa língua ou línguas sem grande foco no inglês são terrivelmente multiladas e separadas na máquina (ex: "transformador" vira facilmente 3 blocos como `[trans][form][ador]`).

## Como funciona?
O universo mágico ocorre de maneira impiedosa antes mesmo de qualquer inteligência atuar na nuvem de processamento:
1. Você envia alegremente uma string "O dev junior foi treinar!"
2. Um sistema rígido chamado 'Tokenizer' recebe e fatiará sua entrada baseada em regras severas de frequência em dicionários (usando técnicas famosas como Byte-Pair Encoding).
3. A string vira um array, ex: `["O", " dev", " junior", " foi", " treinar", "!"]`.
4. Cada string no array recebe um ID fixo e pré-cadastrado no dicionário massivo do modelo (ex: o token " dev" equivale ao número `14890`).
5. A Rede Neural super pesada recebe uma modesta e longa matriz de números puros para calcular a estatística pesada e o avanço semântico daquele bloco de ideias.

> [!TIP] Tokens e o Português (e o Custo!)
> Uma aproximação global estrita dita que `1 token ≈ 4 caracteres` textuais (ou cerca de `¾` de uma palavra) de uso mediano no **idioma nativo do Inglês**.
Mas cuidado! O Português ou idiomas como o Japonês possuem muito mais tokens fracionados bizarros por vocábulo longo que não são fáceis nativamente na memória dos modelos ocidentais. Então, um texto gigante em PT-BR consumirá e torrará os limites de tokens da máquina drasticamente mais veloz do que o mesmíssimo exato longo texto brilhantemente traduzido no prompt em puro Inglês!

## No Mundo Real
O Dev Moderno tromba na barreira e no preço dos amados Tokens no dia-a-dia de sua empresa!
- **Dinheiro na API**: Os fornecedores formidáveis de modelos comerciais em nuvem (Google Gemini Ultra, Anthropic, OpenAI) NÃO cobram a generosa conta mensal pelo "tamanho de KB das respostas" em texto limpo. Eles cobram rigorosamente em centavos estritos pelo uso total numérico de TOKENS (somando cada fragmento do input processado, mais cada fragmento exaustivamente e brutalmente gerado no output).
- **As Respostas Digitando**: Aquele lindo e deslumbrante efeito que adoramos no ChatGPT, onde vemos a impressionante resposta sendo cuspida e dedilhada no vidro mágico na tela do browser (o efeito "stream") é o reflexo honesto das engrenagens. O modelo, em sua essência determinística, apenas calcula pesadamente em sua rede monstruosa oculta e retorna um mísero novo token por vez no servidor, a cada ciclo de sua máquina impetuosa!

## Limitações e Cuidados
- **As Janelas Rígidas e Severas (O Limite Físico Máximo)**: Todos os impressionantes sistemas carregam um duro e inflexível teto global intransponível sobre o tamanho impetuoso do cesto. O limitadíssimo GPT-3.5 travava nos 16k tokens, e sofria perda imediata de sanidade e esquecimento severo para trás! Hoje a fronteira avança agressivamente (GPT-4 Turbo lendo formidáveis 128k, Gemini 1.5 Pro suportando o inacreditável volume insano de 1 a 2 Milhões de tokens). Mas uma vez cheio o cesto e batido no limite máximo da infraestrutura na memória da conversa, ele corta sua janela cruelmente sem dó, ou joga e purga os blocos antigos maravilhosos do passado da sua conversa fora num buraco negro!
- **O Código Explode os Limites**: Mandar longos, confusos e feios blocos intermináveis de dados pesados JSON desminificados para ele ler não gera "textos bonitos", gera poluição massiva nos tokens por causa das dezenas de chaves obscuras, aspas feias em excesso, e chaves abrindo infinitamente! A máquina esgota o limite e a sua grana voa.

## Conceitos Relacionados
[[09 - Modelo de Linguagem]] | [[11 - Transformer]] | [[12 - Embeddings]] | [[23 - Janela de Contexto]]

## Resumo para o Dev Junior
- É puramente e simplesmente a menor peça fracionada individual atômica que compõe intimamente o processamento do longo universo das falas artificiais nos modelos linguísticos.
- Modelos fatiam os textos brutos na base para operá-los em formatos de puros blocos atômicos inteiros numéricos no array de dados do input.
- Você no mundo empresarial é impiedosamente e dolorosamente tributado na carteira (na API de uso) por cada milésimo de cota de token que consome da requisição, em português tende a consumir volumes bem mais densos nas frases.
- Todos impõem um esmagador e impiedoso limite de memória operacional volátil diária da Janela (ex: até 128k blocos e não passa disso!) de uso imediato por cada complexo chat mantido da empresa!
