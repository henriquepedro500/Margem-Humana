# Validação técnica da versão completa

Data: 28 de outubro de 2026. Testes executados pelo assistente, não atribuídos à dupla.

## Testes automatizados

Node.js 24.22.1: **11 testes aprovados, zero falhas**.

- Quatro testes de domínio: 81 trajetórias, extremos da pontuação, entradas inválidas, integridade do dataset e armazenamento bloqueado.
- Sete testes de DOM/CSS: estrutura semântica, IDs, âncoras e arquivos locais, sintaxe CSS, fluxo completo, foco, progresso 4/4, reinício, tabela sem Chart.js, descarte de gráficos, tema e controles sem Bootstrap.
- Os testes DOM usam jsdom e substituem o canvas por uma instância de teste; não são evidência visual. A renderização real foi verificada separadamente.

## Navegador real

Chromium headless **133.0.6943.0**, execução via Playwright e abertura local por file://:

- Larguras 320, 375, 768, 1024 e 1440 px: sem transbordamento horizontal do documento.
- Navbar móvel e accordion operáveis.
- Fluxo completo dos quatro cenários, resultado 8/8, download `protocolo-margem-humana.txt` e reinício.
- Troca de indicador e presença dos valores correspondentes na tabela.
- Alternância de tema e gráfico em canvas.
- Abertura direta de index.html, sem servidor ou instalação pelo usuário.
- Zero exceções de JavaScript detectadas pelo evento pageerror.
- Capturas de desktop/celular revisadas. Preview do README capturado da interface real.

Os CDNs e Google Fonts não carregaram pela rede deste ambiente. As cópias locais incluídas carregaram Bootstrap, Chart.js e fontes, permitindo validar a aplicação em contingência. As falhas externas de rede não foram ocultadas como sucesso de CDN.

## Correções durante a verificação

- Ajuste da ordem das regras de grid sm/md/lg/xl para evitar cards indevidamente largos.
- Correção de quebra de título e tamanho mínimo de itens de Grid em telas de 320 px.
- Inclusão de dependências locais, preservando versões e licenças.
- Área de gráfico com altura controlada e tratamento de erro de construção.
- Barra de progresso no resultado e integração do botão de tema ao cabeçalho.

## Limites

Não foram realizados testes em Firefox, Safari, dispositivos físicos ou no GitHub Pages. Não foi feita auditoria humana integral de WCAG 2.1 AA, leitor de tela ou contraste de todos os estados. O endereço público deve ser validado depois da publicação. Compatibilidade pretendida não é comprovação de teste em todos os navegadores.

A primeira tentativa de instalar o navegador padrão falhou. Uma distribuição Chromium local permitiu executar posteriormente os testes acima. O registro anterior de “navegador indisponível” foi substituído por estes resultados reais.

## Reproduzir

`npm test`: domínio. `npm install` e `npm run test:ui`: DOM e CSS. Para uma nova verificação visual, abrir index.html em um navegador e percorrer a matriz em docs/ENTREGA.md. Após editar JS modular, executar `npm run build`.

## Reverificação de 28/10/2026 (após ajuste de semântica e CSS)

Executada pelo assistente, não atribuída à dupla.

- `html-validate` em index.html: zero erros (DOCTYPE, landmarks com nome único, `&` escapado, ordem de cabeçalhos).
- `npm test` (4) e `npm run test:ui` (7): todos aprovados.
- Chromium real via Playwright, abrindo index.html por file://, com e sem rede: zero `pageerror`; simulador percorrido nos 4 cenários (resultado 3/8 com as opções escolhidas no teste), download `protocolo-margem-humana.txt` e reinício; três indicadores do gráfico e alternância de tema sem erro; sem rolagem horizontal em 320, 375, 768, 1024 e 1440 px.
- No ambiente de teste não havia internet: as requisições aos CDNs falharam e foram atendidas pelas cópias locais. O carregamento real dos CDNs deve ser conferido pela dupla com internet, no F12 > Console.
- Continuam sem teste: Firefox, Safari, dispositivos físicos, leitor de tela e GitHub Pages.

## Rechecagem do pacote preparado para GitHub — 02/11/2026

Executada pelo assistente nesta versão, sem atribuir resultados aos estudantes:

- `npm test`: **4 testes de domínio aprovados**, zero falhas.
- `npm run build`: gerou `js/app.bundle.js` a partir dos módulos originais.
- `node --check js/app.bundle.js`: verificação de sintaxe aprovada.
- A suíte `tests/ui.test.cjs` foi complementada com um caso para erro de construção do Chart.js. **Este novo caso não foi executado** nesta rechecagem porque `jsdom` e `css-tree` não estão instalados neste ambiente. Para executar: `npm install` e `npm run test:ui` em um ambiente com acesso ao npm.
- Tentativas de abrir o arquivo via `file://` e o servidor local via `http://127.0.0.1` no Chromium deste ambiente foram bloqueadas com `net::ERR_BLOCKED_BY_ADMINISTRATOR`. O bloqueio é ambiental. **Método alternativo:** carregar o mesmo HTML e injetar os CSS e scripts locais no Chromium headless, em documento criado em memória (`set_content`), sem fazer navegação de URL. **Neste ambiente, este teste automatizado não verifica acesso ao site publicado, resposta HTTP, fontes externas nem carregamento dos CDNs.**
- Chromium headless via método alternativo: **0 exceções de JavaScript e 0 mensagens de Console do tipo `error`**; largura de 320, 375, 768, 1024 e 1440 px sem transbordamento horizontal; menu móvel expandiu e recolheu; accordion mudou e fechou o painel anterior; quatro decisões do simulador (8/8), download TXT, reinício; três indicadores e tabelas; tema claro/escuro. O canvas Chart.js foi renderizado com cópia local. Em cenário injetado de falha do construtor `Chart`, a interface manteve tabela, aviso e troca de indicador, sem exceção não tratada.
- Estes resultados representam **teste de comportamento no Chromium com arquivos incorporados**, não F12 aberto manualmente pelos estudantes nem comprovação do GitHub Pages ou da CDN externa.
- Documentação final ampliada: checklist com **nove critérios**, modelo de registro dos integrantes e campos de identificação e links reais no README.

**Ainda obrigatório pela dupla:** revisão humana, testes reais de responsividade e Console/Network no navegador, commits das duas contas, publicação e validação do link do GitHub Pages. Os resultados históricos anteriores não certificam a URL pública.
