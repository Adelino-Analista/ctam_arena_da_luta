# Screenshots & Checks — CTAM Arena

Este diretório contém um exemplo (`example.svg`) e orientações rápidas para **screenshots** e verificações visuais/accessibilidade usadas em PRs.

Recomendações de screenshots
- Tamanhos recomendados:
  - Desktop: **1440×900** (ex.: `modalidades-desktop.png`)
  - Mobile: **375×812** ou **375×667** (ex.: `modalidades-mobile.png`)
- Formatos: `png` ou `jpg` (PNG para imagens com texto/alta fidelidade). Comprimir imagens grandes antes de subir.
- Nomeie arquivos com contexto: `seção-view-port.png` (ex.: `modalidades-desktop.png`, `modalidades-mobile.png`).

Como capturar
- Abra `index` no navegador (ou use Live Server no VS Code) e use o modo de dispositivo no DevTools (Ctrl+Shift+M / Cmd+Shift+M) para mobile.
- Use uma ferramenta de captura (DevTools, macOS Screenshot, ou ferramentas de gravação) e salve no diretório local antes de arrastar para o PR.

Comandos úteis para verificações rápidas
- Rodar um servidor estático local (caso não use Live Server):

  npx http-server . -p 8080

- Executar Lighthouse (Acessibilidade) via CLI:

  npx lighthouse http://localhost:8080 --only-categories=accessibility --emulated-form-factor=mobile --output html --output-path=./lighthouse-report.html

- Verificação rápida via pa11y (opcional):

  npx pa11y http://localhost:8080

Ferramentas recomendadas
- Lighthouse (Chrome DevTools ou CLI) — https://developers.google.com/web/tools/lighthouse
- axe DevTools (extensão Chrome) — https://www.deque.com/axe/axe-for-web/
- WebAIM Contrast Checker — https://webaim.org/resources/contrastchecker/

Dica rápida
- Para contraste, verifique cores usadas em `:root` (ex.: `--yellow: #ffcc00` sobre `--black: #0a0a0a`). Confirme WCAG AA para texto normal antes de aceitar mudanças visuais.

Exemplo
- Use `.github/screenshots/example.svg` como referência de dimensão para desktop.

