# Squad Pulse

Portal de acompanhamento da **Squad Lyra** — Hub de Pagamentos Vivo (CI&T).

Reúne em um único lugar os worklogs de sprint e o painel de indicadores de desempenho do time.

---

## Páginas

| Página | Descrição |
|---|---|
| **Hub** (`index.html`) | Navegação central com links para todos os relatórios |
| **Worklog de sprint** (`sprints/`) | Horas lançadas por desenvolvedor, capacidade e métricas de cada iteração |
| **Indicadores** (`indicadores/indicadores-hub.html`) | Dashboard de KPIs por squad: BCPs, horas, qualidade e rework |

---

## Como visualizar

Abra qualquer `.html` diretamente no navegador, ou sirva localmente:

```bash
python -m http.server 8000
```

Não há dependências para instalar nem build para executar.

---

## Estrutura

```
index.html                          # Hub de navegação
indicadores/
  └── indicadores-hub.html          # Dashboard de KPIs (Chart.js + Tailwind)
sprints/
  ├── worklog_lyra_pi1_it6.html     # PI 1 — Iteração 6 (encerrada)
  └── worklog_lyra_pi2_it4.html     # PI 2 — Iteração 4 (atual)
```

---

## Squads monitoradas

| Squad | Sistema |
|---|---|
| VHPE | Cartão de Crédito |
| VHPF | Centaurus |
| VHPH | Pix Auto *(Squad Lyra)* |
| VHPK | Reforma Tributária |

---

Projeto interno · CI&T × Vivo · Hub de Pagamentos
