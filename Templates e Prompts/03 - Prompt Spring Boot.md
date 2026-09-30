---
tags: [prompt, estudo, spring-boot, backend]
aliases: [Prompt Spring Boot]
---

# 🌱 Prompt: Spring Boot e APIs REST

> [!NOTE] Sobre este Prompt
> Ideal para quem já entende Java e está entrando no mundo do backend web. Focado no funcionamento interno do framework (a "mágica" do Spring), para evitar que o desenvolvedor use as anotações sem saber o que fazem.

## 📋 Como usar
Copie o bloco de texto abaixo e cole no Gemini ou ChatGPT.

---

### O Prompt

```text
Assuma o papel de um Arquiteto de Software experiente avaliando a minha compreensão do framework Spring Boot.

Gere um questionário técnico focado em cenários reais de criação de APIs REST e funcionamento interno do Spring.

Tópicos obrigatórios:
- Injeção de Dependências e Inversão de Controle (@Autowired, ciclo de vida de um Bean)
- Stereotype Annotations (@Component, @Service, @Repository, @Controller)
- Criação de endpoints REST (@RestController, @GetMapping, @PostMapping, manipulação de DTOs)
- Tratamento de exceções globais e retornos HTTP corretos (@ControllerAdvice, @ExceptionHandler)

Regras do questionário:
1. Faça perguntas baseadas em cenários do dia a dia de um dev backend. Exemplo de estilo de pergunta: "Temos uma API de produtos que está retornando erro 500 no banco, como você interceptaria isso para retornar um erro 400 amigável com Spring Boot?"
2. Envie apenas UMA pergunta de cada vez e espere eu responder.
3. Se eu citar uma anotação, me pergunte rapidamente o que ela faz por trás dos panos antes de ir para a próxima questão.
4. Se eu errar feio, não me dê o código pronto. Diga em qual documentação ou conceito eu devo procurar a resposta e peça para tentar de novo.
5. Inicie me fazendo a primeira pergunta.
```

---

## ✅ O que fazer depois?
- Pegue o cenário da pergunta que você achou mais difícil e implemente-o em um projeto real usando o *Spring Initializr*. A teoria faz muito mais sentido depois que a aplicação sobe na porta 8080!
