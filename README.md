# Panorama do Mercado de Criptomoedas (CoinGecko API)

Projeto de coleta de dados da disciplina Introdução à Ciência de Dados (Pós-graduação em Ciência de Dados, IFSP), Aula 4.2 - Processamento e Coleta de Dados.

**Autor:** Rafael da Silva Oliveira (CP3044564)

**Repositório:** https://github.com/Rafa516/coleta-dados-criptomoedas-coingecko

## Objetivo

Construir um dataset estruturado com as 100 maiores criptomoedas por capitalização de mercado, coletado por API REST pública, e realizar as etapas de limpeza, processamento, análise exploratória e documentação. O propósito analítico é caracterizar a concentração de mercado, a liquidez e a volatilidade de curto prazo (24 horas) desse conjunto de ativos.

## Fonte de dados

CoinGecko API v3, endpoint `/coins/markets` (https://api.coingecko.com/api/v3/coins/markets), utilizado sem chave de acesso. Documentação: https://docs.coingecko.com/v3.0.1/reference/coins-markets.

## Conteúdo do repositório

| Arquivo | Descrição |
|---------|-----------|
| `Exercicios_Aula4.ipynb` | Notebook com todo o código executável e a documentação do projeto, estruturada conforme o template da disciplina |
| `Template_Documentacao.ipynb` | Template de documentação fornecido com a atividade |
| `criptomoedas_bruto.json` | Resposta original da API, preservada antes da limpeza |
| `criptomoedas_dataset.csv` | Dataset final (100 registros, 15 colunas) |
| `documentacao.md` | Documentação em Markdown gerada pelo notebook |
| `grafico_top10_capitalizacao.png`, `grafico_capitalizacao_volume.png`, `grafico_variacao_24h.png` | Visualizações geradas na análise exploratória |
| `lista_projetos_sugeridos.csv` | Lista de temas sugeridos na atividade |

## Instalação e uso

Requer Python 3 e as bibliotecas listadas em `requirements.txt`.

```bash
pip install -r requirements.txt
jupyter notebook Exercicios_Aula4.ipynb
```

A execução do notebook refaz a coleta e sobrescreve os arquivos gerados. Como a API retorna o estado atual do mercado, os valores numéricos variam a cada execução.

## Principais resultados (coleta de 08/11/2026)

- O Bitcoin responde por 59,5% da capitalização total das 100 moedas coletadas (US$ 2,542 trilhões); as 10 maiores somam 91,0%.
- Capitalização e volume negociado apresentam correlação de Pearson de 0,669 em escala logarítmica (95 moedas com volume positivo).
- Em 76 das 100 moedas a variação em 24 horas foi negativa (mediana de -2,02%).
- 62 das 100 moedas estão mais de 50% abaixo da máxima histórica.

A análise é descritiva, refere-se a um único instantâneo de mercado e não constitui recomendação de investimento. Limitações e próximos passos estão descritos nas seções 7 e 8 do notebook.
