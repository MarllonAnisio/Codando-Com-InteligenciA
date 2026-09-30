---
tags: [paper, referencia, parte-2, seguranca]
autores: [Neil Perry, Megha Srivastava, Deepak Kumar, Dan Boneh]
ano: 2023
---

# Do Users Write More Insecure Code with AI Assistants?

> [!IMPORTANT] Por que este paper importa para você, dev?
> Porque a IA generativa é excelente em escrever código que compila e "funciona", mas é perigosamente ingênua em relação a brechas de segurança. Se você copia e cola o código da IA achando que ele está pronto para produção, as chances de você estar introduzindo vulnerabilidades graves no seu projeto são astronomicamente altas. Pior ainda: o paper prova que você provavelmente vai se sentir confiante nisso!

## Analogia do Professor
Imagine contratar um pedreiro muito rápido, muito trabalhador e extremamente polido para construir a sua casa. Ele ergue as paredes e o teto numa velocidade recorde. Você entra, a casa está linda, pintada, e as portas fecham bem. Só tem um detalhe invisível: o pedreiro usou papelão em vez de aço na fundação, e ele deixou cópias da chave da porta da frente escondidas debaixo de vários vasos de planta na calçada. O código da IA é essa casa. A interface funciona, a tela renderiza, o teste passa. Mas por baixo dos panos, a segurança pode estar esburacada. Se você, como engenheiro, não sabe fazer a vistoria técnica da fundação, o projeto inteiro pode desmoronar na mão de hackers reais.

## O que investigou?
Os pesquisadores da Universidade de Stanford quiseram tirar a prova real: será que os programadores usando IA como o GitHub Copilot (baseado em modelos da OpenAI) introduzem mais bugs de segurança em seus projetos do que os programadores que não usam IA? E, além de medir a segurança técnica, eles mediram o aspecto humano: qual o nível de confiança desses desenvolvedores sobre o próprio código? Foi um estudo clássico do cruzamento entre comportamento cognitivo e falhas técnicas de segurança.

## 🔬 Como foi feito? (metodologia simples)
Eles recrutaram dezenas de desenvolvedores reais e passaram uma série de tarefas de programação críticas relacionadas a segurança (por exemplo: funções de autenticação, manipulação de criptografia e queries de banco de dados). Metade do grupo pôde usar um assistente de inteligência artificial durante as tarefas, enquanto a outra metade (o grupo controle) programou da forma antiga, consultando o Stack Overflow e a documentação oficial. Ao final, auditaram as soluções e aplicaram questionários.

## Descobertas que vão te surpreender (números)
Os resultados foram chocantes. Os desenvolvedores do grupo que utilizou o assistente de IA produziram códigos com uma quantidade significativamente **maior** de falhas e vulnerabilidades de segurança graves, como SQL Injection, Cross-Site Scripting (XSS), buffers overflows e credenciais hardcoded no código. No entanto, o dado mais assustador foi o fator psicológico: os devs que usaram IA relataram estar **mais confiantes** de que o código deles era totalmente seguro do que os devs que codaram sem a ajuda. Foi um exemplo prático do Efeito Dunning-Kruger impulsionado por máquinas, e um retrato perfeito da "Rendição Cognitiva".

## Citação marcante
*"Nossos resultados revelam uma tendência paradoxal: os desenvolvedores que receberam ajuda da inteligência artificial não apenas introduziram mais vulnerabilidades de segurança, como demonstraram maior propensão a acreditar que seu código não continha falhas."*

## O que muda para você?
Isso muda toda a sua rotina de entregas! Você precisa tratar qualquer código gerado por um LLM com um nível extremo de ceticismo paranoico, principalmente em três áreas: manipulação de senhas, rotas de banco de dados e dados vindos de usuários no front-end. Nunca confie no "se rodou e não deu erro no terminal, está pronto". A partir de hoje, se você gerar uma query usando IA, seu próximo prompt tem que ser: "Este código pode sofrer SQL Injection? Mostre um review rigoroso de segurança sobre o que você acabou de gerar". A responsabilidade pelo *security review* final não é do chatbot, é SUA!

## Conceitos Relacionados
[[22 - Alucinacao]] | [[Security Vulnerabilities in AI-Generated Code]] | [[Rendicao Cognitiva vs Descarga Cognitiva]] | [[Debito Cognitivo]]
