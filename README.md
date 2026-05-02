# 📊 PayFlow — Credit Risk Dashboard

![HTML](https://img.shields.io/badge/HTML%20%2B%20CSS%20%2B%20JS-static-blue) ![Chart.js](https://img.shields.io/badge/Chart.js-4.4.1-brightgreen) ![No Server](https://img.shields.io/badge/no%20server-required-lightgrey)

Dashboard interativo de análise de risco de crédito construído como arquivo HTML estático. Explora uma carteira fictícia de 5.000 contratos da PayFlow, identificando padrões de inadimplência por produto, canal, perfil do tomador, score de crédito e região.

---

## Como Visualizar

### Opção 1 — GitHub Pages (recomendado)

```
Settings → Pages → Branch: main → Folder: / (root) → Save
```

Disponível em: `https://gabi-lopes.github.io/payflow-dashboard/`

### Opção 2 — Localmente

```bash
git clone https://github.com/gabi-lopes/payflow-dashboard
# Abra o index.html no navegador — nenhum servidor necessário
```

---

## Funcionalidades

- **7 abas temáticas** — Visão Geral, Análise de Default, Perfil do Tomador, Produtos & Canais, Score & Risco, Regiões, Insights & Alertas
- **KPI cards** com métricas-chave da carteira (taxa de default 12,18%, exposição R$9,9M, score médio 653)
- **12+ gráficos interativos** via Chart.js — barras, donuts, scatter plot, histogramas
- **Heatmap** de risco cruzando produto × canal de aquisição
- **Ranking de preditores** de default com barras visuais
- **Tabelas de segmentação** com badges de risco por região, produto e canal
- **Recomendações estratégicas** priorizadas por impacto estimado

---

## Principais Achados

| Segmento | Taxa de Default | Risco |
|---|---|---|
| BNPL | 15,76% | 🔴 Alto |
| Canal Parceiro | 14,42% | 🔴 Alto |
| Renda < R$2k | 18,64% | 🔴 Alto |
| Atraso > 61 dias | 48,34% | 🔴 Crítico |
| Canal App | 11,47% | 🟢 Baixo |
| Score > 750 | 9,29% | 🟢 Baixo |
| Centro-Oeste | 10,47% | 🟢 Baixo |

- Taxa de default geral de **12,18%** — acima do benchmark de mercado (8–10%)
- **R$9,9M** em exposição a risco (17,5% da carteira total de R$56,4M)
- Contratos com atraso > 61 dias têm **48% de chance** de virar default

---

## Estrutura dos Dados

Base sintética `payflow_credit_risk.xlsx` com 5.000 contratos. Principais variáveis:

| Variável | Descrição |
|---|---|
| `score_credito` | Score de crédito (300–900) |
| `valor_solicitado` | Valor do contrato em R$ |
| `renda_mensal` | Renda mensal do tomador |
| `default_90d` | Flag de inadimplência acima de 90 dias |
| `dias_atraso_max_12m` | Máximo de dias em atraso nos últimos 12 meses |
| `inadimplencias_anteriores` | Histórico de inadimplências |
| `produto` | Empréstimo Pessoal, Cartão, BNPL |
| `canal` | App, Site, Loja, Parceiro |
| `regiao` | Norte, Nordeste, Sudeste, Sul, Centro-Oeste |

---

## Tecnologias

- HTML5 + CSS3 (dark mode, variáveis CSS, grid, flexbox)
- [Chart.js 4.4.1](https://www.chartjs.org/) via CDN
- JavaScript puro (sem frameworks)

---

*PosTech AI Scientist · Fase 1 · Análise Exploratória de Dados*
