# Instruções rápidas para agentes AI — CTAM Arena (site estático)

Resumo rápido
- Projeto: site estático de uma página (`index`). HTML + CSS inline; **sem** build tools, sem JS. Tudo que afeta o site principal fica em `index`.

Principais padrões e onde editar
- Arquivo principal: `index` (HTML). Editar diretamente para conteúdo, layout e estilos.
- Estrutura de seções: `nav`, `header#home`, `section#modalidades`, `footer#contato`.

Como adicionar/alterar uma modalidade (exemplo reutilizável)
- Local: dentro de `.grid-modalidades` insira um novo `.card` com o mesmo padrão:

```html
<div class="card">
  <h3>🥋 NOME DA MODALIDADE</h3>
  <p>Uma descrição curta, 1-2 frases.</p>
  <div class="horarios">
    • Dia/horário<br>
    • Observação (professor, passe livre)
  </div>
</div>
```
- Observações: mantenha emojis nos títulos para consistência visual e use a classe `.horarios` para o bloco amarelo.

Estilo e padrões CSS observáveis
- Cores principais em `:root`: `--yellow`, `--black`, `--dark-gray`, `--light-gray`, `--white` — use essas variáveis se estiver adicionando regras.
- Tipografia: fonte visual principal é `Impact`/`Arial Black`, textos do corpo em `Arial` (definido globalmente no `*`).
- Layout responsivo: `.grid-modalidades` usa `grid` com `auto-fit minmax(320px, 1fr)`; breakpoint existente em `@media (max-width: 768px)` que esconde o `nav ul` e ajusta `hero h1`.

Recursos externos
- Font Awesome via CDN (link no `<head>`).
- Imagem de fundo do `header` é um URL do Unsplash (inline na regra `header { background: ... }`).

Acessibilidade e boas práticas específicas daqui
- O HTML já usa `lang="pt-br"`. Se adicionar imagens `<img>`, inclua `alt` descritivo.
- Se converter o background de `header` para `<img>` por motivos de SEO/acessibilidade, garanta `alt` e role="img" e inclua texto descritivo; mantenha o contraste do texto sobre a imagem.

Testes & visualização
- Não há build ou testes automatizados: para ver alterações, abra `index` diretamente no navegador ou use uma extensão "Live Server" no VS Code para recarregar rápido.
- Instale dependências antes de executar scripts locais: `npm install` ou `npm ci`.
- Scripts úteis: `npm run start` (servidor estático local), `npm run audit:pa11y-ci`, `npm run audit:lighthouse`, ou `npm run audit:accessibility` para rodar as verificações localmente.
- Veja também `.github/screenshots/README.md` para exemplos de tamanhos de screenshot, convenções de nome de arquivo e comandos úteis (Lighthouse, axe, WebAIM).

Automação (CI)
- Há um GitHub Action em `.github/workflows/accessibility.yml` que roda **pa11y-ci** e gera um relatório do **Lighthouse** em PRs. Falhas em pa11y-ci bloqueiam o job; o relatório Lighthouse é enviado como artifact para análise posterior.
- Arquivo de configuração pa11y: `.pa11yci`. Para rodar localmente use `npm run audit:pa11y-ci`.

Commit, PR e deploy
- Não há pipeline/CI detectada. Use o fluxo git padrão (branch por mudança, PR com descrição curta).
- Use o modelo de PR em `.github/PULL_REQUEST_TEMPLATE.md` para facilitar a revisão: marque o tipo (`conteúdo` / `layout` / `docs`) e siga o checklist (screenshots para mudanças visuais, preview em mobile, verificação de `alt`, etc.).
- Para issues de bug ou solicitações de mudança, use os templates em `.github/ISSUE_TEMPLATE/` (bug_report.md, feature_request.md) para descrever passo-a-passo, incluir screenshots e indicar o impacto.
- Para alterações de conteúdo (texto, horários), prefira PRs pequenos que mostrem diffs claros.
- Para mudanças de layout, inclua screenshots no PR e descreva o motivo da alteração.
- Veja também `CONTRIBUTING.md` para regras de revisão, preview e confirmação de dados de contato.

Boas práticas específicas do projeto
- Preserve as variáveis `:root` (`--yellow`, etc.) quando adicionar regras de cor.
- Mantenha o padrão de títulos com emojis (ex.: `h3` das modalidades) para consistência visual.
- Links externos (ex.: redes sociais) podem ser `#` placeholders — confirme URLs reais com o mantenedor antes de publicar.

Perguntas que agentes devem fazer quando em dúvida
- Confirmar tom/voz do texto (ex.: formal vs. coloquial).
- Confirmar horário/professor/telefone antes de alterar contato.
- Perguntar se preferem manter estilos inline ou mover para um arquivo CSS separado.

Resumo curto
- Projeto: uma página estática. Editar `index` é o caminho principal. Seja conservador em mudanças de layout; quando incerto, solicite confirmação do mantenedor.