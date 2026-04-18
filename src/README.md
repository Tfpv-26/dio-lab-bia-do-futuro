# Código da Aplicação
  
Já criei a pasta meu_agente_financeiro com o arquivo principal app.py.
O ambiente virtual (venv) está configurado e as dependências foram instaladas com pip install streamlit pandas.
Para rodar a aplicação, basta entrar na pasta do projeto, ativar o ambiente virtual e executar: streamlit run app.py

## Estrutura Sugerida

```
src/
├── app.py              # Aplicação principal (Streamlit)
├── agente.py           # (opcional) lógica do agente
├── config.py           # (opcional) configurações
└── requirements.txt    # Dependências
```

## Exemplo de requirements.txt

```
streamlit
pandas

```

## Como Rodar

```
pip install -r requirements.txt
streamlit run app.py
```
