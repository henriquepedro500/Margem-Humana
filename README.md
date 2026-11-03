# Margem Humana
## Quem pode discordar da IA no primeiro emprego?

### Visão Geral e Preview

Site sobre autonomia, empatia e aprendizagem de jovens atendentes diante de sugestões de IA e metas de velocidade. O visitante analisa quatro situações fictícias e exporta um protocolo de revisão. Os gráficos distinguem evidências de produtividade de expectativas geracionais.

[Preview real do site Margem Humana][(assets/img/preview.png)](https://henriquepedro500.github.io/Margem-Humana/)


### Integrantes, repositório e site publicado

| Campo | Informação |
|---|---|
| Estudante 1 | Pedro Henrique Teixeira De Lima — @henriquepedro500 |
| Estudante 2 | João Pedro De Souza — @joaoopedro2007 |
| Repositório público | https://github.com/henriquepedro500/Margem-Humana |
| GitHub Pages | https://henriquepedro500.github.io/Margem-Humana/ |


**Transparência sobre IA e autoria:** a implementação fornecida nesta versão foi produzida e revisada com assistência de IA, inclusive HTML e CSS. Caso o enunciado exija autoria manual nessas etapas, ainda é indispensável o trabalho efetivo e documentado dos integrantes. As três fichas do [AUDITORIA_IA.md](AUDITORIA_IA.md) distinguem especificações reconstruídas de mensagens literalmente enviadas. Não são atribuídas revisões, commits ou testes manuais aos estudantes sem evidência.

### Abrir e executar

Extrair o ZIP inteiro e abrir `index.html` no navegador. Nenhuma instalação é necessária. Bootstrap, Chart.js e fontes têm cópias locais; a aplicação funciona sem internet depois de extraída. Os links de pesquisa e as tentativas de carregar CDNs precisam de rede.

Para editar: modificar HTML/CSS diretamente. Ao alterar arquivos JS modulares, executar `node build.mjs`; o HTML usa `js/app.bundle.js` para permitir abertura por file://. Servidor local opcional: `python -m http.server 8000`.

### Estrutura de Arquivos e Diretórios

| Caminho | Função |
|---|---|
| index.html | Estrutura semântica, conteúdo, navegação e Bootstrap |
| css/styles.css | Design system, Grid/Flexbox, responsividade e acessibilidade |
| css/advanced.css | Keyframes e efeito glass opcional |
| css/fonts.css | Fontes locais para contingência |
| js/app.js | Integração, menu e controles alternativos |
| js/dom.js | Criação de texto e controle de foco |
| js/scenarios.js | Quatro cenários, cálculo e protocolo |
| js/simulator.js | Estado, feedback, download e reinício |
| js/data.js | Indicadores e suas fontes |
| js/chart.js | Gráfico, seletor, tabela e tratamento de falhas |
| js/theme.js | Tema, preferência e estado acessível |
| js/app.bundle.js | Versão clássica distribuída; gerada por build.mjs |
| assets/img/ | Favicon e preview real |
| assets/vendor/ | Bootstrap/Chart.js locais e licenças |
| assets/fonts/ | Fontes locais e licenças |
| auditoria/v1/ | Versões iniciais preservadas de três módulos |
| docs/ | Pesquisa, arquitetura, entrega, checklist de 9 critérios, registro da dupla e levantamento de falhas |
| tests/ | Testes de lógica e de DOM |
| AUDITORIA_IA.md | Três rodadas técnicas com origem e limites explícitos |
| VALIDACAO.md | Evidências dos testes realizados |
| LICENSE, .gitignore, .nojekyll | Licença MIT, exclusões Git e publicação estática |

### Arquitetura de Software e Contratos de Dados

Frontend estático, sem backend, frameworks de aplicação ou API de IA. Bootstrap 5 fornece componentes básicos; JavaScript Vanilla controla os recursos avançados. Não há chaves secretas, cadastro ou envio das escolhas a servidor.

O app monta três pontos: `theme-toggle`, `simulator-root`, `chart-root`. O menu e o accordion usam Bootstrap; se seu JS faltar, controles mínimos locais preservam a navegação. O gráfico destrói a instância anterior ao trocar indicador/tema; a tabela continua disponível se não houver canvas funcional.

| Contrato | Esquema |
|---|---|
| Scenario | `{id, title, context, suggestion, options: Option[3]}` |
| Option | `{id, label, points: 0\|1\|2, feedback, action}` |
| Answers | Array de quatro IDs válidos, na ordem dos cenários |
| Result | `{points: integer, maximum: 8, title, actions: string[4], notice}` |
| Dataset | `{title, unit, labels: string[], values: number[], population, source, url, note}` |
| Tema | `light` ou `dark`, chave `margem-humana-theme` no localStorage |

`evaluate` rejeita entradas inválidas e soma quatro decisões. A pontuação é didática, sem interpretação clínica. `buildProtocol` produz texto UTF-8. `getDataset` valida a chave e devolve cópia isolada. As chaves de dataset são produtividade, proposito e impacto. Labels e values têm o mesmo comprimento; todos os dados indicam fonte, população e unidade.

Só o tema é persistido. Escolhas ficam em memória e são apagadas ao recarregar/reiniciar. Texto dinâmico usa textContent. O download usa Blob local e revoga sua URL. O estado acessível e o foco acompanham a interação. A análise do simulador é O(n) no número de cenários, com três opções por cenário.

### Declaração de Dependências e CDN

| Dependência | Versão | Uso |
|---|---|---|
| Bootstrap | 5.3.8 | Grid, navbar, cards, accordion, badges; sem jQuery |
| Chart.js | 4.4.8 UMD | Barras interativas, tooltip e atualização |
| Google Fonts | Manrope e DM Sans, pesos declarados no HTML | Tipografia; cópias WOFF2 locais |
| Node.js | 20+ | Somente desenvolvimento/testes |
| jsdom | 26.0.0, devDependency | Testes de DOM; não é navegador visual |
| css-tree | 3.1.0, devDependency | Validação sintática de CSS |

CDNs: `https://cdn.jsdelivr.net/npm/bootstrap@5.3.8/dist/css/bootstrap.min.css`, `https://cdn.jsdelivr.net/npm/bootstrap@5.3.8/dist/js/bootstrap.bundle.min.js`, `https://cdn.jsdelivr.net/npm/chart.js@4.4.8/dist/chart.umd.min.js` e `https://fonts.googleapis.com/`.

Bootstrap usa SRI específico da versão. A cópia local de CSS antecede a CDN; os fallbacks JS só executam a biblioteca se ela ainda não existir, evitando registros duplicados. As fontes locais têm font-display: swap. Dependências de navegador ficam em assets e mantêm suas licenças.

Compatibilidade pretendida: Chrome, Firefox, Safari e Edge modernos. Há tratamento de localStorage indisponível, redução de movimento e falha do gráfico. Consultar VALIDACAO.md para os ambientes efetivamente testados; não confundir intenção de compatibilidade com testes completos em todos os navegadores.

### Matriz de Rastreabilidade e Colaboração

| Requisito | Implementação | Contribuição verificável da dupla |
|---|---|---|
| Recorte e fontes | docs/PESQUISA.md; QJE e Deloitte | Revisão humana pendente |
| HTML/Bootstrap | index.html | Gerado por IA; não atribuir autoria manual |
| Design/responsividade | styles.css | Gerado por IA; revisão humana pendente |
| Simulador | scenarios.js e simulator.js | Registrar autor/revisor e commit real |
| Dados/gráfico | data.js e chart.js | Registrar conferência das fontes |
| Tema/acessibilidade | theme.js, styles.css | Registrar teste manual e intervenções |
| Auditoria | AUDITORIA_IA.md e auditoria/v1/ | Registro técnico de IA; completar atuação real |
| Publicação | docs/ENTREGA.md | Conta GitHub e deploy pendentes |


### Referências

Referências completas e limites: [docs/PESQUISA.md](docs/PESQUISA.md).

- Brynjolfsson, Li e Raymond (2025), *Generative AI at Work*: https://doi.org/10.1093/qje/qjae044
- Deloitte (2025): https://www.deloitte.com/global/en/about/press-room/deloitte-2025-gen-z-and-millennial-survey.html
- Bootstrap: https://getbootstrap.com/docs/5.3/getting-started/introduction/
- Chart.js: https://www.chartjs.org/docs/latest/getting-started/integration.html
- GitHub Pages: https://docs.github.com/en/pages/getting-started-with-github-pages/configuring-a-publishing-source-for-your-github-pages-site

### Testes e licença

`npm test`: lógica sem dependências externas. `npm install` e `npm run test:ui`: DOM e CSS. `npm run build`: atualizar bundle. O README e a captura não substituem testes no endereço publicado.

Código do projeto sob MIT. Bootstrap e Chart.js mantêm suas licenças; fontes mantêm a SIL Open Font License. Estudos e documentos externos permanecem sob seus próprios termos.
