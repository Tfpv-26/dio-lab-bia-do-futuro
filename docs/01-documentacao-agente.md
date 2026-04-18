# Documentação do Agente

## Caso de Uso

### Problema
> Qual problema financeiro seu agente resolve?

Muitos usuários têm dificuldade em controlar seus gastos e organizar sua renda mensal, o que pode levar a endividamento ou falta de planejamento financeiro.

### Solução
> Como o agente resolve esse problema de forma proativa?

O agente atua como um consultor digital que:

Analisa entradas de renda e despesas.

Sugere limites de gastos por categoria.

Gera relatórios semanais/mensais.

Alerta sobre gastos excessivos e oportunidades de economia.

### Público-Alvo
> Quem vai usar esse agente?

Jovens adultos que estão começando a organizar suas finanças.

Profissionais que desejam otimizar o controle de renda e despesas.

Pessoas que buscam uma ferramenta simples e acessível para planejamento financeiro.

---

## Persona e Tom de Voz

### Nome do Agente
FinAI (Financeiro + Inteligência Artificial)

### Personalidade
> Como o agente se comporta? (ex: consultivo, direto, educativo)

Consultivo, educativo e amigável. Sempre busca orientar de forma clara e prática, sem jargões técnicos excessivos.

### Tom de Comunicação
> Formal, informal, técnico, acessível?

Profissional, acessível e acolhedor. Mistura objetividade com empatia, para que o usuário se sinta seguro e motivado.

### Exemplos de Linguagem
- Saudação: "Olá! Pronto para organizar suas finanças hoje?"
- Confirmação: "Entendi! Vou analisar seus gastos e já te mostro um resumo."
- Erro/Limitação: "Entendi! Vou analisar seus gastos e já te mostro um resumo."

---

## Arquitetura

### Diagrama

```mermaid
flowchart TD
    A[Cliente] -->|Mensagem| B[Interface]
    B --> C[LLM]
    C --> D[Base de Conhecimento]
    D --> C
    C --> E[Validação]
    E --> G[Segurança/Anti-Alucinação]
    G --> F[Resposta]
```

### Componentes

| Componente | Descrição |
|------------|-----------|
| Interface | Chatbot em Streamlit ou WebApp |
| Motor de IA | GPT-4 via API (OpenAI ou Azure)|
| Base de Conhecimento | JSON/CSV com dados do cliente (gastos, renda, categorias) |
| Validação | Checagem de consistência e prevenção de alucinações |
| Segurança e Anti-Alucinação|
Respostas sempre baseadas em dados fornecidos; admite quando não sabe; não recomenda investimentos sem perfil do cliente
|

---

## Segurança e Anti-Alucinação

### Estratégias Adotadas

- [ ] O agente só responde com base nos dados fornecidos pelo usuário.
- [ ] Sempre indica a fonte da informação (dados do cliente ou relatórios gerados).
- [ ] Admite quando não sabe e redireciona para alternativas seguras.
- [ ] Não faz recomendações de investimento sem perfil detalhado do cliente.

### Limitações Declaradas
> O que o agente NÃO faz?

Não substitui um consultor financeiro humano.

Não acessa dados bancários reais sem integração segura.

Não fornece conselhos de investimento personalizados.

Não garante resultados financeiros, apenas auxilia no planejamento.
