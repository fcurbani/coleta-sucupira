# Coleta Sucupira · PPGEAL/UFSC

Página única (`index.html`) para a coleta anual de dados do PPGEAL para a Plataforma Sucupira. Publicada no GitHub Pages.

## Endereços

- `…/` → formulário do docente
- `…/#leia-me` → leia-me para os docentes
- `…/#exemplo` → docente fictício preenchido, para os professores verem como fica
- `…/#admin` → painel da secretaria (com senha)
- `…/#leia-me-secretaria` → guia da secretaria (ciclo anual completo)
- `…/#relatorio-2026` → relatório anual do ano indicado (com senha)

## O que o docente preenche

Missões e cooperação, Solidariedade institucional (nacional/internacional), Organização de eventos, Palestras, Ações e Cursos de extensão, Comitês e representações, Convênios e acordos, Produtos em destaque, Disciplinas ministradas **fora** do PPGEAL e Egressos.

Não são cadastrados no formulário (a secretaria busca na fonte): publicações (Web of Science e Lattes), patentes (Lattes), projetos de pesquisa (SIGPEX/UFSC) e disciplinas, orientações e bancas do PPGEAL (CAPG).

O rascunho do docente fica só no navegador dele; ele envia um arquivo `.json` por e-mail à secretaria.

## Ciclo anual da secretaria (painel `#admin`)

0. Escolher o **Ano-base**.
1. Importar os `.json` dos docentes.
2. Importar as planilhas do CAPG: Ingressantes, Concluintes, Regulares e Disciplinas oferecidas (CPF, nascimento, raça, deficiência e e-mail são descartados na leitura).
3. Importar os currículos Lattes salvos com Ctrl+S → “Página da Web, somente HTML” (também aceita .xml/.zip).
4. Copiar a **consulta pronta** do WoS (ResearcherIDs e ORCIDs), exportar em Excel com *Full Record* e importar.
5. Conferir o **dashboard**, exportar o **Excel consolidado** e gerar o **relatório** (Imprimir → Salvar como PDF).

Os dados importados ficam só no navegador da secretaria. Guarde os arquivos de origem numa pasta do ano e **nunca** os envie ao GitHub.

## Configuração (bloco `CONFIG` no topo do `index.html`)

- `anoPadrao`, `prazoLattes`, `emailSecretaria`
- `modoTeste` → `false` antes de divulgar
- `senhaSecretariaHash` → hash SHA-256 da senha da secretaria
- `docentes` e `identificadores` (ID Lattes, ORCID, ResearcherID, Google Acadêmico)
- `areaConcentracao` e `linhas` (com os projetos de pesquisa)

## Publicar uma nova versão

No repositório: **Add file → Upload files** → arraste o `index.html` → **Commit changes**. A página atualiza em cerca de 1 minuto (abra com Ctrl+F5).

## Servidor opcional

`apps-script/Codigo.gs` permite receber os envios dos docentes direto numa planilha Google, sem e-mail. Instruções no próprio arquivo. Para usar, preencha `CONFIG.endpoint` com a URL do App da Web.
