# Contribuindo — CTAM Arena

Obrigado por contribuir! Algumas orientações rápidas para tornar revisões fáceis e rápidas.

- Este é um site de **uma página**: tudo está em `index` (HTML) com CSS inline.
- Para conteúdo (horários, textos): crie PRs pequenos e focados; mantenha emojis nos títulos (`h3`) para consistência.
- Para adicionar/alterar uma modalidade: copie o padrão dentro de `.grid-modalidades` (veja `.card` no `index`).
- Para mudanças visuais: inclua screenshots (desktop + mobile) e descreva o motivo da alteração.
- Preferência: não mover o CSS inline para arquivos separados sem antes abrir uma issue e alinhar com o mantenedor.
- Preview: abra `index` no navegador ou use a extensão Live Server no VS Code.
- Antes de rodar scripts locais (ex.: `npm run audit:accessibility`), execute `npm install` ou `npm ci` para instalar dependências de desenvolvimento.
- Verificações rápidas: responsividade no breakpoint 768px, `alt` em imagens, manter variáveis `:root`.
- Para mudanças de dados de contato (telefone, endereço, redes): confirme com o mantenedor antes do merge.
- Para mudanças grandes de layout/estrutura: abra uma issue antes de implementar.

Acessibilidade — verificação rápida
- Verifique contraste de cores (WCAG AA para texto normal) com Lighthouse, axe ou um verificador de contraste.
- Garanta `alt` descritivo para imagens e mantenha contraste do texto sobre backgrounds.
- Verifique navegação por teclado (foco visível em links e botões).
- Para mudanças visuais, inclua screenshots desktop (~1440px) e mobile (~375px) e mencione verificações de contraste/foco no PR.

Se tiver dúvidas, abra uma issue com descrição e screenshots — o mantenedor responderá com orientações.