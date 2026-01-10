# CTAM Arena — Site estático

[![Accessibility checks](https://github.com/antonioadelino/ctam-site/actions/workflows/accessibility.yml/badge.svg)](https://github.com/antonioadelino/ctam-site/actions/workflows/accessibility.yml)

Pequeno site de uma página usado para apresentar modalidades e contato da CTAM Arena.

Como rodar localmente
1. Instale dependências (recomendado):

   npm install

2. Inicie um servidor estático para visualizar `index`:

   npm run start

Scripts úteis
- `npm run start` — servidor estático local (http://localhost:8080)
- `npm run audit:pa11y-ci` — executa `pa11y-ci` com `.pa11yci` (falha o processo em caso de problemas)
- `npm run audit:lighthouse` — gera um relatório Lighthouse (acessibilidade)
- `npm run audit:accessibility` — executa `pa11y-ci` + Lighthouse (usa servidor local temporário)
- `npm test` — atalho que executa `npm run audit:accessibility` (útil para integrações / scripts padrão)

CI
- O repositório tem um workflow em `.github/workflows/accessibility.yml` que roda `pa11y-ci` em PRs e anexa um relatório Lighthouse como artifact.

Observações
- Este projeto não usa build tools; tudo está em `index` (HTML) com CSS inline.
- Antes de rodar scripts de auditoria localmente, execute `npm install` para instalar as dependências necessárias.