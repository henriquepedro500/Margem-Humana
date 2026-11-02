# Publicar e entregar

O site local está implementado. Não foi publicado, pois não houve conexão com uma conta GitHub. Os passos abaixo são executados na conta da dupla.

## 1. Preparar a identificação

Preencher os nomes completos, os perfis GitHub e os campos de links no README. Completar `docs/REGISTRO_DA_DUPLA.md` com evidências reais. Se desejarem exibir os nomes no site, editar o rodapé. Revisar o conteúdo e o registro de IA. O material foi gerado com IA, inclusive a Parte I; não descrevê-lo como autoria manual.

## 2. Criar o repositório

No GitHub, usar New repository, nome `margem-humana`, visibilidade Public. Adicionar o outro integrante em Settings > Collaborators. Cada pessoa deve usar sua própria identidade e contribuir com trabalho real. Não fabricar participação ou commits.

## 3. Enviar os arquivos

Extrair o ZIP. Enviar os arquivos **de dentro** de margem-humana, não a pasta externa nem o ZIP. Na página inicial do repositório devem aparecer index.html, README.md, LICENSE, css/, js/, assets/ e docs/.

O envio pode ser feito por Add file > Upload files ou por Git. Manter a estrutura de pastas e os nomes exatos. Se usar o upload do navegador, verificar se os arquivos .gitignore e .nojekyll também foram enviados; alguns seletores podem ocultá-los.

Usar mensagens Conventional Commits correspondentes ao trabalho real: `feat: adiciona versao inicial assistida por IA`, `fix: corrige comportamento identificado na revisao`, `docs: registra verificacao da dupla`. Não atribuir commits de código gerado ao trabalho manual de estudantes.

## 4. Ativar GitHub Pages

Settings > Pages > Build and deployment > Source: Deploy from a branch. Selecionar main (ou a branch principal), pasta / (root), Save. Aguardar a execução e copiar a URL real exibida pelo GitHub. Não é necessário Node no deploy: app.bundle.js já está pronto.

Adicionar a URL real ao README. Referência: https://docs.github.com/en/pages/getting-started-with-github-pages/configuring-a-publishing-source-for-your-github-pages-site.

## 5. Conferir a versão publicada

| Verificação | Resultado esperado | Registro da dupla |
|---|---|---|
| Página inicial | Abre pelo link público, sem erro 404 | Preencher |
| Assets locais | CSS, JS, favicon e preview sem caminhos quebrados | Preencher |
| Menu e accordion | Operáveis por teclado, estados corretos | Preencher |
| Simulador | Quatro casos, feedback, resultado, reinício e TXT | Preencher |
| Gráfico | Três indicadores, fonte e tabela correspondentes | Preencher |
| Tema | Alterna e persiste quando o navegador permite | Preencher |
| Telas e zoom | 320 a 1440 px, zoom 200%, sem perda de controles | Preencher |
| Navegadores | Registrar versão de Chrome, Firefox e Safari usados | Preencher |
| Leitor de tela | Rótulos e ordem compreensíveis | Preencher |
| Console | Nenhuma exceção de JavaScript | Preencher |

Testes locais já realizados estão em VALIDACAO.md. Não equivalem à verificação da URL publicada ou a uma auditoria manual da dupla.

## Entrega ao professor

Entregar o link do repositório e o link real do GitHub Pages. O README deve incluir o preview, arquitetura, versões, contratos, matriz de colaboração, **nomes e links reais** e referências. O logbook precisa distinguir a revisão técnica feita por IA da intervenção realmente executada pelos estudantes.

**Verificação final:** use `docs/CHECKLIST.md` (nove itens) e `docs/REGISTRO_DA_DUPLA.md` (evidências humanas). Não enviar o link enquanto houver campos `[PREENCHER]` essenciais.
