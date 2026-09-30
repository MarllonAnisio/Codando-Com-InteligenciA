---
tags: [llm, conceito, parte-1]
conceito_numero: 25
dificuldade: 🟡 Intermediário
aliases: [Algorithmic Bias, Preconceito de IA, Viés de Máquina]
---

# 🔢 25 — Viés Algorítmico (Algorithmic Bias)

> [!NOTE] Em uma frase só...
> O Viés Algorítmico é o fenômeno preocupante onde as IAs herdam, replicam e chegam a amplificar os estereótipos sistêmicos, preconceitos sociais e injustiças humanas que já estavam ocultos — de forma acidental ou estrutural — na base gigantesca de dados usada em seu treinamento original.

## Analogia do Professor
Imagine que você tem a brilhante ideia de criar uma criança ensinando-a a observar a humanidade única e exclusivamente através de velhos livros empoeirados escritos por homens ocidentais de uma elite europeia de três séculos atrás, e através dos roteiros mais batidos dos filmes de Hollywood. Nunca permitiu que ela conversasse com o mundo de fora.

Quando essa criança finalmente crescer e virar escritora, como você acha que ela irá descrever o mundo? Ela fará narrativas rasas onde enfermeiras sempre são do sexo feminino e frágeis, líderes e CEOs sempre usam terno cinza, os cenários paradisíacos são sempre nos moldes norte-americanos, e culturas minoritárias são completamente esquecidas, estereotipadas ou vilanizadas.
A criança não faz isso porque ela é essencialmente perversa, mesquinha e cruel por natureza. Mas por conta do *input* corrompido; esse foi todo o repertório mental ofertado a ela para prever os cenários. A IA gigante age, aprende e entrega o resultado na mais perfeita semelhança aos rastros obscuros do viés deixado nos fóruns e blogs antigos da humanidade!

## 📖 O que é?
No ramo das inteligências artificiais (e em Machine Learning clássico), quando o Dev sobe seu modelo, ele não ensina linha a linha da lógica com "If-Elses". Ele apenas joga volumes massivos de informações em planilhas/textos para que a rede neural encontre as correlações mais densas e mais frequentes.
O problema do mundo real é que o comportamento histórico não é neutro. O mundo tem injustiças colossais.
Se os dados de currículos e salários históricos de uma empresa contêm mais homens (ou pagam mais aos homens), ao programar uma IA para "achar o candidato ideal previsor de lucros" com a técnica padrão de busca matemática para a contratação, ela infere fatalmente que *"Ser Mulher reduz a estatística de sucesso dessa empresa, logo, devo ranquear os currículos de perfis femininos no fundo da fila"*.

Existem dezenas de ramificações do Viés, sendo os principais:
- **Representação Desigual:** Se os desenvolvedores usam repositórios de fotos da Califórnia (compostos pela imensa maioria de brancos), o sistema de análise e reconhecimento de rostos policiais falhará com margens gigantes em pessoas negras (trazendo trágicas prisões injustas decorrentes da IA).
- **Associação de Palavras Tóxicas:** Por vasculhar comentários bizarros nas caixas abertas do Reddit, o LLM aprende linguagens corrosivas (o infame *Toxic Output*).

## Como funciona?
Do ponto de vista puramente técnico no fluxo do ML:
1. **Dados envenenados (Garbage in):** Como as distribuições contidas nas colunas e amostras da DB estão em absoluto desequilíbrio e não são corrigidas artificialmente, as interconexões da rede vão fortalecer (no Backpropagation, peso/bias matemático na veia!) apenas aquele caminho excludente de um padrão ocidental machista.
2. **Propagação Automática do Padrão (Garbage Out):** Durante a Geração de imagens com IAs visuais de Difusão e no LLM, a rede cospe a amostra "mais provável" do treinamento inteiro. E, por consequência cruel de mercado, acaba massificando saídas geradas preconceituosas ou insensíveis, já que elas ganharam o status numérico de "Verdade Absoluta" nas matrizes.

## No Mundo Real
E para nós, profissionais na ponta, como essa catástrofe social chega?
- O caso verídico e chocante (2018) do Algoritmo de RH da Amazon — que precisou ser jogado de fato no lixo ao se descobrir que penalizava severamente (baixava as notas) todos os arquivos PDF de currículos que contivessem o termo "Universidade das Mulheres" ao longo do corpo do texto, porque no histórico, não haviam mulheres antigas trabalhando num padrão corporativo.
- Ferramentas do campo de "Credit Score", de aprovação de financiamento bancário autônomo e de risco judiciário que embutem racismo velado em códigos postais segregados dos clientes em bases de governos locais.
- E o desastre linguístico nos LLMs: Pedir para desenhar *"Um trabalhador recolhendo lixo"*, e ter como saída de imagens, negros e nordestinos em situações de abandono.

## Limitações e Cuidados
> [!WARNING] Não encare a máquina como neutra! A Matemática também tem preconceito na IA!
> Desenvolvedores perigosos e imprudentes abraçam a narrativa de que *"Não existe erro na decisão da minha máquina, os números não mentem!"*.
- Muito pelo contrário. Como guardiões das aplicações modernas, desenvolvedores devem promover auditorias ativas. Existem times voltados apenas em ataques e sabotagem da própria ferramenta ("Red-Teaming"!) na base da empresa antes de permitir soltá-la em público no *Deploy* das APIs do Chatbot.
- Para frear isso, engenheiros de dados gastam suor na curadoria extrema dos datasets, além de utilizarem a exaustiva fase pós-treinamento através de humanos avaliando resultados (*RLHF* do português e suas matrizes representativas plenas). Jamais ponha as mãos no fogo pelo algorítimo!

## Conceitos Relacionados
- [[06 - Treinamento]]
- [[16 - IA Generativa]]
- [[22 - Alucinacao]]

## Resumo para o Dev Junior
- **Abreviação:** Viés de IA / Algorithmic Bias.
- **Sintoma Crítico:** Respostas e predições baseadas em estereótipos grotescos sociais com origem em racismo, sexismo e disparidades geográficas/culturais do mundo analógico.
- **O Fator do Espelho:** A Inteligência Artificial da sociedade serve de espelho da humanidade atual! Os repositórios digitais antigos não nasceram limpos de opiniões deturpadas e preconceitos na web aberta.
- **Responsabilidade do Dev:** Auditoria humana forte, inclusão de dados equilibrados artificialmente antes do treino da matriz matemática e, no Front-end e Back-End, bloqueios e diretrizes sólidas de governança moral de resposta do sistema.
