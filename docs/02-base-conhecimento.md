# Base de Conhecimento

## Dados Utilizados

Descreva se usou os arquivos da pasta `data`, por exemplo:

| Arquivo | Formato | Utilização no Agente |
|---------|---------|---------------------|
| `transacoes_atendimento.csv` | CSV | Analisar padrão de gastos do cliente (categorias, frequência, valores)|
| `perfil_cliente.json` | JSON | Guardar informações de perfil (nome, renda, metas financeiras) |
| `alertas.json` | JSON |Configurar limites de gastos e alertas personalizados |
| `historico_relatorios.csv` | CSV | Registrar relatórios semanais/mensais para acompanhamento |

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

O agente consulta dinamicamente os dados conforme a interação.

Informações relevantes (últimas transações, saldo, metas) são inseridas no system prompt para contextualizar a resposta.

Relatórios e alertas são gerados com base nesses dados, evitando alucinações.

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
