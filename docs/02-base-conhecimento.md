# Base de Conhecimento

## Dados Utilizados

Descreva se usou os arquivos da pasta `data`, por exemplo:

| Arquivo | Formato | Utilização no Agente |
|---------|---------|---------------------|
| `transacoes_atendimento.csv` | CSV | Analisar padrão de gastos do cliente (categorias, frequência, valores)|
| `perfil_cliente.json` | JSON | Guardar informações de perfil (nome, renda, metas financeiras) |
| `alertas.json` | JSON |Configurar limites de gastos e alertas personalizados |
| `historico_relatorios.csv` | CSV | Registrar relatórios semanais/mensais para acompanhamento |


## Fontes internas
Documentação própria do projeto.
FAQs e relatórios de uso do agente.
Exemplos de interações simuladas para reforçar o tom consultivo.


## Fontes externas

### Datasets Hugging Face
- **TableQAKit/FinQA_retrieval**  
  [Link](https://huggingface.co/datasets/TableQAKit/FinQA_retrieval)  
  *Objetivo:* Treinar o agente para responder perguntas sobre relatórios e tabelas financeiras.

- **Banking77**  
  [Link](https://huggingface.co/datasets/PolyAI/banking77)  
  *Objetivo:* Reconhecer intenções comuns de usuários em contexto bancário (saldo, transferências, abertura de conta).

- **DailyDialog**  
  [Link](https://huggingface.co/datasets/li2017dailydialog)  
  *Objetivo:* Dar naturalidade e empatia às respostas do agente, reforçando o tom consultivo e amigável.

> [!TIP]
> **Quer um dataset mais robusto?** Você pode utilizar datasets públicos do [Hugging Face](https://huggingface.co/datasets) relacionados a finanças, desde que sejam adequados ao contexto do desafio.

---

## Adaptações nos Dados

> Você modificou ou expandiu os dados mockados? Descreva aqui.

Expansão dos dados mockados para incluir categorias de gastos (alimentação, transporte, lazer, saúde).

Inclusão de campos de metas financeiras (ex: poupar R$ 500/mês).

Normalização dos valores para facilitar cálculos estatísticos.

---

## Estratégia de Integração

### Como os dados são carregados?
Os arquivos JSON e CSV são carregados no início da sessão.

São transformados em dicionários/estruturas Python e incluídos no contexto do prompt.


### Como os dados são usados no prompt?
> Os dados vão no system prompt? São consultados dinamicamente?

Maior gasto: identifica a transação de maior valor.
Total de gastos: soma todos os valores registrados.
Média de gastos: calcula a média dos gastos registrados.
Gasto por categoria: calcula o total gasto em uma categoria específica.

Essas funções permitem que o agente responda dinamicamente às perguntas do usuário, evitando respostas fixas e tornando a interação mais útil.
---

## Exemplo de Contexto Montado

> Mostre um exemplo de como os dados são formatados para o agente.

```
Dados do Cliente:
- Nome: João Silva
- Perfil: Moderado
- Renda Mensal: R$ 5.000
- Meta: Poupar R$ 500/mês

Últimas transações:
- 01/11: Supermercado - R$ 450
- 03/11: Streaming - R$ 55
- 05/11: Transporte - R$ 120
- 07/11: Restaurante - R$ 200

Alertas:
- Gastos em lazer acima de R$ 800/mês → Notificação

...
```
