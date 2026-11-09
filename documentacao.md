# Documentação do Projeto

- **Tema:** Panorama do mercado de criptomoedas (CoinGecko API)
- **Autor:** Rafael da Silva Oliveira (CP3044564)
- **Data da coleta:** 08/11/2026 20:40:05
- **Fonte / URL:** https://api.coingecko.com/api/v3/coins/markets (parâmetros: vs_currency=usd, order=market_cap_desc, per_page=100, page=1)
- **Documentação da fonte:** https://docs.coingecko.com/v3.0.1/reference/coins-markets

## Propósito
Caracterizar a concentração de mercado, a liquidez e a volatilidade de curto prazo (24 h) das 100 maiores criptomoedas por capitalização.

## Dicionário de dados
| Coluna | Tipo | Descrição |
|--------|------|-----------|
| `nome` | object | Nome da criptomoeda |
| `simbolo` | object | Símbolo (ticker) em maiúsculas |
| `ranking_capitalizacao` | int64 | Posição pela capitalização de mercado (1 = maior) |
| `preco_usd` | float64 | Preço atual em dólares norte-americanos (USD) |
| `variacao_24h_pct` | float64 | Variação percentual do preço nas últimas 24 horas |
| `capitalizacao_usd` | int64 | Capitalização de mercado em USD (preço x oferta circulante) |
| `volume_24h_usd` | float64 | Volume total negociado nas últimas 24 horas em USD |
| `oferta_circulante` | float64 | Quantidade de unidades em circulação |
| `maxima_historica_usd` | float64 | Maior preço já registrado (ATH) em USD |
| `distancia_maxima_pct` | float64 | Variação percentual do preço atual em relação ao ATH |
| `atualizado_em` | datetime64[ns] | Data e hora (UTC) da última atualização do registro na API |
| `giro_volume_capitalizacao` | float64 | Derivada: volume em 24 h dividido pela capitalização |
| `participacao_mercado_pct` | float64 | Derivada: participação na capitalização total do conjunto (%) |
| `sentido_24h` | object | Derivada: Alta (variação >= 0) ou Queda (variação < 0) |
| `faixa_ranking` | object | Derivada: Top 10, 11 a 50 ou 51 a 100 |

## Estatísticas gerais
- Registros: 100 | Colunas: 15
- Capitalização total do conjunto: US$ 2.542 trilhões
- Participação de Bitcoin: 59.5% | 10 maiores: 91.0%
- Variação mediana em 24 h: -2.02%

```
                   count              mean                std            min            25%              50%              75%                  max
preco_usd         100.00            893.15           7,529.74           0.00           0.32             1.00             6.87            75,185.00
variacao_24h_pct  100.00             -1.91               2.19         -11.24          -3.12            -2.02            -0.00                 3.23
capitalizacao_usd 100.00 25,423,024,952.10 153,921,387,172.92 515,084,771.00 929,804,206.50 1,775,203,923.00 3,710,397,766.50 1,511,942,918,879.00
volume_24h_usd    100.00    707,364,714.39   3,399,602,363.63           0.00   7,809,812.75    35,938,780.50   125,906,262.50    28,757,554,957.00
```

## Insights
Ver a seção 6 do notebook Exercicios_Aula4.ipynb.
