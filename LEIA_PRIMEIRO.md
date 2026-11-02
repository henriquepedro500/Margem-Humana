# Margem Humana — versão completa

## Abrir o site

1. Extraia o ZIP inteiro para uma pasta.
2. Abra a pasta `margem-humana`.
3. Dê dois cliques em `index.html`.

Não é necessário instalar Node, VS Code ou executar comandos para abrir o site. Mantenha as pastas css, js e assets junto do HTML. As fontes, Bootstrap e Chart.js têm cópias locais para contingência. O site funciona sem internet depois de extraído; links para as pesquisas exigem conexão.

## O que foi concluído

- HTML5 semântico, descrição para mecanismos de busca e navegação por âncoras.
- Layout responsivo, design system com variáveis, Grid/Flexbox e estados de foco.
- Bootstrap 5: navbar colapsável, cards, badges e accordion.
- Simulador com quatro casos fictícios, feedback, progresso, resultado e download TXT.
- Gráfico interativo, três indicadores, fontes e tabela alternativa.
- Tema claro/escuro, preferência persistida quando disponível e redução de movimento.
- Pesquisa, README, registro técnico de IA, testes e instruções de publicação.

## Antes da entrega acadêmica

O site foi gerado e revisado com IA a seu pedido, inclusive o HTML/CSS. O enunciado original reserva essa camada ao trabalho manual sem IA. Portanto, esta versão completa não deve ser declarada como código escrito manualmente pela dupla. O registro técnico identifica o que foi produzido pelo assistente; a revisão humana e a participação dos dois integrantes precisam ser reais.

Ainda dependem de vocês: preencher os dois nomes, revisar o projeto com intervenções próprias, testar no navegador/F12, registrar contribuições verdadeiras, criar o repositório e publicar e validar o GitHub Pages. Consulte `docs/CHECKLIST.md` e `docs/REGISTRO_DA_DUPLA.md`. A conta GitHub não foi conectada nesta conversa e nenhum deploy foi realizado.

## Publicação

Siga `docs/ENTREGA.md`. Envie o **conteúdo** desta pasta para a raiz do repositório, de modo que `index.html` apareça diretamente na raiz. Atualize o link real no README depois de publicar.

## Edição e testes

- Layout: `index.html` e `css/styles.css`.
- Textos/casos: `js/scenarios.js`; dados e fontes: `js/data.js`.
- Depois de mudar módulos JS: executar `node build.mjs` para atualizar `js/app.bundle.js`.
- Lógica: `npm test` (Node 20+).
- Interface em DOM simulado: `npm install` e `npm run test:ui`.
- Limites e resultados reais dos testes: `VALIDACAO.md`.
