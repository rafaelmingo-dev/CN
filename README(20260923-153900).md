# Radar Connors RSI — Streamlit

Painel Streamlit para monitorar Connors RSI 3/2/100 em ativos da B3.

## Arquivos do repositório

```text
app.py
requirements.txt
.streamlit/
  config.toml
```

## Ativos monitorados

VIVT3, TUPY3, ITUB4, EGIE3, TAEE11, VALE3, CMIG4, EQTL3, IRBR3, BRSR6,
BBSE3, BBDC4, BPAC11, ITSA4, LEVE3, B3SA3, GGBR4, GOAU4, PSSA3, RANI3,
BBAS3, CPLE3, CXSE3, ABEV3, PRIO3, CPFE3, GOLD11, PETR4, WEGE3, CSMG3,
SBSP3, RADL3, BRAP4, UNIP6, KEPL3, PNVL3, SANB11, INBR32, CSAN3 e MRVE3.

## Lógica preservada

- Connors RSI = RSI do preço (3) + RSI da streak (2) + PercentRank (100), dividido por 3.
- Níveis monitorados: 20 e 80.
- Tabelas principais usam CRSI confirmado.
- Snapshots: 30, 90 e 180 dias corridos, usando o último pregão disponível em ou antes da data-alvo.
- Percentil CRSI 1A continua usando janela de um ano.
- CRSI atual/intraday e Status candle continuam calculados internamente para auditoria.

## Publicar no Streamlit Community Cloud

1. Crie um repositório no GitHub.
2. Envie `app.py`, `requirements.txt` e a pasta `.streamlit`.
3. No Streamlit Community Cloud, clique em **Create app**.
4. Selecione o repositório e informe `app.py` como arquivo principal.
5. Faça o deploy.

Não são necessários secrets para esta versão.

## Atualização

O painel usa cache de 15 minutos. O botão **Atualizar** limpa o cache e força nova coleta.

## Observação

Os dados são obtidos via `yfinance`/Yahoo Finance. O painel é uma ferramenta de análise e não constitui recomendação de investimento.
