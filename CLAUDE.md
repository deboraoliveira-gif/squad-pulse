# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Visão geral

Portal estático de relatórios da Squad Lyra (CI&T / Hub de Pagamentos Vivo). Não há build pipeline, framework ou servidor — apenas HTML, CSS e JavaScript vanilla publicados diretamente no GitHub.

## Como rodar localmente

```bash
# Qualquer servidor HTTP local funciona:
python -m http.server 8000
# Depois abrir http://localhost:8000
```

Não há `npm install`, compilação ou variáveis de ambiente.

## Estrutura das páginas

| Arquivo | Propósito |
|---|---|
| `index.html` | Hub de navegação — links para worklogs e indicadores |
| `sprints/worklog_lyra_pi<N>_it<N>.html` | Worklog de sprint: horas lançadas por dev, métricas de capacidade |
| `indicadores/indicadores-hub.html` | Dashboard de KPIs: BCPs, horas, qualidade (bugs) por squad |

## Convenções importantes

**Dados são hardcoded.** Todos os valores (horas, BCPs, bugs) estão em objetos JavaScript dentro do próprio HTML. Não há integração com API em produção — o footer menciona integração futura com Tempo API + Jira API.

**Nomes de arquivos de sprint:** `worklog_lyra_pi<número_PI>_it<número_iteração>.html` — ex: `worklog_lyra_pi2_it4.html`.

**Tema visual:** Dark mode com variáveis CSS customizadas. Worklogs usam tema Copa 2026 (verde/dourado/azul). Indicadores usam Tailwind CSS 4 via CDN + Chart.js 4.4.0 via CDN. Index usa tema Lyra/constelação (roxo Vivo + laranja CI&T).

**Squads no dashboard de indicadores:**
- `VHPE` — Cartão de Crédito
- `VHPF` — Centaurus
- `VHPH` — Pix Auto (Squad Lyra)
- `VHPK` — Reforma Tributária

## Ao criar um novo worklog de sprint

1. Copiar o worklog mais recente em `sprints/` como base.
2. Renomear com o número correto de PI e iteração.
3. Atualizar: período, dados de horas por dev, totais e o link no `index.html`.
4. O tema Copa 2026 é reutilizado entre sprints — manter a identidade visual.

## Ao atualizar o dashboard de indicadores

Os dados ficam em um objeto JavaScript (ex: `dadosMensais`) dentro do `<script>` da página. Para adicionar um mês novo: inserir a chave com os dados de cada squad e atualizar o seletor de datas no HTML.
