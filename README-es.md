<div align="center">

# ⬆️ dsh-plugin-upgrade-015
- **Canal de la tienda 1024**: ejecuta `npm i -g dsh1024` una vez y luego `dsh1024 plugin --profile web add dsh-plugin-upgrade-015` (cuenta para el ranking de instalaciones de [deepseek1024.com](https://deepseek1024.com)).
[![Gitee](https://img.shields.io/badge/Gitee-mirror-c71d23?logo=gitee)](https://gitee.com/perrylink/dsh-plugin-upgrade-015)
[![dshfind](https://dshfind.com/api/badge/PerryLink/dsh-plugin-upgrade-015?metric=downloads&lang=es)](https://dshfind.com/es/plugins/PerryLink/dsh-plugin-upgrade-015?ref=badge)

**Habilidad de actualización de plugins para DeepSeek Harness, fusionada y con versión bloqueada — `0.1.3-alpha.1` → `0.1.5-rc.1`, llevada como dos tramos cerrados.**

*Tramo A `0.1.3-alpha.1` → `0.1.5-alpha.1`, tramo B `0.1.5-alpha.1` → `0.1.5-rc.1`: una tarjeta de corredor más un escáner de costuras sin dependencias sobre el catálogo fusionado de 20 costuras, para que una mitad de cliente que dejó de montarse en silencio nunca se confunda con «typecheck en verde».*

> **Repositorio oficial.** Este es el único repositorio oficial de dsh-plugin-upgrade-015, mantenido por PerryLink. Sustituye a los dos paquetes con versión bloqueada `dsh-plugin-upgrade` (tramo A) y `dsh-plugin-upgrade-rc1` (tramo B). Los repositorios con el mismo nombre en otras cuentas no están afiliados.

[![License](https://img.shields.io/badge/license-Apache%202.0-blue.svg)](LICENSE)
[![DSH plugin](https://img.shields.io/badge/dsh--plugin-✅-green)](https://github.com/topics/dsh-plugin)
[![dsh-doctor](https://raw.githubusercontent.com/PerryLink/dsh-plugin-doctor/main/badges/PerryLink__dsh-plugin-upgrade-015.svg)](https://github.com/PerryLink/dsh-plugin-doctor#verified-徽章)
[![Node](https://img.shields.io/badge/node-%5E22.19%20%7C%7C%20%3E%3D24-brightgreen.svg)](#)
[![CI](https://img.shields.io/github/actions/workflow/status/PerryLink/dsh-plugin-upgrade-015/ci.yml?branch=main&label=CI)](https://github.com/PerryLink/dsh-plugin-upgrade-015/actions)
[![Version](https://img.shields.io/github/v/tag/PerryLink/dsh-plugin-upgrade-015?label=version)](https://github.com/PerryLink/dsh-plugin-upgrade-015/releases)
[![npm version](https://img.shields.io/npm/v/dsh-plugin-upgrade-015)](https://www.npmjs.com/package/dsh-plugin-upgrade-015)
[![npm downloads](https://img.shields.io/npm/dm/dsh-plugin-upgrade-015)](https://www.npmjs.com/package/dsh-plugin-upgrade-015)

[English](README.md) · [简体中文](README-zh.md) · [Español](README-es.md) · [Português](README-pt.md) · [हिन्दी](README-hi.md)

</div>

---

## Compatibilidad

| Superficie | Estado |
|---|---|
| Harness | DeepSeek Harness `0.1.5-rc.1` (tag `dsh-v0.1.7-alpha.2` = `183f08e9c6dd`; relevo tramo A→B `dsh-v0.1.7-alpha.2` = `5dda764ed3aa`; inicio del corredor `0.1.3-alpha.1`). Banda de peers `@deepseek-ai/dsh-skill >=0.1.2-rc.1 <0.2.0 \|\| >=0.1.5-alpha.1 <0.2.0`, `@deepseek-ai/cordis ^4.0.2`, `@deepseek-ai/schemastery ^3.18.2`. |
| Node | `^22.19.0 \|\| >=24.0.0` |
| Plataformas | Donde corra Node; el escáner solo usa el sistema de archivos y es neutral respecto a la plataforma |
| Modelo | Modelos solo de texto totalmente soportados; la habilidad es un Markdown, sin requisitos de herramientas ni visión |
| Alcance | **Dos tramos cerrados, un solo lapso**: tramo A `0.1.3-alpha.1` → `0.1.5-alpha.1` más tramo B `0.1.5-alpha.1` → `0.1.5-rc.1`. Un corredor nunca se ensancha: un salto posterior a `0.1.5-rc.1` es un paquete nuevo. |
| Tramos | Ambos tramos viven en este paquete: el tramo A conserva las costuras `S1`–`S10` + `M1`, el tramo B conserva `C1`, `C2`, `C4`, `C5`, `H1`–`H4`, `P1` — cada uno con su propia evidencia, sección de tarjeta, fixtures y ruta de reversión. No hay paquete hermano que instalar. |
| `C3` | Retirada: la tarjeta del tramo B escribía como `C3` el falso verde de la línea de tipos obsoleta, que es el mismo defecto que el `M1` del tramo A. La fusión queda registrada en la tarjeta; `--seams C3` no coincide con nada. |
| Paquete anterior | No montes el retirado `dsh-plugin-upgrade` en el mismo perfil: ambos registran la skill `plugin-upgrade-015`, así que el segundo montaje colisiona con ese nombre. Ese paquete está obsoleto en npm y su repositorio se retiró; este paquete sustituye sus dos tramos. |

## Lo que obtienes

Dos mitades, un solo catálogo de costuras:

- **Una habilidad de agente incluida (`plugin-upgrade-015`)** — la tarjeta del corredor fusionado y un bucle de arreglar-y-verificar. El cuerpo primero enruta a quien la llama al tramo que corresponde a su banda de peers; el modelo la carga solo cuando una tarea la necesita de verdad, y el paquete no aporta ningún párrafo al prompt del sistema ni registra herramientas.
- **Una CLI sin dependencias (`dsh-plugin-upgrade-015-scan`)** — informa hechos `file:line` de las veinte costuras fusionadas (`S3`, `S8`, `S9`, `M1`, `S4`, `S5`, `S6`, `S7`, `S2`, `S1`, `S10`, `C1`, `C2`, `P1`, `C4`, `C5`, `H1`, `H2`, `H4`, `H3`) releídas de los rangos de tags del harness el 2026-09-09 (tramo A) y el 2026-09-10 (tramo B). Sale con `1` ante cualquier hallazgo de severidad error, así que entra directo en CI.

El objetivo es el modo de fallo que este corredor existe para matar: **la rotura de este lapso es mayormente silenciosa, y lo es por ambos extremos.** La línea de tipos puede estar obsoleta, así que el repo compila contra el **catálogo antiguo** (costura `M1`), y el slot de cliente desnudo `conversation` se eliminó sin alias mientras `ctx.slots.inject()` solo ejecuta su callback cuando la declaración existe: una mitad de cliente que aún lo apunta deja de montarse sin error, sin línea de log y sin build fallido (costura `C1`). Tres clases de rotura sobreviven a `typecheck` + `test`:

1. la puerta local compila una línea de tipos obsoleta — un alias `paths` antiguo, o tipos de dev/test fijados en `0.1.5-alpha.*` (costura `M1`);
2. un escritor de logs omite el campo `stream` obligatorio de V3, así que la sesión se importa y luego se niega a reanudarse (costura `S3`);
3. las pruebas están simuladas contra la forma antigua, así que pasan mientras el host descarta tu contribución (costura `C1`).

Medición honesta: el barrido del espacio de trabajo del tramo B encontró que las mitades de cliente de la familia usan solo **8** claves de slot, y las 8 sobreviven en rc.1 — para ellas la rotura de rc.1 es **latente, no real**. Los plugins de cliente de terceros que apuntaban a la clave desnuda `conversation` son los que se rompen, y lo hacen en silencio. El barrido del tramo A encontró la textura opuesta: 40 repos, 11 de ellos dieron con `M1`, y arreglar la ruta obsoleta destapó errores reales de TypeScript en 3 repos que antes estaban «en verde».

## Inicio rápido

```sh
# 1. instala el bundle en tu perfil
dsh plugin --profile web add dsh-plugin-upgrade-015

# 2. verifica que la fila se montó
dsh --profile web --dump-config | grep -A3 'id: dsh-plugin-upgrade-015'

# 3. escanea el plugin que vas a actualizar
npx dsh-plugin-upgrade-015-scan --repo ../my-plugin
```

Luego pide al agente que use la habilidad `plugin-upgrade-015`, o lleva el bucle tú mismo con la tarjeta en
`skills/plugin-upgrade-015/references/v0.1.3-alpha.1-to-v0.1.5-rc.1.md` (el tramo A es §1, el tramo B es §2, el índice de costuras fusionado es §3).

## Instalación y desinstalación

```sh
dsh plugin --profile web add dsh-plugin-upgrade-015            # desde npm
dsh plugin --profile web add "github:PerryLink/dsh-plugin-upgrade-015#main"   # desde el código
dsh plugin --profile web remove dsh-plugin-upgrade-015         # desinstalar (reversible)
```

Instalar el bundle solo registra una habilidad; quitar la fila quita la habilidad. La CLI es un destino `npx` normal y no necesita perfil.

## Configuración

Cada clave es opcional y vive en el patch del perfil:

| Clave | Por defecto | Significado |
|---|---|---|
| `enabled` | `true` | Registra la habilidad incluida. Pon `false` para mantener la dependencia montada pero en silencio. |
| `skillName` | `plugin-upgrade-015` | Directorio bajo `skillsRoot` que se registra, y el nombre que aparece en el catálogo. |
| `skillsRoot` | el `./skills` del propio paquete | Dónde vive `<skillName>/SKILL.md`. Apúntalo a tu propia tarjeta para reutilizar la infraestructura. |
| `userInvocable` | `true` | Si una persona puede invocar la habilidad por nombre además del modelo. |

```yaml
- insert:
    - id: dsh-plugin-upgrade-015
      name: dsh-plugin-upgrade-015
      config:
        skillName: plugin-upgrade-015
```

El plugin monta de forma ruidosa: un `SKILL.md` ausente, un cuerpo vacío o un frontmatter sin `name` hacen fallar el montaje en lugar de registrar una habilidad vacía.

## Superficies

**Habilidad** — `plugin-upgrade-015` (invocable por el modelo y por personas por defecto). Cuerpo: la tabla de enrutado por tramo, las 8 reglas duras y el bucle de 6 pasos. Referencias: la tarjeta del corredor fusionado. Scripts: el detector, dentro del directorio de la habilidad para que las rutas relativas resuelvan.

**CLI** — `dsh-plugin-upgrade-015-scan`:

```sh
dsh-plugin-upgrade-015-scan [--repo <path>] [--json <out.json>] [--seams S3,C1,P1] [--quiet]
```

| Bandera | Significado |
|---|---|
| `--repo <path>` | Repositorio a escanear (por defecto: el directorio actual). |
| `--json <out.json>` | También escribe el informe legible por máquina (`repo`, `scannedAt`, `files`, `hits[]`, `bySeam`). |
| `--seams S3,C1,P1` | Restringe a costuras concretas del catálogo fusionado. |
| `--quiet` | Suprime la salida humana (combínala con `--json`). |

Códigos de salida: `0` sin hallazgos de severidad error · `1` al menos un hallazgo de severidad error · `2` uso o fallo del escaneo. Un escaneo limpio es necesario pero no suficiente: el criterio de salida es un smoke real en el host, más un ida y vuelta de reanudación para los escritores de logs (tramo A) y una aserción en un navegador real para la mitad de cliente (tramo B).

## Las veinte costuras

El orden sigue el catálogo de `lib/scan.mjs` (primero el tramo A, luego el tramo B), que es también el orden al que `test/card.test.mjs` fija la tarjeta.

| Id | Severidad | Qué cambió en el camino a `0.1.5-rc.1` |
|---|---|---|
| `S3` | error | `assistant/message` ganó un campo `stream` obligatorio (formato de sesión V3): un log escrito sin él se importa con éxito y luego se niega a reanudarse (`Session.fromRestore` lanza `invalid settlement fields`). |
| `S8` | error | `SessionHandle.read()` devuelve `SessionHandleReadResult` (`{ eventState, events }`) en lugar del array de eventos; las operaciones de array deben desenvolver `.events`. |
| `S9` | error | La configuración de `SystemPrompt` renombró `persona` → `personaPrefix` / `personaSuffix`. Sustituirlo por `includeHarnessIdentity: false` **no** es equivalente: elimina el bloque de identidad del harness. |
| `M1` | error | La puerta local compila una línea de tipos obsoleta: tipos de dev/test fijados en `0.1.5-alpha.*`, o un alias `paths` de `tsconfig` que resuelve a un directorio de checkout inexistente, hacen que TypeScript vuelva en silencio a los tipos publicados. Puerta en verde, regla equivocada. |
| `S4` | error | `tool/code-dispatch` pasó a llamarse `tool/ptc-dispatch`; la etiqueta antigua ya no se reconoce en las sesiones V3. |
| `S5` | error | `ctx.agent` se eliminó: quien llama debe pasar el Agent explícitamente (por ejemplo, el segundo parámetro de `setup(agentCtx, agent)`). |
| `S6` | error | `Inbox` es una interfaz de tipo, no una clase construible; los fixtures usan la forma oficial no soportada y el código en tiempo de ejecución lee `agent.inbox`. |
| `S7` | warn | `SubprocessHandle.pid` se eliminó (solo queda `SubprocessTerminalHandle.pid`); quita el campo de los fixtures de prueba. |
| `S2` | warn | `EpochHeader.system` se eliminó: el prompt del sistema es ahora el `system/message` del nodo 0 de la superficie. |
| `S1` | warn | Formato de sesión V3 y nombres de log con sufijo de generación: la generación actual es `session.v3.jsonl.zstd`, así que los scripts que fijan `session.jsonl.zstd` fallan en silencio. |
| `S10` | warn | Los eventos de sesión escritos por un plugin deben pasar por la puerta de adaptación fail-closed del host: `Session.append` no tiene canal de escritura `ignorable`, así que un append incondicional puede dejar una sesión ilegible. |
| `C1` | error | El slot de cliente desnudo `conversation` se eliminó y se sustituyó por `main` + `main.conversation`, **sin alias**. `ctx.slots.inject()` solo se dispara si la declaración existe, así que un plugin que lo apunta deja de montarse **en silencio**. |
| `C2` | error | `@deepseek-ai/dsh-client-ui-sidebar-textpreview` pasó a llamarse `…-sidebar-documentpreview`; el nombre antiguo desapareció y no hay paquete shim. |
| `P1` | error | La banda de peers debe conservar su segundo segmento: `>=0.1.2-rc.1 <0.2.0` por sí solo **rechaza** `0.1.5-rc.1` bajo la regla prerelease-tuple de npm semver (medido `false` en semver 7.8.5). |
| `C4` | warn | rc.1 añadió un modelo de panel principal global (`main`, `sidebar.panellist`, `ctx.layout.selectPanel(MainPanelId \| null)`) y añadió la prop estándar `usePanelInfo` a casi todos los slots. |
| `C5` | warn | La vista previa de documentos se movió al slot con clave `sidebar.right.tab.document` (`DocumentContent`); `sidebar.right.pane.tab` sobrevive pero su entrada padre pasó a ser `rightbar.session`. |
| `H1` | warn | `KNOWN_SESSION_EVENT_TYPES` ganó `deliverables/presented` y `subagent/catalog`: el vocabulario fail-closed creció. |
| `H2` | warn | La fila de la nueva herramienta `present` ocupa la clave `'present'` de `tool.call.toolview`, que en alpha.1 estaba libre. |
| `H4` | info | El catálogo asesor por defecto del adaptador DeepSeek ahora encabeza con `deepseek-flash` (DeepSeek-V41-Flash). |
| `H3` | info | Nuevas capacidades opcionales: `ctx.sessionFeedback`, `ctx.layout.beginNavigation()`, `ctx.workspaces.openSession()` / `openWorkspace()` / `forkSession()`. Listadas en la tarjeta; deliberadamente sin detección automática. |

`S7`, `S2`, `S1`, `S10`, `C4`, `C5`, `H1`, `H2` y `H4` son deliberadamente asesorables: tienen coincidencias legítimas (un repo que ya usa la API nueva, una instantánea de documentación, la tabla de ids de modelo de un plugin, un `ChildProcess.pid` de Node), así que el escáner las reporta como pistas para revisión manual, no como fallos. `M1` y `P1` son comprobaciones **estructurales** — resuelven `package.json` y `tsconfig*.json` en lugar de coincidir texto — y `H3` es **solo de tarjeta**: documentada, con paridad de ids comprobada y deliberadamente sin detector (`CARD_ONLY = ['H3']`).

## Lo que esto no cubre

- **Un salto posterior a `0.1.5-rc.1`.** El lapso fusionado termina en rc.1 por construcción: el salto del harness `0.1.5-rc.1` → `0.1.5-rc.2` no añadió ninguna costura de cara a los plugins (el pin de dev/test de este propio paquete corre ahora sobre la línea `0.1.7-alpha.2`, de modo que el catálogo queda verificado contra los tipos publicados más recientes; la sonda del workflow compat sigue anclada en `0.1.6-alpha.2`). Cualquier cosa que añada una costura más adelante es un **paquete nuevo**: una tarjeta que deriva es peor que ninguna tarjeta.
- **El salto `0.1.1` → `0.1.2`.** Usa la habilidad de convergencia de la comunidad.
- **Repetir entre tramos.** El tramo A posee las costuras del formato de sesión (`assistant/message.stream`, `SessionHandleReadResult`, `EpochHeader.system`, `ctx.agent`, `Inbox`, `SystemPrompt.persona`, la generación de log V3) y el tramo B no las repite: todo el diff de `packages/core/session/src` en el rango del tramo B son dos literales de tipo de evento añadidos y una línea de comentario. La sección de tarjeta de cada tramo conserva su propia declaración de alcance.
- **La ruta de actualización del usuario de DSH.** Este paquete actualiza *código fuente de plugins*, no la instalación del harness de un usuario.
- **Tokens de tema.** `docs/web-styling.md` no tiene ningún cambio en el rango del tramo B.
- **Prueba.** Un escaneo limpio es una hipótesis. El criterio de salida es un smoke real en el host (`DSH_HOME` temporal, CLI objetivo, `plugin add <tarball>`, `--dump-config`) más un ida y vuelta de reanudación para los escritores de logs de sesión (tramo A) y una aserción en un navegador real para cada hallazgo del lado cliente (tramo B).

## Límites de seguridad

- **Escaneo de solo lectura.** La CLI nunca escribe dentro del repositorio escaneado; `--json` escribe solo en la ruta que indiques.
- **Sin red, sin shell.** El escáner no importa nada fuera de la biblioteca estándar de Node y nunca lanza un proceso.
- **Sin secretos.** Nada en el paquete lee credenciales, tokens de entorno ni datos de sesión.
- **Receta de smoke en sandbox.** La comprobación de host real de la tarjeta usa un `DSH_HOME` de `mkdtemp`; nunca toca tu `~/.dsh` real.

## Desarrollo

```sh
npm install                        # o: pnpm install (el repo incluye pnpm-lock.yaml)
npm test                           # node --test: escáner, paridad tarjeta<->catálogo, Cordis + SkillRegistry reales
npm run verify:self-contained      # cada import resuelve dentro del paquete
npm run verify:artifacts           # el tarball lleva la habilidad, la CLI y el patch, y excluye las pruebas
npm run check:readmes              # consistencia de los README en cinco idiomas
npm pack
```

El escáner tiene un par de fixtures sintéticos **por tramo**: `fixtures/leg-a-bad-repo` (las costuras de sesión/configuración del tramo A, con todas las costuras de error presentes a propósito) junto con `fixtures/leg-a-good-repo` (adaptado), y `fixtures/bad-repo` (las costuras de slot de cliente del tramo B) junto con `fixtures/good-repo` (adaptado) — más un negativo en vivo sobre un repositorio de la familia ya fijado a `0.1.5-rc.1`, de modo que una regresión del catálogo falla en esta suite y no en un usuario aguas abajo. `test/card.test.mjs` afirma que el índice de la tarjeta fusionada y `lib/scan.mjs` nombran **exactamente** los mismos veinte ids de costura con las mismas severidades, y que `CARD_ONLY` es exactamente `['H3']`: la regla de vinculación de evidencia como puerta de máquina.

## Temas

`dsh`, `dsh-plugin`, `deepseek-harness`, `deepseek`, `cordis`, `plugin-upgrade`, `migration`, `skill`, `version-card`, `scanner`, `client-slots` (reflejan las `keywords` de `package.json`; `dsh-plugin` es el canal de visibilidad del ecosistema).

## Licencia

Apache-2.0 — consulta [LICENSE](LICENSE). Las dependencias de instalación y sus licencias están en [THIRD_PARTY_NOTICES.md](THIRD_PARTY_NOTICES.md); no se incluye nada empaquetado.


## PerryLink DSH Plugin Family

This project is one of the **45 DeepSeek Harness plugins** maintained by [PerryLink](https://github.com/PerryLink). If this one helps you, the others likely will too:

| Plugin | One-liner |
|---|---|
| **[dsh-auto-review](https://github.com/PerryLink/dsh-auto-review)** | Second-model auto-review on the approval chain, fail-closed by default | |
| **[dsh-autotier](https://github.com/PerryLink/dsh-autotier)** | Automatic strong/cheap model-tier routing with deterministic risk guards and a `/tier` command | |
| **[dsh-background-agents](https://github.com/PerryLink/dsh-background-agents)** | Durable background child agents with a Web UI sidebar, messaging and interrupt | |
| **[dsh-budget](https://github.com/PerryLink/dsh-budget)** | Cost governance for DeepSeek Harness: budgets, carbon, and latency in one panel. | |
| **[dsh-catalog](https://github.com/PerryLink/dsh-catalog)** | DSH Desktop Market standard catalog source for the PerryLink family | |
| **[dsh-cert-mcp](https://github.com/PerryLink/dsh-cert-mcp)** | Read-only MCP server exposing the certification registry: grades, snapshots and five-dimension evidence | |
| **[dsh-checkpoint-rewind](https://github.com/PerryLink/dsh-checkpoint-rewind)** | Claude Code /rewind-equivalent: snapshots, session forks, one-shot restore | |
| **[dsh-claude-move](https://github.com/PerryLink/dsh-claude-move)** | Migrate Claude Code sessions, memory, skills and CLAUDE.md into DSH | |
| **[dsh-click](https://github.com/PerryLink/dsh-click)** | Cross-platform native desktop control for DeepSeek Harness — Windows first. | |
| **[dsh-composer-history](https://github.com/PerryLink/dsh-composer-history)** | Terminal-style input history for the web composer: arrows, Ctrl+R search | |
| **[dsh-data-quality](https://github.com/PerryLink/dsh-data-quality)** | Dataset quality checks and citation cross-checks (the optional numeric bridge consumed here) | |
| **[dsh-defend](https://github.com/PerryLink/dsh-defend)** | Prompt-injection, jailbreak, and secret-leak defense for DeepSeek Harness. | |
| **[dsh-doublecheck](https://github.com/PerryLink/dsh-doublecheck)** | Engineering-discipline guard: requirements grill, test gates, adversary review | |
| **[dsh-draw](https://github.com/PerryLink/dsh-draw)** | Unified static-image generation routing for DeepSeek Harness. | |
| **[dsh-fast](https://github.com/PerryLink/dsh-fast)** | Read-only performance diagnostics for DeepSeek Harness. | |
| **[dsh-fund-research](https://github.com/PerryLink/dsh-fund-research)** | Deterministic research reports for Chinese public mutual funds | |
| **[dsh-github](https://github.com/PerryLink/dsh-github)** | GitHub PR/issues integration for DSH, every write gated by approval | |
| **[dsh-industry-research](https://github.com/PerryLink/dsh-industry-research)** | Industry research orchestration that seals its deliverables through this plugin's `ctx.researchReport.assemble` | |
| **[dsh-laya](https://github.com/PerryLink/dsh-laya)** | Laya typed decisions (`noul`/`choice`/`score`) as a first-class Cordis service and model-visible tools | |
| **[dsh-library](https://github.com/PerryLink/dsh-library)** | Local document knowledge base for DeepSeek Harness. | |
| **[dsh-local-ai](https://github.com/PerryLink/dsh-local-ai)** | Local-model (Ollama) integration for DeepSeek Harness. | |
| **[dsh-lsp-actions](https://github.com/PerryLink/dsh-lsp-actions)** | LSP diagnostics, formatting, completion, code actions and rename over language servers | |
| **[dsh-mask](https://github.com/PerryLink/dsh-mask)** | PII masking middleware: anonymize at the model boundary, restore at the display layer | |
| **[dsh-mcp-panel](https://github.com/PerryLink/dsh-mcp-panel)** | Read-only MCP runtime panel: /mcp command + Settings tab with status, tools and errors | |
| **[dsh-memento](https://github.com/PerryLink/dsh-memento)** | Approval-gated cross-session memory: ctx.memory seam + SQLite + memory tool | |
| **[dsh-observe](https://github.com/PerryLink/dsh-observe)** | OpenTelemetry and Langfuse observability exporter for DeepSeek Harness. | |
| **[dsh-output-styles](https://github.com/PerryLink/dsh-output-styles)** | Claude Code outputStyles-equivalent runtime style switching | |
| **[dsh-permission-rules](https://github.com/PerryLink/dsh-permission-rules)** | Claude Code-style declarative allow/deny/ask permission rules with audit | |
| **[dsh-plugin-certification](https://github.com/PerryLink/dsh-plugin-certification)** | Community certification registry with repro-checkable grades and badges | |
| **[dsh-plugin-doctor](https://github.com/PerryLink/dsh-plugin-doctor)** | Zero-dependency static + sandbox smoke detector for DSH plugins | |
| **[dsh-plugin-guide](https://github.com/PerryLink/dsh-plugin-guide)** | Plugin-development knowledge base as an on-demand agent skill | |
| **[dsh-plugin-kit](https://github.com/PerryLink/dsh-plugin-kit)** | Shared zero-runtime-dependency toolkit for the PerryLink DSH plugins | |
| **[dsh-plugin-upgrade](https://github.com/PerryLink/dsh-plugin-upgrade)** | One-package, one-corridor-index plugin upgrade skill: routes a repository to the matching closed corridor card | |
| **[dsh-plugin-upgrade-015](https://github.com/PerryLink/dsh-plugin-upgrade-015)** | Merged `0.1.3-alpha.1` → `0.1.5-rc.1` upgrade corridor card plus a zero-dependency seam scanner | |
| **[dsh-reach](https://github.com/PerryLink/dsh-reach)** | Multi-channel approval/question bridge: WeChat/Telegram/Feishu, session console | |
| **[dsh-research-report](https://github.com/PerryLink/dsh-research-report)** | Verifiable research-report engine: content-addressed evidence ledger and sealed versions | |
| **[dsh-score](https://github.com/PerryLink/dsh-score)** | Multi-dimensional quality scoring for DeepSeek Harness plugins. | |
| **[dsh-session-pin](https://github.com/PerryLink/dsh-session-pin)** | Pin sessions in the Web sidebar with durable ordering | |
| **[dsh-session-sync](https://github.com/PerryLink/dsh-session-sync)** | Cross-device session sync for DeepSeek Harness — a dedicated git mirror of your session store. | |
| **[dsh-skill-pack-security](https://github.com/PerryLink/dsh-skill-pack-security)** | Security-audit skill pack: secret scan, dependency and supply-chain review | |
| **[dsh-talk](https://github.com/PerryLink/dsh-talk)** | Voice-first session loop for DeepSeek Harness: talk to it, hear it answer. | |
| **[dsh-team-rooms](https://github.com/PerryLink/dsh-team-rooms)** | Cross-session team rooms: shared message bus, task board and timeline | |
| **[dsh-test-drive](https://github.com/PerryLink/dsh-test-drive)** | Isolated install-and-smoke test drives for DeepSeek Harness plugins. | |
| **[dsh-ticktick](https://github.com/PerryLink/dsh-ticktick)** | TickTick/Dida365 task bridge: session-header panel + 11 tools | |
| **[dsh-translate](https://github.com/PerryLink/dsh-translate)** | Vendor parameter translation and deterministic JSON repair for DeepSeek Harness. | |
