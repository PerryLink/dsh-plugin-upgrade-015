<div align="center">

# ⬆️ dsh-plugin-upgrade-015
- **Canal da loja 1024**: rode `npm i -g dsh1024` uma vez e depois `dsh1024 plugin --profile web add dsh-plugin-upgrade-015` (conta para o ranking de instalações do [deepseek1024.com](https://deepseek1024.com)).
[![Gitee](https://img.shields.io/badge/Gitee-mirror-c71d23?logo=gitee)](https://gitee.com/perrylink/dsh-plugin-upgrade-015)
[![dshfind](https://dshfind.com/api/badge/PerryLink/dsh-plugin-upgrade-015?metric=downloads&lang=pt)](https://dshfind.com/pt/plugins/PerryLink/dsh-plugin-upgrade-015?ref=badge)

> 🪦 **RETIRADO — sem manutenção desde 2026-10-05.** Este pacote foi retirado pelo mantenedor. **Todas as atualizações de plugins agora passam pelo [`dsh-plugin-upgrade`](https://github.com/PerryLink/dsh-plugin-upgrade)** (npm `dsh-plugin-upgrade`), que carrega todos os corredores e encaminha cada repositório pela **versão que o próprio repositório fixa** (`engines.dsh` / faixas de peers / devDeps) — portanto não é mais necessário um pacote com versão travada por salto do host. **Não adote `dsh-plugin-upgrade-015` para trabalho novo**; ele não recebe mais correções, versões nem atualizações de segurança. Mantido público apenas como referência. O conhecimento de corredores que ele carregava está preservado nos cartões de referência do `dsh-plugin-upgrade`.

**Habilidade de atualização de plugins para o DeepSeek Harness, com versão travada e fundida — `0.1.3-alpha.1` → `0.1.5-rc.1`, carregada em duas pernas fechadas.**

*Perna A `0.1.3-alpha.1` → `0.1.5-alpha.1`, perna B `0.1.5-alpha.1` → `0.1.5-rc.1`: um cartão de corredor mais um scanner de costuras sem dependências sobre o catálogo fundido de 20 costuras, para que uma metade de cliente que parou de montar em silêncio nunca seja confundida com «typecheck verde».*

> **Repositório oficial.** Este é o único repositório oficial de dsh-plugin-upgrade-015, mantido pela PerryLink. Ele substitui os dois pacotes com versão travada `dsh-plugin-upgrade` (perna A) e `dsh-plugin-upgrade-rc1` (perna B). Repositórios com o mesmo nome em outras contas não são afiliados.

[![License](https://img.shields.io/badge/license-Apache%202.0-blue.svg)](LICENSE)
[![DSH plugin](https://img.shields.io/badge/dsh--plugin-✅-green)](https://github.com/topics/dsh-plugin)
[![dsh-doctor](https://raw.githubusercontent.com/PerryLink/dsh-plugin-doctor/main/badges/PerryLink__dsh-plugin-upgrade-015.svg)](https://github.com/PerryLink/dsh-plugin-doctor#verified-徽章)
[![DSH Market](https://raw.githubusercontent.com/2BingLing/dsh-market/master/assets/readme/badge-listed-en.svg)](https://dsh.market/)
[![Node](https://img.shields.io/badge/node-%5E22.19%20%7C%7C%20%3E%3D24-brightgreen.svg)](#)
[![CI](https://img.shields.io/github/actions/workflow/status/PerryLink/dsh-plugin-upgrade-015/ci.yml?branch=main&label=CI)](https://github.com/PerryLink/dsh-plugin-upgrade-015/actions)
[![Version](https://img.shields.io/github/v/tag/PerryLink/dsh-plugin-upgrade-015?label=version)](https://github.com/PerryLink/dsh-plugin-upgrade-015/releases)
[![npm version](https://img.shields.io/npm/v/dsh-plugin-upgrade-015)](https://www.npmjs.com/package/dsh-plugin-upgrade-015)
[![npm downloads](https://img.shields.io/npm/dm/dsh-plugin-upgrade-015)](https://www.npmjs.com/package/dsh-plugin-upgrade-015)

[English](README.md) · [简体中文](README-zh.md) · [Español](README-es.md) · [Português](README-pt.md) · [हिन्दी](README-hi.md)

```sh
dsh plugin --profile <name> add dsh-plugin-upgrade-015
```


</div>

---

## Instalação e desinstalação

```sh
dsh plugin --profile web add dsh-plugin-upgrade-015            # do npm
dsh plugin --profile web add "github:PerryLink/dsh-plugin-upgrade-015#main"   # do código-fonte
dsh plugin --profile web remove dsh-plugin-upgrade-015         # desinstalar (reversível)
```

Instalar o bundle apenas registra uma habilidade; remover a linha remove a habilidade. A CLI é um alvo `npx` normal e não precisa de perfil algum.

## Compatibilidade

| Superfície | Estado |
|---|---|
| Harness | DeepSeek Harness `0.1.5-rc.1` (tag `dsh-v0.1.7-rc.1` = `183f08e9c6dd`; passagem da perna A→B `dsh-v0.1.7-rc.1` = `5dda764ed3aa`; início do corredor `0.1.3-alpha.1`). Faixa de peers `@deepseek-ai/dsh-skill >=0.1.2-rc.1 <0.2.0 \|\| >=0.1.5-alpha.1 <0.2.0`, `@deepseek-ai/cordis ^4.0.2`, `@deepseek-ai/schemastery ^3.18.2`. |
| Node | `^22.19.0 \|\| >=24.0.0` |
| Plataformas | Onde o Node rodar; o scanner só usa o sistema de arquivos e é neutro em relação à plataforma |
| Modelo | Modelos somente texto totalmente suportados; a habilidade é um Markdown, sem exigência de ferramentas ou visão |
| Escopo | **Duas pernas fechadas, um único intervalo**: perna A `0.1.3-alpha.1` → `0.1.5-alpha.1` mais perna B `0.1.5-alpha.1` → `0.1.5-rc.1`. Um corredor nunca se alarga: um salto depois de `0.1.5-rc.1` é um novo pacote. |
| Pernas | As duas pernas vivem neste pacote: a perna A mantém as costuras `S1`–`S10` + `M1`, a perna B mantém `C1`, `C2`, `C4`, `C5`, `H1`–`H4`, `P1` — cada uma com suas próprias evidências, seção de cartão, fixtures e caminho de rollback. Não há pacote irmão a instalar. |
| `C3` | Aposentada: o cartão da perna B chamava de `C3` o verde falso da linha de tipos desatualizada, que é o mesmo defeito da `M1` da perna A. A fusão está registrada no cartão; `--seams C3` não corresponde a nada. |
| Pacote anterior | Não monte o retirado `dsh-plugin-upgrade` no mesmo perfil: os dois registram a skill `plugin-upgrade-015`, então a segunda montagem colide nesse nome. Aquele pacote está obsoleto no npm e seu repositório foi retirado; este pacote substitui as suas duas pernas. |

## O que você recebe

Duas metades, um único catálogo de costuras:

- **Uma habilidade de agente empacotada (`plugin-upgrade-015`)** — o cartão do corredor fundido e um ciclo de corrigir-e-verificar. O corpo primeiro encaminha quem chama para a perna que corresponde à sua faixa de peers; o modelo só a carrega quando uma tarefa realmente precisa dela, e o pacote não contribui com nenhum parágrafo de prompt de sistema nem com nenhuma ferramenta.
- **Uma CLI sem dependências (`dsh-plugin-upgrade-015-scan`)** — reporta fatos `file:line` das vinte costuras fundidas (`S3`, `S8`, `S9`, `M1`, `S4`, `S5`, `S6`, `S7`, `S2`, `S1`, `S10`, `C1`, `C2`, `P1`, `C4`, `C5`, `H1`, `H2`, `H4`, `H3`) relidas dos intervalos de tags do harness em 2026-09-09 (perna A) e 2026-09-10 (perna B). Sai com `1` em qualquer achado de severidade error, então entra direto no CI.

O objetivo é o modo de falha que este corredor existe para matar: **a quebra deste intervalo é em grande parte silenciosa, pelas duas pontas.** A linha de tipos pode estar desatualizada, então o repositório compila contra o **catálogo antigo** (costura `M1`), e o slot de cliente puro `conversation` foi removido sem alias enquanto `ctx.slots.inject()` só executa o callback quando a declaração existe — então uma metade de cliente que ainda aponta para ele para de montar sem erro, sem linha de log e sem build quebrado (costura `C1`). Três classes de quebra sobrevivem a `typecheck` + `test`:

1. o portão local compila uma linha de tipos desatualizada — alias `paths` antigo, ou tipos de dev/test fixados em `0.1.5-alpha.*` (costura `M1`);
2. um escritor de log omite o campo `stream` exigido pelo V3, então a sessão é importada e depois se recusa a retomar (costura `S3`);
3. os testes são simulados contra a forma antiga, então passam enquanto o host descarta a contribuição (costura `C1`).

Medição honesta: a varredura do workspace da perna B encontrou que as metades de cliente da família usam apenas **8** chaves de slot, e todas as 8 sobrevivem no rc.1 — para elas a quebra do rc.1 é **latente, não real**. Os plugins de cliente de terceiros que apontavam para a chave pura `conversation` são os que quebram, e quebram em silêncio. A varredura da perna A encontrou a textura oposta: 40 repositórios, 11 deles atingidos por `M1`, e corrigir o caminho desatualizado expôs erros reais de TypeScript em 3 repositórios que antes estavam «verdes».

## Início rápido

```sh
# 1. instale o bundle no seu perfil
dsh plugin --profile web add dsh-plugin-upgrade-015

# 2. confirme que a linha montou
dsh --profile web --dump-config | grep -A3 'id: dsh-plugin-upgrade-015'

# 3. escaneie o plugin que você vai atualizar
npx dsh-plugin-upgrade-015-scan --repo ../my-plugin
```

Depois peça ao agente para usar a habilidade `plugin-upgrade-015`, ou conduza o ciclo você mesmo com o cartão em
`skills/plugin-upgrade-015/references/v0.1.3-alpha.1-to-v0.1.5-rc.1.md` (a perna A é a §1, a perna B é a §2, o índice fundido de costuras é a §3).

## Configuração

Toda chave é opcional e fica no patch do perfil:

| Chave | Padrão | Significado |
|---|---|---|
| `enabled` | `true` | Registra a habilidade empacotada. Use `false` para manter a dependência montada porém silenciosa. |
| `skillName` | `plugin-upgrade-015` | Diretório sob `skillsRoot` a registrar, e o nome exibido no catálogo. |
| `skillsRoot` | o `./skills` do próprio pacote | Onde vive `<skillName>/SKILL.md`. Aponte para o seu próprio cartão para reutilizar a infraestrutura. |
| `userInvocable` | `true` | Se uma pessoa pode invocar a habilidade pelo nome além do modelo. |

```yaml
- insert:
    - id: dsh-plugin-upgrade-015
      name: dsh-plugin-upgrade-015
      config:
        skillName: plugin-upgrade-015
```

O plugin monta de forma ruidosa: um `SKILL.md` ausente, um corpo vazio ou um frontmatter sem `name` fazem a montagem falhar em vez de registrar uma habilidade vazia.

## Superfícies

**Habilidade** — `plugin-upgrade-015` (invocável pelo modelo e por pessoas por padrão). Corpo: tabela de encaminhamento por perna, as 8 regras rígidas e o ciclo de 6 passos. Referências: o cartão do corredor fundido. Scripts: o detector, enviado dentro do diretório da habilidade para que os caminhos relativos resolvam.

**CLI** — `dsh-plugin-upgrade-015-scan`:

```sh
dsh-plugin-upgrade-015-scan [--repo <path>] [--json <out.json>] [--seams S3,C1,P1] [--quiet]
```

| Flag | Significado |
|---|---|
| `--repo <path>` | Repositório a escanear (padrão: diretório atual). |
| `--json <out.json>` | Também grava o relatório legível por máquina (`repo`, `scannedAt`, `files`, `hits[]`, `bySeam`). |
| `--seams S3,C1,P1` | Restringe a costuras específicas do catálogo fundido. |
| `--quiet` | Suprime a renderização humana (combine com `--json`). |

Códigos de saída: `0` nenhum achado de severidade error · `1` ao menos um achado de severidade error · `2` uso ou falha do escaneamento. Um escaneamento limpo é necessário mas não suficiente — o critério de saída é um smoke real no host, mais uma ida-e-volta de retomada para escritores de log (perna A) e uma asserção em navegador real para a metade de cliente (perna B).

## As vinte costuras

A ordem segue o catálogo em `lib/scan.mjs` (perna A primeiro, depois perna B), que também é a ordem à qual `test/card.test.mjs` fixa o cartão.

| Id | Severidade | O que mudou no caminho até `0.1.5-rc.1` |
|---|---|---|
| `S3` | error | `assistant/message` ganhou um campo `stream` obrigatório (formato de sessão V3): um log escrito sem ele é importado com sucesso e depois se recusa a retomar (`Session.fromRestore` lança `invalid settlement fields`). |
| `S8` | error | `SessionHandle.read()` retorna `SessionHandleReadResult` (`{ eventState, events }`) em vez do array de eventos; operações de array precisam desembrulhar `.events`. |
| `S9` | error | A configuração de `SystemPrompt` renomeou `persona` → `personaPrefix` / `personaSuffix`. Substituir por `includeHarnessIdentity: false` **não** é equivalente — isso apaga o bloco de identidade do harness. |
| `M1` | error | O portão local compila uma linha de tipos desatualizada: tipos de dev/test fixados em `0.1.5-alpha.*`, ou um alias `paths` do `tsconfig` resolvendo para um diretório de checkout inexistente, fazem o TypeScript cair em silêncio nos tipos publicados. Portão verde, régua errada. |
| `S4` | error | `tool/code-dispatch` foi renomeado para `tool/ptc-dispatch`; o rótulo antigo não é mais reconhecido em sessões V3. |
| `S5` | error | `ctx.agent` foi removido: quem chama deve passar o Agent explicitamente (por exemplo, o segundo parâmetro de `setup(agentCtx, agent)`). |
| `S6` | error | `Inbox` é uma interface de tipo, não uma classe construível; as fixtures usam a forma oficial não suportada e o código de runtime lê `agent.inbox`. |
| `S7` | warn | `SubprocessHandle.pid` foi removido (só resta `SubprocessTerminalHandle.pid`); remova o campo das fixtures de teste. |
| `S2` | warn | `EpochHeader.system` foi removido: o prompt de sistema agora é o `system/message` do nó de superfície 0. |
| `S1` | warn | Formato de sessão V3 e nomes de log com sufixo de geração — a geração atual é `session.v3.jsonl.zstd`, então scripts que fixam `session.jsonl.zstd` falham em silêncio. |
| `S10` | warn | Eventos de sessão escritos por plugins precisam passar pelo portão de adaptação fail-closed do host: `Session.append` não tem canal de escrita `ignorable`, então um append incondicional pode tornar uma sessão ilegível. |
| `C1` | error | O slot de cliente puro `conversation` foi removido e substituído por `main` + `main.conversation`, **sem alias**. `ctx.slots.inject()` só dispara quando a declaração existe, então um plugin que aponta para ele para de montar **em silêncio**. |
| `C2` | error | `@deepseek-ai/dsh-client-ui-sidebar-textpreview` virou `…-sidebar-documentpreview`; o nome antigo sumiu e não há pacote shim. |
| `P1` | error | A faixa de peers deve manter o segundo segmento: `>=0.1.2-rc.1 <0.2.0` sozinho **rejeita** `0.1.5-rc.1` pela regra prerelease-tuple do npm semver (medido `false` no semver 7.8.5). |
| `C4` | warn | O rc.1 adicionou um modelo de painel principal global (`main`, `sidebar.panellist`, `ctx.layout.selectPanel(MainPanelId \| null)`) e acrescentou a prop padrão `usePanelInfo` a quase todos os slots. |
| `C5` | warn | A pré-visualização de documentos migrou para o slot com chave `sidebar.right.tab.document` (`DocumentContent`); `sidebar.right.pane.tab` sobrevive, mas sua entrada pai passou a ser `rightbar.session`. |
| `H1` | warn | `KNOWN_SESSION_EVENT_TYPES` ganhou `deliverables/presented` e `subagent/catalog`: o vocabulário fail-closed cresceu. |
| `H2` | warn | A linha da nova ferramenta `present` ocupa a chave `'present'` de `tool.call.toolview`, que no alpha.1 estava livre. |
| `H4` | info | O catálogo consultivo padrão do adaptador DeepSeek agora começa com `deepseek-flash` (DeepSeek-V41-Flash). |
| `H3` | info | Novas capacidades opcionais: `ctx.sessionFeedback`, `ctx.layout.beginNavigation()`, `ctx.workspaces.openSession()` / `openWorkspace()` / `forkSession()`. Listadas no cartão; deliberadamente sem detecção automática. |

`S7`, `S2`, `S1`, `S10`, `C4`, `C5`, `H1`, `H2` e `H4` são deliberadamente consultivas: têm correspondências legítimas (um repositório que já usa a API nova, um snapshot de documentação, a tabela de ids de modelo de um plugin, um `ChildProcess.pid` do Node), então o scanner as reporta como pistas para revisão manual, não como falhas. `M1` e `P1` são verificações **estruturadas** — resolvem `package.json` e `tsconfig*.json` em vez de casar texto — e `H3` é **somente-cartão**: documentada, com paridade de id verificada e deliberadamente sem detector (`CARD_ONLY = ['H3']`).

## O que isto não cobre

- **Um salto depois de `0.1.5-rc.1`.** O intervalo fundido termina no rc.1 por construção: o salto do harness `0.1.5-rc.1` → `0.1.5-rc.2` não acrescentou nenhuma costura voltada a plugins (o pin de dev/test deste próprio pacote roda agora na linha `0.1.7-rc.1`, para que o catálogo seja verificado contra os tipos publicados mais recentes; a sonda do workflow compat segue ancorada em `0.1.6-alpha.2`). Qualquer coisa que acrescente uma costura depois é um **novo pacote** — um cartão que deriva é pior do que nenhum cartão.
- **O salto `0.1.1` → `0.1.2`.** Use a habilidade de convergência da comunidade.
- **Repetir costuras entre pernas.** A perna A é dona das costuras do formato de sessão (`assistant/message.stream`, `SessionHandleReadResult`, `EpochHeader.system`, `ctx.agent`, `Inbox`, `SystemPrompt.persona`, a geração de log V3) e a perna B não as repete — todo o diff de `packages/core/session/src` no intervalo da perna B são dois literais de tipo de evento acrescentados e uma linha de comentário. A seção de cartão de cada perna mantém sua própria declaração de escopo.
- **O caminho de atualização do usuário do DSH.** Este pacote atualiza *código-fonte de plugins*, não a instalação do harness de um usuário.
- **Tokens de tema.** `docs/web-styling.md` não tem nenhuma mudança no intervalo da perna B.
- **Prova.** Um escaneamento limpo é uma hipótese. O critério de saída é um smoke real no host (`DSH_HOME` temporário, CLI alvo, `plugin add <tarball>`, `--dump-config`) mais uma ida-e-volta de retomada para escritores de log de sessão (perna A) e uma asserção em navegador real para cada achado do lado cliente (perna B).

## Limites de segurança

- **Escaneamento somente leitura.** A CLI nunca escreve dentro do repositório escaneado; `--json` grava apenas no caminho que você indicar.
- **Sem rede, sem shell.** O scanner não importa nada além da biblioteca padrão do Node e nunca inicia um processo.
- **Sem segredos.** Nada no pacote lê credenciais, tokens de ambiente ou dados de sessão.
- **Receita de smoke em sandbox.** A verificação de host real do cartão usa um `DSH_HOME` de `mkdtemp`; nunca toca o seu `~/.dsh` real.

## Desenvolvimento

```sh
npm install                        # ou: pnpm install (o repositório inclui pnpm-lock.yaml)
npm test                           # node --test: scanner, paridade cartão<->catálogo, Cordis + SkillRegistry reais
npm run verify:self-contained      # todo import resolve dentro do pacote
npm run verify:artifacts           # o tarball leva a habilidade, a CLI e o patch, e exclui os testes
npm run check:readmes              # consistência dos READMEs em cinco idiomas
npm pack
```

O scanner tem um par de fixtures sintéticas **por perna**: `fixtures/leg-a-bad-repo` (as costuras de sessão/config da perna A, com toda costura de erro presente de propósito) com `fixtures/leg-a-good-repo` (adaptado), e `fixtures/bad-repo` (as costuras de slot de cliente da perna B) com `fixtures/good-repo` (adaptado) — além de um negativo ao vivo em um repositório da família já fixado no `0.1.5-rc.1`, de modo que uma regressão no catálogo falha nesta suíte e não em um usuário a jusante. `test/card.test.mjs` afirma que o índice do cartão fundido e `lib/scan.mjs` nomeiam **exatamente** os mesmos vinte ids de costura com as mesmas severidades, e que `CARD_ONLY` é exatamente `['H3']` — a regra de vinculação de evidência como portão de máquina.

## Tópicos

`dsh`, `dsh-plugin`, `deepseek-harness`, `deepseek`, `cordis`, `plugin-upgrade`, `migration`, `skill`, `version-card`, `scanner`, `client-slots` (espelham as `keywords` do `package.json`; `dsh-plugin` é o canal de visibilidade do ecossistema).

## Licença

Apache-2.0 — veja [LICENSE](LICENSE). As dependências de instalação e suas licenças estão em [THIRD_PARTY_NOTICES.md](THIRD_PARTY_NOTICES.md); nada é empacotado.


## PerryLink DSH Plugin Family

Este projeto é um dos **87 plugins ativamente mantidos** do DeepSeek Harness da [PerryLink](https://github.com/PerryLink). O registro da família tem **95** plugins — **5 congelados**, **3 retirados** — e fica recolhido abaixo para que cada README mantenha uma primeira tela curta. Expanda para ver cada linha, com o motivo na coluna Status.

<details>
<summary>Expandir os 95 plugins</summary>

| Plugin | Uma linha | Status |
|---|---|---|
| **[dsh-aqua-input-check](https://github.com/PerryLink/dsh-aqua-input-check)** | 水产养殖投入品记录核对（按投入品用量、休药期与起捕间隔核对记录自洽，仅提示差异，不作出定性结论） |  |
| **[dsh-archive-check](https://github.com/PerryLink/dsh-archive-check)** | 档案归档完整性与保管期限核对（依据《档案法》及配套规定，仅提示差异，不作出定性结论） |  |
| **[dsh-auto-review](https://github.com/PerryLink/dsh-auto-review)** | Second-model auto-review on the approval chain, fail-closed by default |  |
| **[dsh-autotier](https://github.com/PerryLink/dsh-autotier)** | Automatic strong/cheap model-tier routing with deterministic risk guards and a `/tier` command |  |
| **[dsh-background-agents](https://github.com/PerryLink/dsh-background-agents)** | Durable background child agents with a Web UI sidebar, messaging and interrupt | 🚫 RETIRADO — ver o README do repositório |
| **[dsh-bid-ca-precheck](https://github.com/PerryLink/dsh-bid-ca-precheck)** | 投标文件符合性预检（按招标文件逐条核对响应情况，仅提示差异，不作出定性结论） |  |
| **[dsh-bid-qual-check](https://github.com/PerryLink/dsh-bid-qual-check)** | 投标人资格条件核对（按资格条件与证明材料核对逐条响应，仅提示差异，不作出定性结论） |  |
| **[dsh-budget](https://github.com/PerryLink/dsh-budget)** | Cost governance for DeepSeek Harness: budgets, carbon, and latency in one panel. | 🧊 CONGELADO — ver o README do repositório |
| **[dsh-cert-mcp](https://github.com/PerryLink/dsh-cert-mcp)** | Read-only MCP server exposing the certification registry: grades, snapshots and five-dimension evidence |  |
| **[dsh-checkpoint-rewind](https://github.com/PerryLink/dsh-checkpoint-rewind)** | Claude Code /rewind-equivalent: snapshots, session forks, one-shot restore |  |
| **[dsh-claude-move](https://github.com/PerryLink/dsh-claude-move)** | Migrate Claude Code sessions, memory, skills and CLAUDE.md into DSH | 🧊 CONGELADO — ver o README do repositório |
| **[dsh-click](https://github.com/PerryLink/dsh-click)** | Cross-platform native desktop control for DeepSeek Harness — Windows first. |  |
| **[dsh-composer-history](https://github.com/PerryLink/dsh-composer-history)** | Terminal-style input history for the web composer: arrows, Ctrl+R search |  |
| **[dsh-contract-stance](https://github.com/PerryLink/dsh-contract-stance)** | 合同条款立场台账核对（按立场、风险等级与退让底线核对台账自洽，仅提示差异，不作出定性结论） |  |
| **[dsh-customs-doc-check](https://github.com/PerryLink/dsh-customs-doc-check)** | 报关单证一致性核对（按公开的报关单填制规范核对单证间字段一致性，仅提示差异，不作出定性结论） |  |
| **[dsh-data-quality](https://github.com/PerryLink/dsh-data-quality)** | Dataset quality checks and citation cross-checks (the optional numeric bridge consumed here) |  |
| **[dsh-defend](https://github.com/PerryLink/dsh-defend)** | Prompt-injection, jailbreak, and secret-leak defense for DeepSeek Harness. | 🧊 CONGELADO — ver o README do repositório |
| **[dsh-demurrage-ledger](https://github.com/PerryLink/dsh-demurrage-ledger)** | 滞箱费台账核对（按免箱期与费率核对超期天数与金额的自洽性，仅提示差异，不作出定性结论） |  |
| **[dsh-doublecheck](https://github.com/PerryLink/dsh-doublecheck)** | Engineering-discipline guard: requirements grill, test gates, adversary review |  |
| **[dsh-draw](https://github.com/PerryLink/dsh-draw)** | Unified static-image generation routing for DeepSeek Harness. | 🧊 CONGELADO — ver o README do repositório |
| **[dsh-drill-script-check](https://github.com/PerryLink/dsh-drill-script-check)** | 应急演练脚本核对（按阶段、响应分级、指挥与资源要素核对脚本齐备，仅提示差异，不作出定性结论） |  |
| **[dsh-eia-guide-check](https://github.com/PerryLink/dsh-eia-guide-check)** | 环评导则适用性核对（按要素、导则名称与执行标准核对台账自洽，仅提示差异，不作出定性结论） |  |
| **[dsh-emergency-plan](https://github.com/PerryLink/dsh-emergency-plan)** | 应急预案要素齐备性与条款级页码定位（依据 GB/T 29639-2020 等公开文件，仅提示差异，不作出定性结论） |  |
| **[dsh-essay-rubric-check](https://github.com/PerryLink/dsh-essay-rubric-check)** | 作文量表评分核对（按评分项、原文定位与分值算术核对评分自洽，仅提示差异，不作出定性结论） |  |
| **[dsh-evidence-check](https://github.com/PerryLink/dsh-evidence-check)** | 证据清单齐备性核对（按待证事实与证据要素核对清单自洽，仅提示差异，不作出定性结论） |  |
| **[dsh-export-ctl-check](https://github.com/PerryLink/dsh-export-ctl-check)** | 出口管制物项核对（按管制清单、最终用途与许可证核对台账齐备，仅提示差异，不作出定性结论） |  |
| **[dsh-fast](https://github.com/PerryLink/dsh-fast)** | Read-only performance diagnostics for DeepSeek Harness. |  |
| **[dsh-fmea-table-check](https://github.com/PerryLink/dsh-fmea-table-check)** | FMEA 分析表要素齐备性与风险顺序数一致性核对（按公开的 FMEA 方法标准核对表内自洽，仅提示差异，不作出定性结论） |  |
| **[dsh-forecast-penalty](https://github.com/PerryLink/dsh-forecast-penalty)** | 预测准确率考核核对（按准确率、门槛与考核单价核对考核费用的算术自洽，仅提示差异，不作出定性结论） |  |
| **[dsh-fund-research](https://github.com/PerryLink/dsh-fund-research)** | Deterministic research reports for Chinese public mutual funds |  |
| **[dsh-github](https://github.com/PerryLink/dsh-github)** | GitHub PR/issues integration for DSH, every write gated by approval |  |
| **[dsh-gongwen-flow-check](https://github.com/PerryLink/dsh-gongwen-flow-check)** | 公文流转与办理时限核对（按公开的公文处理规范核对环节完整性与时限，仅提示差异，不作出定性结论） |  |
| **[dsh-gongwen-word-check](https://github.com/PerryLink/dsh-gongwen-word-check)** | 公文格式要素核对（按公开的党政机关公文格式标准核对版头与主体要素，仅提示差异，不作出定性结论） |  |
| **[dsh-guard-plan-qc](https://github.com/PerryLink/dsh-guard-plan-qc)** | 劳动保护与安全防护用品配置表核对（按公开的配备标准核对品名规格与配置数量，仅提示差异，不作出定性结论） |  |
| **[dsh-hazchem-check](https://github.com/PerryLink/dsh-hazchem-check)** | 危险化学品临界量与重大危险源辨识核对（按储存量与临界量核对台账自洽，仅提示差异，不作出定性结论） |  |
| **[dsh-hazplan-check](https://github.com/PerryLink/dsh-hazplan-check)** | HAZOP 分析表要素齐备性与偏差推导一致性核对（依据公开的危险与可操作性分析标准，仅提示差异，不作出定性结论） |  |
| **[dsh-hidden-risk-map](https://github.com/PerryLink/dsh-hidden-risk-map)** | 安全隐患台账→《工贸企业重大事故隐患判定标准》（应急管理部令第10号）条款映射提示（仅提示差异，不作出定性结论） |  |
| **[dsh-hs-classify](https://github.com/PerryLink/dsh-hs-classify)** | 商品归类层级一致性核对（按章、品目、子目与商品编号的层级关系核对自洽，仅提示差异，不作出定性结论） |  |
| **[dsh-icd-rule-check](https://github.com/PerryLink/dsh-icd-rule-check)** | ICD 合并编码与星剑号配对提示（依据 GB/T 14396-2016 与公开的 ICD 使用说明，仅提示差异，不作出定性结论） |  |
| **[dsh-industry-research](https://github.com/PerryLink/dsh-industry-research)** | Industry research orchestration that seals its deliverables through this plugin's `ctx.researchReport.assemble` |  |
| **[dsh-lawcite-adapter](https://github.com/PerryLink/dsh-lawcite-adapter)** | 法条引用与文书要素核对（按名称、条号、原文与效力状态核对引用可核验性，仅提示差异，不作出定性结论） |  |
| **[dsh-laya](https://github.com/PerryLink/dsh-laya)** | Laya typed decisions (`noul`/`choice`/`score`) as a first-class Cordis service and model-visible tools |  |
| **[dsh-lc-doc-check](https://github.com/PerryLink/dsh-lc-doc-check)** | 信用证单据条款核对（按单据种类、份数、期限与不符点核对交单自洽，仅提示差异，不作出定性结论） |  |
| **[dsh-learning-gap-check](https://github.com/PerryLink/dsh-learning-gap-check)** | 能力差距与培养计划核对（按能力等级差、培养措施与完成期限核对台账闭环，仅提示差异，不作出定性结论） |  |
| **[dsh-library](https://github.com/PerryLink/dsh-library)** | Local document knowledge base for DeepSeek Harness. |  |
| **[dsh-local-ai](https://github.com/PerryLink/dsh-local-ai)** | Local-model (Ollama) integration for DeepSeek Harness. |  |
| **[dsh-lsp-actions](https://github.com/PerryLink/dsh-lsp-actions)** | LSP diagnostics, formatting, completion, code actions and rename over language servers |  |
| **[dsh-mask](https://github.com/PerryLink/dsh-mask)** | PII masking middleware: anonymize at the model boundary, restore at the display layer |  |
| **[dsh-mcp-panel](https://github.com/PerryLink/dsh-mcp-panel)** | Read-only MCP runtime panel: /mcp command + Settings tab with status, tools and errors |  |
| **[dsh-medrec-qc](https://github.com/PerryLink/dsh-medrec-qc)** | 病案首页形式质控与逻辑矛盾提示（依据国卫办医发〔2016〕24号等公开文件，仅提示差异，不作出定性结论） |  |
| **[dsh-memento](https://github.com/PerryLink/dsh-memento)** | Approval-gated cross-session memory: ctx.memory seam + SQLite + memory tool |  |
| **[dsh-nsfc-form-check](https://github.com/PerryLink/dsh-nsfc-form-check)** | 国家自然科学基金申请书形式审查与匿名化提示（依据《国家自然科学基金条例》与申请人导入的当年指南，仅提示差异，不作出定性结论） |  |
| **[dsh-nurse-record-check](https://github.com/PerryLink/dsh-nurse-record-check)** | 护理记录时限、签名与评估表完整性校验（依据《病历书写基本规范》等公开文件，仅提示差异，不作出定性结论） |  |
| **[dsh-observe](https://github.com/PerryLink/dsh-observe)** | OpenTelemetry and Langfuse observability exporter for DeepSeek Harness. |  |
| **[dsh-origin-rvc-check](https://github.com/PerryLink/dsh-origin-rvc-check)** | 原产地区域价值成分核对（按 RVC 定义式与门槛核对原产地判定自洽，仅提示差异，不作出定性结论） |  |
| **[dsh-ota-review-check](https://github.com/PerryLink/dsh-ota-review-check)** | 在线点评回复台账核对（按回复时限、问题分类与整改状态核对台账闭环，仅提示差异，不作出定性结论） |  |
| **[dsh-output-styles](https://github.com/PerryLink/dsh-output-styles)** | Claude Code outputStyles-equivalent runtime style switching |  |
| **[dsh-paper-doc-adapter](https://github.com/PerryLink/dsh-paper-doc-adapter)** | 试卷解析结构核对（按题型、答案、分值与 yotta 标识核对试卷结构自洽，仅提示差异，不作出定性结论） |  |
| **[dsh-permission-rules](https://github.com/PerryLink/dsh-permission-rules)** | Claude Code-style declarative allow/deny/ask permission rules with audit |  |
| **[dsh-permit-report-check](https://github.com/PerryLink/dsh-permit-report-check)** | 行政许可办理核对（按申请材料、法定时限与决定记录核对台账闭环，仅提示差异，不作出定性结论） |  |
| **[dsh-pipeline-check](https://github.com/PerryLink/dsh-pipeline-check)** | 项目全流程文件链条核对（按环节先后与金额口径核对链条自洽，仅提示差异，不作出定性结论） |  |
| **[dsh-pleading-draft](https://github.com/PerryLink/dsh-pleading-draft)** | 起诉状要素齐备性核对（按诉请、事实、证据、法条四要素核对文书齐备，仅提示差异，不作出定性结论） |  |
| **[dsh-plugin-doctor](https://github.com/PerryLink/dsh-plugin-doctor)** | Zero-dependency static + sandbox smoke detector for DSH plugins |  |
| **[dsh-plugin-guide](https://github.com/PerryLink/dsh-plugin-guide)** | Plugin-development knowledge base as an on-demand agent skill |  |
| **[dsh-plugin-kit](https://github.com/PerryLink/dsh-plugin-kit)** | Shared zero-runtime-dependency toolkit for the PerryLink DSH plugins |  |
| **[dsh-plugin-upgrade](https://github.com/PerryLink/dsh-plugin-upgrade)** | One-package, one-corridor-index plugin upgrade skill: routes a repository to the matching closed corridor card |  |
| **[dsh-policy-brief-draft](https://github.com/PerryLink/dsh-policy-brief-draft)** | 政策专报要素核对（按观点、依据、出处与建议核对专报齐备，仅提示差异，不作出定性结论） |  |
| **[dsh-power-loss-split](https://github.com/PerryLink/dsh-power-loss-split)** | 线损电量拆分与考核表核对（依据公开的线损计算口径，仅提示差异，不作出定性结论） |  |
| **[dsh-power-ticket-check](https://github.com/PerryLink/dsh-power-ticket-check)** | 电力工作票要素齐备性与签发许可顺序核对（依据现行电力安全工作规程，仅提示差异，不作出定性结论） |  |
| **[dsh-ppap-check](https://github.com/PerryLink/dsh-ppap-check)** | PPAP 提交要素齐备性核对（按公开的 PPAP 手册与提交等级核对要素齐备与版本填写，仅提示差异，不作出定性结论） |  |
| **[dsh-protest-deadline](https://github.com/PerryLink/dsh-protest-deadline)** | 质疑与投诉期限核对（按公开的政府采购质疑投诉规定核对期限与台账自洽，仅提示差异，不作出定性结论） |  |
| **[dsh-railway-window](https://github.com/PerryLink/dsh-railway-window)** | 铁路施工天窗台账核对（按时间窗、时长算术与命令号核对台账自洽，仅提示差异，不作出定性结论） |  |
| **[dsh-reach](https://github.com/PerryLink/dsh-reach)** | Multi-channel approval/question bridge: WeChat/Telegram/Feishu, session console | 🧊 CONGELADO — ver o README do repositório |
| **[dsh-repair-order-qc](https://github.com/PerryLink/dsh-repair-order-qc)** | 维修工单结算核对（按项目金额、配件工时合计与结算总额核对算术自洽，仅提示差异，不作出定性结论） |  |
| **[dsh-research-report](https://github.com/PerryLink/dsh-research-report)** | Verifiable research-report engine: content-addressed evidence ledger and sealed versions |  |
| **[dsh-review-reply-check](https://github.com/PerryLink/dsh-review-reply-check)** | 审稿意见逐条回应覆盖核对（按意见与回应一一对应核对覆盖完整性，仅提示差异，不作出定性结论） |  |
| **[dsh-rulefile-check](https://github.com/PerryLink/dsh-rulefile-check)** | 规则库文件自检核对（按条款引用纪律与效力上限核对规则库自身合规，仅提示差异，不作出定性结论） |  |
| **[dsh-safety-brief-check](https://github.com/PerryLink/dsh-safety-brief-check)** | 安全技术交底记录要素齐备性与签字闭环核对（依据公开的安全生产法规与检查标准，仅提示差异，不作出定性结论） |  |
| **[dsh-score](https://github.com/PerryLink/dsh-score)** | Multi-dimensional quality scoring for DeepSeek Harness plugins. |  |
| **[dsh-session-pin](https://github.com/PerryLink/dsh-session-pin)** | Pin sessions in the Web sidebar with durable ordering | 🚫 RETIRADO — ver o README do repositório |
| **[dsh-session-sync](https://github.com/PerryLink/dsh-session-sync)** | Cross-device session sync for DeepSeek Harness — a dedicated git mirror of your session store. |  |
| **[dsh-site-log-check](https://github.com/PerryLink/dsh-site-log-check)** | 监理日志跨日连续性与旁站覆盖提示（依据 GB/T 50319-2013 等公开文件，仅提示差异，不作出定性结论） |  |
| **[dsh-skill-pack-security](https://github.com/PerryLink/dsh-skill-pack-security)** | Security-audit skill pack: secret scan, dependency and supply-chain review |  |
| **[dsh-soe-decision-check](https://github.com/PerryLink/dsh-soe-decision-check)** | 三重一大决策台账核对（按前置研究、会议审议与决议记录核对程序留痕，仅提示差异，不作出定性结论） |  |
| **[dsh-soilwater-check](https://github.com/PerryLink/dsh-soilwater-check)** | 土壤与地下水监测台账核对（按点位、监测项目、限值与超标判定核对台账自洽，仅提示差异，不作出定性结论） |  |
| **[dsh-sop-sync-check](https://github.com/PerryLink/dsh-sop-sync-check)** | 作业规程与 FMEA／控制计划一致性核对（按编号与版本核对三份文件是否同步，仅提示差异，不作出定性结论） |  |
| **[dsh-spc-gbt-adapter](https://github.com/PerryLink/dsh-spc-gbt-adapter)** | 控制图常数与过程能力指数核对（按 GB/T 4091 的常规控制图常数表核对控制限与 Cp/Cpk 的自洽性，仅提示差异，不作出定性结论） |  |
| **[dsh-talk](https://github.com/PerryLink/dsh-talk)** | Voice-first session loop for DeepSeek Harness: talk to it, hear it answer. |  |
| **[dsh-team-rooms](https://github.com/PerryLink/dsh-team-rooms)** | Cross-session team rooms: shared message bus, task board and timeline | 🚫 RETIRADO — ver o README do repositório |
| **[dsh-tender-extract](https://github.com/PerryLink/dsh-tender-extract)** | 招标文件条款摘录核对（按出处与原文逐字核对摘录完整性，仅提示差异，不作出定性结论） |  |
| **[dsh-tender-matrix](https://github.com/PerryLink/dsh-tender-matrix)** | 评标因素评分矩阵核对（按分值上限与合计核对矩阵自洽，仅提示差异，不作出定性结论） |  |
| **[dsh-test-drive](https://github.com/PerryLink/dsh-test-drive)** | Isolated install-and-smoke test drives for DeepSeek Harness plugins. |  |
| **[dsh-ticktick](https://github.com/PerryLink/dsh-ticktick)** | TickTick/Dida365 task bridge: session-header panel + 11 tools |  |
| **[dsh-translate](https://github.com/PerryLink/dsh-translate)** | Vendor parameter translation and deterministic JSON repair for DeepSeek Harness. |  |
| **[dsh-warranty-calc](https://github.com/PerryLink/dsh-warranty-calc)** | 质保期与索赔金额核对（按质保期月数与里程、索赔金额算式核对自洽，仅提示差异，不作出定性结论） |  |

</details>

</details>

</details>