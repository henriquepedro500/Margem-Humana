# Checklist final de submissão — Margem Humana

**Atualização:** 02/11/2026. Os estados abaixo dizem respeito ao **pacote local**, não ao futuro repositório. O que depende de dois estudantes ou de um link público fica pendente até haver prova. Não marcar como feito apenas porque há instruções para realizar.

| Item da atividade | Estado atual | Evidência no ZIP | Ação necessária antes de entregar |
|---|---|---|---|
| **1. Tema inovador, delimitado e fundamentado** | ✅ Atendido documentalmente | `docs/PESQUISA.md`, recorte de atendentes iniciantes e autonomia para contestar IA; referências QJE e Deloitte | A dupla deve conferir e conseguir explicar os limites das fontes. |
| **2. HTML5 semântico e hierarquia acessível** | ✅ Atendido no código | `index.html`: `header`, `nav`, `main`, `section`, `article`, `aside`, `footer`, um `h1` e demais cabeçalhos | Reavaliar navegação com teclado e leitor de tela, se disponível. |
| **3. `styles.css` com `:root` e autoria** | 🟡 Parcial | `css/styles.css` possui `:root`, cores próprias, Grid/Flexbox, media queries e estilos personalizados | As estilizações foram geradas com auxílio de IA. A dupla deve fazer revisão e decisões próprias reais, registradas com commits. |
| **4. Bootstrap 5 via CDN e grid testado** | 🟡 Parcial | `index.html` importa Bootstrap 5.3.8 do CDN, usa `container`, `row` e `col-*` e possui fallback local; `VALIDACAO.md` tem ensaios anteriores | Repetir no navegador os tamanhos de 320, 375, 768, 1024 e 1440 px; verificar carregamento do CDN com rede e registrar. |
| **5. Microaplicação e gráficos sem erro no Console** | 🟡 Parcial | `js/simulator.js`, `js/chart.js` e `js/app.bundle.js`; `npm test` 4/4 em 02/11/2026; testes de DOM disponíveis | Abrir **F12 → Console** e **Network**, simular quatro casos, baixar TXT, trocar indicadores e tema, registrar resultado real. A navegação direta foi bloqueada pelo ambiente, mas um teste real no Chromium com HTML/CSS/JS locais incorporados confirmou o fluxo; não substitui testar o URL publicado. |
| **6. `AUDITORIA_IA.md` com ≥3 fichas completas** | ✅ Atendido na estrutura documental | `AUDITORIA_IA.md` contém 3 fichas com **Prompt**, **Resposta**, **Diagnóstico** e **Refatoração**, diff e versões originais em `auditoria/v1/` | Registrar contribuição crítica real da dupla. Os três prompts técnicos são reconstruídos; não são três pedidos literais dos integrantes. |
| **7. Commits de ambos os integrantes** | ❌ Pendente | ZIP não possui `.git` e não há GitHub vinculado | Cada estudante deve colaborar de verdade com sua conta e gerar commits próprios e verificáveis; registrar URLs/hashes em `docs/REGISTRO_DA_DUPLA.md`. |
| **8. README com seções e referências** | 🟡 Parcial | `README.md` reúne preview, arquitetura, contratos, dependências, pesquisa, fontes e checklist | Preencher nomes, perfis, links reais do GitHub e Pages, papéis, evidências e data antes da entrega. |
| **9. Deploy GitHub Pages público validado** | ❌ Pendente | Arquivo `.nojekyll`, `index.html` na raiz e roteiro `docs/ENTREGA.md` | Publicar no repositório, abrir o link público, verificar erros 404, assets, responsividade, funcionalidades e F12. |

## O que já foi conferido nesta revisão

- **Lógica:** `npm test` → 4 testes aprovados, nenhum erro (02/11/2026).
- **Build:** `npm run build` regenerou `js/app.bundle.js`; `node --check js/app.bundle.js` não encontrou erro de sintaxe.
- **Arquivos:** código-fonte modular, bundle, Bootstrap/Chart.js locais, CSS, HTML, preview e documentação presentes.
- **Navegador:** as tentativas de navegar diretamente por `file://` e `http://127.0.0.1` receberam `net::ERR_BLOCKED_BY_ADMINISTRATOR`. Para verificar a interface, o Chromium headless recebeu o HTML e os mesmos CSS/JS locais **incorporados em memória** (sem abrir a URL). Neste modo: **0 erros de Console e 0 exceções de JavaScript**, **0 transbordamento horizontal** em 320, 375, 768, 1024 e 1440 px, **4 cenários**, **8/8 pontos**, download TXT, reinício, **3 indicadores**, tema, menu móvel e accordion aprovados. A construção do Chart.js também foi simulada com erro: tabela permaneceu operável e a mensagem de contingência apareceu. **Limite:** esse teste verifica os códigos no navegador real, mas não o carregamento de arquivos/CDN pela rede nem o endereço público. A dupla deve testar a URL final.

## Como a dupla conclui os itens amarelos ou vermelhos

1. Preencher o [registro de colaboração e testes](REGISTRO_DA_DUPLA.md) com ações realizadas de fato, sem atribuir à dupla alterações feitas exclusivamente por IA.
2. Revisar código e design com intervenção humana, rodar os testes e conferir o site em dispositivos/DevTools, registrando achados e correções próprias.
3. Criar repositório público e efetuar commits reais pelas duas contas.
4. Publicar e validar a URL real do GitHub Pages, registrar resultado e preencher os links no README.
5. Só depois entregar o endereço do repositório e do site ao professor.

> **Importante:** esta tabela é um instrumento de verificação, não uma declaração de que a dupla já cumpriu os requisitos de autoria, publicação ou testes manuais.
