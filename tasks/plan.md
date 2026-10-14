# Plan: mobile-control and mcp-access

**Status:** Active — dopo il conflitto di coordinamento, l'ultima decisione del Product Owner conferma questa sessione OMP come unico coordinatore Matt Pocock/RFC-0001. Gli esiti Osmani precedenti restano storia accettata. Il rilascio operativo è approvato soltanto dopo review sullo SHA esatto e check applicabili verdi.
**Mission:** [Agent OS35](https://github.com/skunklabs-uk/agent-os/issues/35), coordinatore corrente e provider bound sul WSL originale NOVBSCWOLaulMaU.
**Coordinator:** omp-current-session
**Coordinator session:** 01a13b77-fd88-778e-97cc-aadb754902d5
**Provider role:** observer
**Provider session:** 01a131c7-ecba-7000-a4fb-ff906f642f4f
**Permitted scope:** mobile-control/mcp-access-readiness-and-port
**Permitted commands:** observe
**Authority:** [mobile-control](../SPEC-mobile-control.md), [mcp-access](../SPEC-mcp-access.md) and the [shared provider contract](../SPEC-team-execution.md#shared-remote-consumer-contract), explicitly approved on 2026-10-12 at `f55c2b7838104770766825e57b68129b019e951e`. Team-execution is accepted and delivered by [PR51](https://github.com/skunklabs-uk/agent-os/pull/51), merge `95528e6c0013f067702496902c40051fba973e48`.
**Method:** skill originali Matt Pocock a `24fe0ef7737efae15c87225755e9f6f5965e4888`, scelte esplicitamente per il lavoro residuo. Riusare specifiche, ticket e seam accettati; non ripetere acceptance dei pilot. Le decisioni tecniche seguono la delega del Product Owner, senza inventare invocazioni letterali di skill.
**Phase:** P1 e integrazione qualificati localmente; trial read-only revisionato; custodia, full plan, rilascio WSL e acceptance personali da completare
**Tracking:** GitHub issue35 and its native sub-issues; no tasks/todo.md or second ledger. [Task52](https://github.com/skunklabs-uk/agent-os/issues/52) owns readiness and the complete local port checkpoint after the reviewed component increments53–58. Current scope and outcomes appear below; recheck duplicates before any necessary new task. The former team-execution plan is Archived history and is not overwritten.

## Prima successione OMP/Pocock — 2026-10-14, storia

La richiesta diretta del PO di riprendere l'handoff conferma questa nuova
sessione come unico coordinatore. Sostituisce il coordinatore uscente
`01a136e1-3183-72bb-aeca-d82f1bc60b6c`, non il provider observer.
I checkout esistenti restano intatti; i bundle verificati sono recuperati in
`/workspaces/mission35-omp-web` e `/workspaces/mission35-agent-os`.
Il remoto documentale `449feab` e la PR app `f861bb8` conservano lavoro
concorrente Codex: nessun overwrite, force-push o GO ereditato.
Le dichiarazioni concorrenti di ownership non prevalgono sulla richiesta
diretta corrente. Primo lavoro: P1 bootstrap su app `91319e0`, risposta e
interruzione indipendenti dall'avvio pendente, con ricevuta originale
consultabile e senza replay. Seam già autorizzati dall'handoff: commander
pubblico e pannello Next reale con domanda nativa `session_start`.
Nessun trial modello, apply o rilascio eseguito nella ripresa.

## Ripresa sul WSL originale — coordinatore entrante

La nuova richiesta diretta del PO di riprendere l'handoff assegna il
coordinamento esclusivo a `01a13b77-fd88-778e-97cc-aadb754902d5`,
successore di `01a139d2-93a6-704a-a1cc-570907f479a9`.
Il provider resta `01a131c7-ecba-7000-a4fb-ff906f642f4f`,
`observer/observe`; successione documentale, non promozione executor.
Host e utente osservati direttamente: NOVBSCWOLaulMaU/iingenito.
L'handoff richiesto sotto `/workspaces` non è montato in questo contesto:
la copia originale e i sei allegati in
`/tmp/mission35-developer-workspace-handoff-745kkjbp` superano SHA256SUMS.
Recuperati checkout nuovi sotto `/home/iingenito/tmp/mission35-resume-`:
`omp-web`, `agent-os` e `homelab`. Checkout e processi preesistenti
restano preservati, senza reset, clean, force-push o arresti.

Le fonti successive all'handoff prevalgono sui suoi pending: P1
`16faf8d` e integrazione `8fc6e67` sono qualificati nei perimetri sotto;
manifest delle prove recuperate verificati rispettivamente38/38 e30/30.
Il successivo report originale `7b939c3` registra il trial già eseguito:
non si rilancia un modello né si interpreta remaining16 come allowance.
La review indipendente della risposta finale e dei report correlati
qualifica soltanto la lettura pertinente Pocock sotto authority `e87c349`,
con il limite della fonte coordinatore arretrata esplicitamente rilevato.
Non qualifica lo stato runtime successore, i pending, il rilascio o l'MVP.
Il Plan successore deve essere consumabile dal parser nativo nel CWD
originale mediante fast-forward esplicito; nessun cambio ID/CWD/auth.



## Outcome and scope

Deliver two real user journeys: control the host mission from the user's mobile browser, and delegate/inspect/interrupt it through the user's actual ChatGPT MCP surface. Both use the same provider identity, state and decisions. Acceptance is per module, then reconciled for the MVP; accepted Waypoint/Pocock proofs are not repeated. No deployment, IWANT merge, runtime replacement, new infrastructure or spending is authorized by this plan's creation or approval.

The plan deliberately qualifies existing capabilities before selecting an implementation. Unknown access or source compatibility is not converted into a success claim. Later packages are conditional paths, not permission to build an unspecified adapter. If qualification establishes that an extension is necessary, amend this plan with the exact owner repository, base, files, commands, costs and necessity evidence before approving that implementation's Tasks.

## Evidence and implementation choices

| Observation / source | Planning consequence |
|---|---|
| Accepted team-execution provides native OMP18.8.7, original skill pins, real isolated workers and independent review; [outcome](team-execution-evidence.md). | KEEP that provider baseline. No new coordinator, workflow router, fixed team, state database or replay of accepted proofs. |
| [Collab documentation atb07a1c1](https://github.com/can1357/oh-my-pi/blob/b07a1c146d0d12cfc855a2c65d52f892ef319040/docs/collab.md) describes browser sharing and guest intervention but host-only commands/session transitions. | Start mobile qualification here; joining an existing session cannot by itself satisfy remote start/resume. Preserve the gap rather than accepting a desktop-assisted substitute. |
| [omp-web package at0acce624](https://github.com/ddallabenetta/omp-web/blob/0acce6240b27eb7d44d5c9b78187bd95e01270f8/package.json) declares OMP dependencies~18.1.17; compatibility with18.8.7 is unproven. | Compare only if native capability leaves a required gap. Verify compatibility before adoption for mission work; an isolated baseline installation may qualify the candidate under the bounded scope below. Do not downgrade the qualified provider or add a second mission runtime silently. |
| [Official Secure MCP Tunnel documentation](https://developers.openai.com/api/docs/guides/secure-mcp-tunnels?site_locale=en), read2026-10-12, describes an outbound private connection and ChatGPT connection through a workspace-associated tunnel. | Assess this supported transport before proposing public ingress. Account/workspace entitlement, host reachability and actual use are unknown. No tunnel creation, API key, API model call or network change has been authorized. Transport alone supplies no OMP business tools. |
| [Official authentication documentation](https://developers.openai.com/plugins/build/auth), read2026-10-12, describes OAuth-based user authentication and recommends an existing identity provider. | Reuse supported authentication if available; do not invent anonymous write access or custom auth. Verify actual client/account path and candidate tool semantics before choosing integration. |
| User requires mobile device and actual ChatGPT client evidence, both still missing. | Put identity/access qualification first. Desktop emulation and server-only tests cannot close either module. |

For MCP, compare existing supported tools/integrations against the full provider contract before considering a maintained MCP adapter around OMP SDK/RPC. Native RPC is a building block, not proof of an MCP server or account access. If no reusable route covers the gaps, the smallest custom alternative requires the RFC-0001 necessity record and explicit scope approval; it is not selected now. Existing Codex remote facilities may inform the comparison but cannot silently replace the qualified OMP provider or prove OMP-native behavior.

### Focused native-source readiness findings

A separate read-only preparer checked the pinned Collab/RPC sources and the local installed path. The binary exists at `/home/iingenito/.local/share/mise/installs/oh-my-pi/18.8.7/omp`. Subsequent local qualification verified its SHA256 against the official v18.8.7 release checksums: `b87f9835a0acdbb81bbbad8273aa2d999b608a208598421a9584cffeb3139a8a`. This establishes release-asset identity, not a reproducible source-to-binary build. A fresh read-only source archive at b07a1c1 was used for SDK inspection.

At the cited pin, Collab exposes guest observation/intervention/dialogs, but `/resume` and machine commands are host-only and new/resumed sessions change rooms. The old link does not follow the new session. Thus M1 must investigate a supported start/resume route rather than repeatedly proving only joining. The production relay is not distributed for self-hosting; a development stand-in is not a production hosting solution.

[Native RPC at the same pin](https://github.com/can1357/oh-my-pi/blob/b07a1c146d0d12cfc855a2c65d52f892ef319040/docs/rpc.md) supplies session operations, state and interruption over proprietary JSONL stdio, not MCP. A yielded prompt result can precede settled work. `--no-ui` disables the UI extension, but `--mode rpc-ui --no-ui` retains supported tool dialogs; tool approval is separate and fails without the UI extension. Closing stdin disposes the session and pending UI. Any later bridge must prove correct decision handling, settled state and reconnection without a duplicate coordinator or accidental stdin closure. These are observed source constraints, not an adapter implementation proposal.

Read-only inspection commands, with no runtime launch or secret output:

```bash
stat /home/iingenito/.local/share/mise/installs/oh-my-pi/18.8.7/omp
curl --fail --silent --show-error https://raw.githubusercontent.com/can1357/oh-my-pi/b07a1c146d0d12cfc855a2c65d52f892ef319040/docs/collab.md
curl --fail --silent --show-error https://raw.githubusercontent.com/can1357/oh-my-pi/b07a1c146d0d12cfc855a2c65d52f892ef319040/docs/rpc.md
```

Do not log `omp collab link` capability URLs. Registry-listing commands may clean stale metadata and must not be classified as pure filesystem inspection. No such commands were run for this Plan.

## Dependencies, ownership and parallelism

```text
Approved specs + provider contract
  -> P0 shared readiness / ownership
       -> M1 mobile path qualification -> M2 mobile decisions/reconnect
       -> C1 actual-client MCP qualification -> C2 MCP long work/decisions/reconnect
  M2 + C2 (or explicit PO decision on a demonstrated MCP limit)
       -> R independent final review -> D module acceptance and closeout
```

M1 and C1 may run independently after P0; M2 never precedes M1, C2 never precedes C1. A missing MCP permission blocks its dependent path, not mobile qualification. At most two assignments run concurrently; reduce for available resource authority. Coordination/integration is one owner, not a third competing implementation lane. No fixed team.

- **Coordinator:** exclusively owns shared contract, `tasks/plan.md`, capability map, mission35 and serial integration. Provider contract changes are reviewed before consumers rely on them.
- **Mobile specialist:** owns the mobile candidate and its evidence in a separate worktree/check-out if writing. Returns exact base/head, changed files, observed device results and limits; never updates the shared plan.
- **MCP specialist:** owns the separate MCP candidate/evidence under the same rules. No access to other projects solely because a transport supports them.
- **Reviewers:** clean sessions using original Pocock code-review, with separate Standards and Spec axes on the exact integration revision and original requirements. Re-review material corrections only. Application QA and access/security review are responsibilities activated by actual work, not permanent extra agents.

The present Agent OS writer reuses the isolated coordinator worktree. No owner checkout or other worktree is reset, cleaned or cherry-picked. Future executable writers receive explicit owned files and permitted repositories in approved tasks before any launch. One integrator per repository.

## Proposed work packages, not duplicate task records

These packages are the scope and ordering for the next Tasks phase, not issued/approved executable tasks. Each must become a small native task with no more than three acceptance criteria and about five changed files; split any larger implementation only after its actual surface is known.

| Package / size | Result and focused verification | Prerequisites / ownership |
|---|---|---|
| P0 — shared readiness, S | Confirm host identity/availability, exact provider/source pins, one active coordinator and read/write ownership; record actual device/browser and ChatGPT surface/account capability without secrets; identify allowed access, model/cost ceilings and a bounded synthetic mission. Classify each lane READY/BLOCKED with precise next action. | Approved Plan and readiness Task. Coordinator; existing plan/mission plus source inspection. Source discovery remains read-only. The later bounded local RPC/SDK probe below used only disposable lab configuration and isolated processes; it did not expose a service. |
| M1 — mobile start/resume and visibility, S–M | On the actual device, qualify native collab and any source-justified existing alternative against start/resume, correct mission/team visibility and authorization. Record authentic observations including any required host intervention. Return exact uncovered gap if native route fails; no substitute acceptance. | P0 + approved task/runtime/access limits. Mobile owner; initially evidence only, candidate config paths specified before writing. |
| C1 — actual-client MCP delegation, S–M | Verify supported client/account connection and authentication; select an existing integration/transport only after source comparison. On an approved bounded mission, observe delegation/status to the sole coordinator and rejection outside scope. A supported transport with no mission tools is incomplete. | P0 + actual account access + approved task/connection resources. MCP owner. No install, tunnel, ingress or new service before owner authorization; material extension requires amended Plan. |
| M2 — mobile intervention and reconnect, M | Exercise question/approval/rejection, steer/interrupt and disconnect with a pending decision; reconnect and resolve once. Verify touch/keyboard usability, actual execution outcome and stale/duplicate response handling. Trace every mobile acceptance scenario to real evidence. | M1 covered required path + task approval + unchanged approved shared contract. Mobile owner; tests only for new approved logic, no framework by default. |
| C2 — MCP long work and reconnect, M | Exercise a request whose work outlives the initiating call, retrieve the same mission's result, resolve an applicable pending decision and interrupt/reconnect without duplicate work. Distinguish unknown/acknowledged/completed. Trace every MCP acceptance scenario to actual client evidence. | C1 qualified route + task approval. MCP owner; no model/API spending inferred from protocol testing. |
| R — independent exact-head review, S | Reconcile both module criteria against original specs, ownership, source pins and real raw; verify unauthorized/stale decisions do not mutate another mission. Required/Critical findings return to the owning writer; review material corrections on their new head. | M2/C2 outcomes available, or precise accepted product-limit decision. Independent reviewer read-only, coordinator integrates. |
| D — bounded acceptance and closeout, S | Present actual user-device/client results and remaining limits for module acceptance; record MCP include/limit/defer decision if needed, proportional mission retro and durable outcome; archive only completed plans and update all current pointers. Deliver PR/SHA/smoke after any separately authorized merge. | R clear + applicable PO module/delivery approval. Coordinator serial writer. #35 closes only when agreed MVP criteria are met. No deploy or IWANT merge. |

## Checkpoints and executable boundaries

1. **After P0:** coordinator confirms each lane's precise prerequisites and resource authority. No invented device identity, credential migration, pilot allowance reuse or unbounded retry. Missing user input is requested once for the affected lane, with independent preparation continuing.
2. **After M1/C1:** review evidence of the actual route, decide KEEP native/reusable or document the uncovered gap. A materially new implementation, owner repository, dependency, permission or service requires a concrete amended Plan/authority before writing. A source-only negative is not a fabricated runtime failure, and not a unilateral MCP deferral.
3. **After M2/C2:** original scenarios must have actual result/revision/raw pointers. User reports remain attributed to the user; coordinator tests remain coordinator tests. Reviewer receives evidence, not an expected verdict.
4. **Before D:** verify current branch policy, checks and delivery authority on exact heads. Never inherit Waypoint CI/merge delegation for a new module, trigger preview/build/deploy by accident, or rerun paid checks without applicable permission.

Current phase checks, from this repository:

```bash
git status --short
git diff --check
git diff --check origin/main...HEAD
git diff origin/main...HEAD -- SPEC-mobile-control.md SPEC-mcp-access.md SPEC-team-execution.md CAPABILITY-MAP-agent-team.md tasks/plan.md
```

No application build/bootstrap/CI is applicable to this Markdown planning change. Verify relative links and anchors plus source consistency and independent review. Executable readiness tasks must pin the actual installed binary paths, source/config inspection commands and, before any runtime trial, the complete startup/test/cleanup commands for the selected route. Do not treat interactive `/collab` as a shell command or blindly execute upstream tunnel quickstarts. These documentary checks do not execute a provider. The later local qualification below records the runtime processes actually started, separately from source inspection.

For later authorized OMP proofs retain `dev.autoqa: false`, `PI_AUTO_QA=0`, permitted provider/model, isolated workers and automatic patch application disabled. Close stdin only on the previously qualified one-shot noninteractive path; do not apply that startup workaround to a persistent RPC transport, whose stdin must remain owned and open for its intended lifetime. Runtime duration/soft request bounds must not be represented as monetary caps. Determine actual resource authority in the task before use; do not transfer the pilot's budget.

## Resource and prerequisite boundary

- **Already acquired:** specifications and shared contract approval, this planning assignment, accepted provider proof, read-only preparation and real independent documentary review.
- **Current delegated step:** [Task52](https://github.com/skunklabs-uk/agent-os/issues/52), readiness and bounded local qualification. The user selected tablet/browser/ChatGPT outside the LAN. Authentic supplied screenshots show custom MCP, URL/Tunnel options and a tunnel ID text field; actual entitlement and connection remain unverified. No mobile/MCP application implementation or remote operational trial is complete.
- **Before user trials:** actual mobile device/browser and remote network context; actual ChatGPT client/workspace supported setup; operator participation for login/device smoke. Request facts or supported operator actions, never secrets in chat.
- **Before new operational use:** exact candidate, minimal permissions/connectivity, repository owner, startup/shutdown procedure, duration/cost authority and any necessary service/network approval. These are not all assumed to be needed: first reuse what is already present and authorized.
- **Always excluded:** deploy, IWANT merge, production/AWS, unsupported ChatGPT UI automation, routine tool upgrades, reopening unrelated Homelab34, fabricated proofs or duplicate trackers.

## Risks and proportional responses

| Concrete risk | Response |
|---|---|
| Browser joins a session but cannot remotely start/resume it | Fail that scenario explicitly; compare source-supported existing alternatives before any minimal extension. |
| Actual account cannot use the selected MCP route | Preserve the observed constraint, continue mobile, request explicit include/limit/defer decision only with evidence. |
| Native guest dialog lacks required scoped-decision behavior | Test the actual provider semantics, reuse existing request identity/rejection; custom controls need demonstrated gap and scope approval. |
| A connection expires or changes mission while a decision is pending | Verify target identity and stale response behavior end-to-end; do not infer from UI reappearance. |
| Persistent host or exposure is needed | State the minimum owner change and operational cost, obtain authority before provisioning; do not turn a local proof into an unsolicited hosting project. |
| Several small adapters become a new platform | Review total components and operating burden under RFC-0001; prefer KEEP native or DELETE/REPLACE unnecessary machinery. |

## Readiness snapshot — Task52, 2026-10-12

- **Host PASS:** `hostname` returns NOVBSCWOLaulMaU. The coordinator owns only the clean isolated Agent OS worktree/branch before this status update; no owner checkout has been changed. `/proc` inspection of process name, executable path and cwd (not arguments/secrets) found active OMP executables under the18.10.1 installation and other-project workloads. The18.8.7 binary remains installed. This does not requalify18.10.1 or prove its exact binary/source identity; do not modify those processes or reuse their sessions.
- **Mobile BLOCKED for execution:** the user selected a tablet browser outside the host LAN; exact platform/browser and the authorized remote route remain unverified. Pinned omp-web has real browser session/dialog primitives but creates its own SDK host and has process-local locks. Against18.8.7 it imports absent `thinking`, `modes/theme/theme` and `config/settings-schema` subpaths, and declares~18.1.17 dependencies. Unchanged adoption is unsuitable; no one-file repin or existing-coordinator attachment is proven. Preserve it as a candidate, not a selected deployment.
- **MCP BLOCKED for remote execution:** the user selected ChatGPT in the tablet browser; custom MCP/Tunnel UI is observed, but entitlement and authenticated route remain unverified; no inspected adapter qualifies. Native OMP consumes MCP tools, while RPC exposes proprietary JSONL. The inspected `a-Fig/pi-mcp-server@8bc0cc778954540460a194125a99bb4c64655226` targets Pi0.74.1 with synchronous unauthenticated sessions; `guyiicn/pi-subagent@07047044f5a251a0546637e7db887c2cea76383f` targets Pi0.77+, creates children and its own scheduler/registry. Neither establishes the sole qualified OMP coordinator or interactive decision contract. This bounded comparison does not assert that no suitable adapter exists.
- **Independent preparation completed:** official18.10.1 tag resolves to `5d0aaffaf1f987503ce129a642fb6e30339615af`. The focused comparison found unchanged Collab/RPC/MCP-authoring documents and no newly documented mission-MCP or existing-coordinator attachment route. Relevant RPC/UI and reconnect improvements do not establish the missing start/resume/MCP behavior. No reason to switch the qualified baseline solely to close these gaps was established. The running18.10.1 binaries were not requalified or changed. The subsequent18.8.7 release-asset check and isolated process probes are recorded below. Task52 retains source links and observations, without an additional tracker.

## Current readiness and next action

The Product Owner's instruction to continue followed presentation of this Plan; the coordinator applies it as authorization for the stated technical progression, not approval of unspecified infrastructure or costs. [Task52](https://github.com/skunklabs-uk/agent-os/issues/52) owns the concrete readiness criteria and results. Two actual read-only specialists compared mobile and MCP candidates; neither wrote shared sources or substituted for OMP-native execution proof. Their findings constrain later executable scope.

La prosecuzione resta tecnica e locale: i risultati sotto qualificano il riuso delle primitive native, non la connessione remota. Il laboratorio `omp-web` ha verificato la baseline originale e delimitato gap di compatibilità, prima di scegliere un host per la missione. Non serve una seconda conferma delle specifiche o della pianificazione. La successiva delega a proseguire copre la qualificazione locale necessaria, reversibile e senza nuovi accessi o spesa: il coordinatore delimita sotto download e build nel solo laboratorio, oltre la precedente lettura delle sorgenti. Nessun tunnel, servizio persistente o deploy è incluso.

## Qualificazione locale RPC/SDK — 2026-10-12

Dopo «ok prosegui», il coordinatore e uno specialista reale hanno eseguito processi OMP18.8.7 separati in directory usa-e-getta, con rete disabilitata tramite `unshare -Urn`, nessun prompt/inferenza, nessuna porta, tool/estensioni/skill disabilitati, `dev.autoqa: false` e `PI_AUTO_QA=0`. Nessun processo di altri progetti è stato modificato. Non si tratta di sola lettura delle sorgenti né di una ripetizione delle prove team-execution.

| Verifica | Esito osservato e limite |
|---|---|
| Identità binario | PASS: SHA256 coincide con `omp-linux-x64` in [SHA256SUMS v18.8.7](https://github.com/can1357/oh-my-pi/releases/download/v18.8.7/SHA256SUMS.txt). |
| RPC diretto | PASS al terzo tentativo: negoziazione v2, stato e messaggi vuoti, EOF e uscita0. I primi due tentativi falliscono prima dei frame RPC per percorsi native/HOME; raw conservati. |
| SDK Python originale | PASS limitato: `omp-rpc`0.1.0 importato dalla sorgente b07a1c1 senza installazione; stato, nuova sessione, binding idempotente nello stesso processo e arresto verificati. `stop()` termina il gruppo di processi; non è prova di EOF regolare. |
| Persistenza/ripresa | BLOCCATO: un nuovo processo con binding a directory vuota restituisce nuovo ID e `resumed=false`. I confini espliciti producono JSONL con soli metadati: l'aspettativa iniziale «nessun file» era errata, non un difetto del prodotto. Il tentativo di `switch_session` è respinto dal registry isolato per modello non trovato; nessun retry o modifica delle credenziali. La sorgente distingue lookup CLI sul catalogo completo e override RPC sui modelli disponibili (auth/config/filtri): non prova che il nome sia invalido o che il precedente account qualificato abbia perso accesso. |
| Interruzione | PASS solo per ack di `abort` inattivo, stessa identità e stato settled. Interruzione di lavoro attivo BLOCCATA/non provata: nessuna inferenza avviata. |
| Privacy | Il risultato completo `get_state` contiene contesto e metadati interni. Evidenze pubblicabili limitate a campi selezionati; raw privati, nessun inoltro indiscriminato a MCP. |

Dettagli, comandi esatti, errori e percorsi dei raw sono conservati nel [risultato Task52](https://github.com/skunklabs-uk/agent-os/issues/52#issuecomment-6123992823). Le evidenze private risiedono su NOVBSCWOLaulMaU in `/home/iingenito/.local/state/agent-os/remote-control`, con directory private e raw0700/0600; i binari del laboratorio conservano i soli permessi di esecuzione necessari. Questi risultati non provano identità missione, approvazioni, resume non vuoto, autenticazione, collegamento ChatGPT o uso dal tablet.

### Slice locale delimitata: compatibilità omp-web

**Esito della sola baseline: originale verificata; compatibilità18.8.7 e host unico non qualificati da questa prova. Il port successivo è descritto negli incrementi sotto.** Necessità: prima di introdurre codice custom, verificare se l'interfaccia esistente può funzionare con il provider qualificato. La sorgente dimostra import incompatibili ma non quantifica ancora tutti gli errori di compilazione. Il beneficio atteso è una decisione KEEP/REPLACE basata sul costo reale, non una nuova applicazione.

- **Owner e base:** uno specialista writer, checkout locale isolato del solo candidato `ddallabenetta/omp-web@0acce6240b27eb7d44d5c9b78187bd95e01270f8` sotto il laboratorio; nessun push al repository upstream, nessuna modifica dei checkout proprietari. Il coordinatore integra soltanto il risultato in Task52/Plan; reviewer separato se viene proposta una patch da mantenere.
- **Primo perimetro:** download del checkout completo e del lockfile al pin, Bun1.3.14 estratto soltanto nel laboratorio (asset ufficiale `bun-linux-x64.zip`, SHA256 `951ee2aee855f08595aeec6225226a298d3fea83a3dcd6465c09cbccdf7e848f`), dipendenze del lockfile; build/typecheck di baseline. Nessuna riscrittura o aggiornamento indiscriminato. Verificare disponibilità/versione/checksum e script di installazione prima di eseguirli; eventuali richieste di credenziali o risorse ulteriori fermano questa sola slice.
- **Comandi di verifica:** dopo risoluzione del percorso Bun fissato nel Task52, `bun install --frozen-lockfile --ignore-scripts`, `bun run typecheck`, `bun run build`. Ogni comando con limite10min; massimo un'installazione e un giro iniziale. Un errore di dipendenza richiede diagnosi sul log esistente, non ripetizioni indiscriminate. Nessun server `dev`, `start`, `dev:lan`, modello o CI.
- **Criteri:** (1) dipendenze/pin e risultato reale della baseline osservati; (2) costo minimo della compatibilità18.8.7 delimitato con file/API e test necessari, oppure incompatibilità esplicita; (3) proposta di riuso compatibile con il coordinatore unico, senza equiparare una build a un attach. Solo dopo questi risultati si delimita l'eventuale patch: non è autorizzato un adapter/framework generico.
- **Risorse e uscita:** un processo alla volta, massimo30min di comandi, zero inferenze e servizi pagati, nessuna credenziale copiata, nessuna porta/tunnel/deploy. Output confinati al laboratorio e rimovibili dopo la decisione; conservare soltanto evidenze necessarie. Il limite di tempo è operativo, non un tetto monetario.

Download e output di build estendono la precedente ricognizione read-only entro la prosecuzione tecnica locale; non sono una prova di nuova approvazione letterale né un'autorizzazione al trasporto remoto. Non vengono modificati file applicativi o repository proprietari. Per MCP resta disponibile l'SDK nativo, ma non è ancora selezionato un server: non costruire un secondo host/scheduler mentre l'ownership comune è irrisolta. Le tre ragioni concrete per rifiutare una consegna attuale restano: possibile coordinatore concorrente, assenza di prova autenticata fuori LAN, mancata verifica delle decisioni/ripresa durante lavoro reale.

### Esito baseline omp-web

[Risultato e raw Task52](https://github.com/skunklabs-uk/agent-os/issues/52#issuecomment-6124027214): un'installazione frozen/ignore-scripts, typecheck e build della sorgente originale passano (exit0), con dipendenze OMP18.1.17 e un warning sull'import dinamico della route export. File originali/manifest/lock invariati. Typecheck e build senza rete; override nativo `PI_CONFIG_DIR` relativo al laboratorio isola anche configRoot/log, oltre ad agent/natives. HOME invariato. Il build usa worker interni Next, non agenti né server di prova. Un chmod errato del coordinatore ha tolto il bit eseguibile al Bun del laboratorio: riparato da byte/manifest originali, nessun comando fallito o reinstallazione.

Il gap18.8.7 è maggiore di un repin: oltre agli import già rilevati, `Settings.get(path)/set(path)` sono sostituiti da handle `Setting.get/set`, e `isConfigured` accetta `AnySetting`. Sono coinvolti otto file di produzione per questa sola API, elencati nel risultato proprietario. Questo è un vincolo di sorgente; nessun build18.8.7 è stato simulato. Al termine della baseline la migrazione non era ancora avviata; gli incrementi successivi sono registrati sotto. Il PO ha ora richiesto anche il pannello separato; il candidato resta la prima opzione di riuso da qualificare; la build originale non copre la proprietà unica della missione o la prova tablet.

### Decisione di interfaccia acquisita — 2026-10-12

Il PO ha scelto esplicitamente «Anche il pannello OMP»: il percorso deve includere il pannello web OMP dal tablet oltre a ChatGPT/MCP. La proposta di usare soltanto ChatGPT non viene adottata. Restano tutti gli scenari approvati per entrambi gli accessi, sul dispositivo reale fuori LAN, con un unico coordinatore e il contratto condiviso di stato/comandi/decisioni.

La scelta risolve il requisito di interfaccia, non qualifica automaticamente il candidato, autorizza due host concorrenti o concede nuovi accessi/deploy. La prossima azione tecnica è delimitare il port del candidato18.1.17 verso il provider qualificato18.8.7, riusando baseline e gap già verificati senza ripeterne le prove. Uno specialista prepara il primo incarico implementabile e le dipendenze seriali, distinguendo compatibilità dalle successive prove di ownership e accesso MCP. Il coordinatore conserva l'ownership dei documenti e dell'integrazione; i writer useranno checkout distinti e un reviewer indipendente esaminerà ogni risultato materiale sul suo SHA esatto. Nessun merge IWANT o deploy.

### Primo incarico del port — Task53

[Task53](https://github.com/skunklabs-uk/agent-os/issues/53), sub-issue nativa di35, concretizza il lavoro successivo alla readiness: conservare le preferenze iniziali browser con le API18.8.7. Owner: un writer in checkout Git isolato del candidato0acce624, branch dedicato; coordinatore solo sulle fonti condivise; reviewer distinto sullo SHA finale. Cinque file massimi: manifest, lock Bun, eliminazione del lock npm obsoleto soltanto nel port, funzione preferenze e relativo test. La baseline originale resta intatta. Si riusa Bun qualificato, senza nuove installazioni di runtime.

La decisione locale di usare il solo lock Bun segue il runtime obbligatorio del candidato e impedisce due lock che descrivano provider differenti; non cambia gestori in altri repository. La migrazione necessaria modifica soltanto i cinque pin OMP diretti, tipi/handle Settings e test della funzione; niente shim o framework. Il criterio osservabile è RED→GREEN delle preferenze isolate, nessun modello o sessione. La superficie runtime non è avviata. I dettagli esecutivi e i criteri sono nel task, senza una checklist duplicata.

Questo incremento non produce un'app interamente compilabile: le incompatibilità note altrove rimangono esplicite. Le successive superfici seriali sono selezione modelli, tema/display, editor impostazioni, wrapper sessione e goal mode; non sono task già approvati o creati. Il checkpoint typecheck/build completo del port segue le correzioni necessarie, senza ripetere la baseline18.1.17. La scelta di sviluppare e verificare prima il componente isolato è un adattamento dichiarato dell'incrementalità al port, non una build verde simulata.

Il punto concreto di riuso per pannello e futuro MCP è `AgentSessionWrapper`/registry di `lib/rpc-manager.ts`: getRpcSession, send e onEvent condividono una sessione nello stesso processo. Il registry globale non si condivide tra processi; startRpcSession crea un proprietario SDK. Pertanto nessun avvio di missione avviene prima della decisione su host unico e transizione di ownership. Il seam osservato non seleziona o autorizza un server MCP custom.

### Raccordo MCP individuato — preparazione, non implementazione

La [ricognizione mirata in Task52](https://github.com/skunklabs-uk/agent-os/issues/52#issuecomment-6124306905) identifica un handler Web Request/Response del SDK MCP TypeScriptv2.3.1 come candidato per il medesimo processo Next/Bun. Il wrapper OMP deve essere recuperato dal registry esistente; una richiesta o disconnessione MCP non deve creare o distruggere il proprietario della sessione. Un secondo processo non condivide `globalThis`. Supporto documentato del trasporto non equivale a integrazione runtime verificata.

Il percorso remoto ha un gap di autenticazione concreto: il proxy del pannello protegge `/api/*` con Basic; una route MCP con bearer incontra tale controllo, mentre `/mcp` ne sarebbe fuori. Non esentare o spostare la route per aggirarlo. Prima dell'incarico esecutivo MCP occorre un raccordo di autenticazione deliberato, coerente con il client reale e senza un nuovo sistema duplicato. Nessun server, nuova dipendenza MCP o tunnel è stato creato. Il primo incremento eventualmente delimitato può osservare soltanto sessioni già presenti nello stesso processo, senza avvio automatico né comandi mutanti; non sostituisce gli scenari completi.

### Esito Task53 — preferenze iniziali

[Task53 concluso nel perimetro locale](https://github.com/skunklabs-uk/agent-os/issues/53#issuecomment-6124435079), candidato finale `0cf2c958c830b7ba6f7eb82afc915856159eda9d` su base0acce624. Otto test focalizzati passano senza rete/sessioni/inferenze; review indipendente esatta senza Required/Critical dopo correzione del caso Off. Il nuovo dominio18.8.7 consente Off nella sessione ma non nel default globale: la funzione conserva il default precedente senza alterare la scelta della sessione; Auto rimane Auto. Lock/pin verificati, cinque file nello scope, baseline originale invariata. Nessun push/merge del candidato o deploy.

Il sorgente Git e i raw restano in `~/.local/state/agent-os/remote-control/mobile-compat/port`; la fonte proprietaria del risultato contiene comandi, hash e limiti. Non è una build completa del pannello, una prova di ownership o un'accettazione mobile/MCP. Il port prosegue serialmente dalla revisione riesaminata; la prossima superficie necessaria è la selezione dei modelli e dei ruoli.

### Esito Task54 — selezione modelli/ruoli

[Task54 concluso nel perimetro locale](https://github.com/skunklabs-uk/agent-os/issues/54#issuecomment-6124734314), candidato finale `4f659cc3534b1569562db0cb22ae1d32f9ad94e4` su base0cf2c958. Handle cfgEnabledModels e thinking nativi; cinque file, pin/lock invariati. RED reale e GREEN finale padre14/14, figlio6/6; il test strutturale comune non viene contato come due scenari distinti. Review indipendente esatta senza Required/Critical dopo due correzioni: mock confinati in child Bun, e ruolo fuori filtro verificato nelle risposte GET/PUT. La mutazione delle due letture fa fallire entrambe le asserzioni; export file-access reale verificato nel padre dopo il child. Raw iniziali e tentativo intermedio fallito conservati nella fonte proprietaria. Nessuna suite/build completa, discovery/auth reale o accettazione remota.

### Esito Task55 — tema e display

[Task55 concluso nel perimetro locale](https://github.com/skunklabs-uk/agent-os/issues/55#issuecomment-6124862290), candidato `cd7ea935ae753c498dfcc3261728df27995ec4fb` su base4f659cc. Riutilizzati pi-tui/theme e gli handle cfgThemeDark/cfgThemeLight/cfgHideThinkingBlock; cinque file, formule palette e pin/lock invariati. RED delle API rimosse e GREEN focale8/8 più child2/2. Reviewer nuovo indipendente sullo SHA esatto: nessun Required/Critical, mutazione booleano rilevata e cold-theme probe1/1; verificati default/override, scope e rifiuti accesso, isolamento mock. Rendering visivo, configurazione da disco e app completa non attestati.

### Esito Task56 — editor impostazioni

[Task56 concluso nel perimetro locale](https://github.com/skunklabs-uk/agent-os/issues/56#issuecomment-6125045408), candidato `b4784462d2fcd02849421a629a8735168ae8681f` su base cd7ea935. Due file, registro/handle e metadata originali, nessuno schema duplicato. GREEN finale5 test più wrapper; masking GET, scope e validazioni verificati con Settings isolati. La review ha rilevato e fatto correggere un restringimento PATCH dei numeri con ui senza options; riesame esatto e mutazione dimostrano la regressione. Nessun finding residuo. PATCH conserva il readback della credenziale inviata già esistente; masking attestato solo per GET. Persistenza, UI e app completa restano non verificate.

### Gap delle decisioni rilevati nelle sorgenti

La [ricognizione read-only Task52](https://github.com/skunklabs-uk/agent-os/issues/52#issuecomment-6125019369) distingue il replay dei pending nel wrapper vivo dalla riconciliazione completa richiesta. Risposte duplicate/scadute non risolvono due volte, ma l'API riporta successo; mancano chiusura/riconciliazione dei dialoghi e verifica della revisione del piano durante l'attesa. Le primitive native cancel/targetId possono essere riusate. Prima di scegliere una correzione, serve la prova locale delimitata di questi casi: nessun nuovo ledger, host o architettura dedotto dalla ricognizione. Il passaggio seriale a una sessione OMP proprietaria resta da qualificare prima della missione reale e non è stato eseguito.

### Esito Task57 — entrypoint sessione

[Task57 concluso nel perimetro locale](https://github.com/skunklabs-uk/agent-os/issues/57#issuecomment-6125175757), candidato `c2be206748c8e9f1bf7061eeffbd535fdcbca000` su base b4784462. Due import thinking e handle enabledModels, cinque file con test. GREEN21/21 parent e4/4 child; parser nativo, opzioni/guard/errori/ensure_session e Auto verificati. Reviewer indipendente esatto senza finding: mutazioni guard, thinking e getter obsoleto rilevate. RED e incidente intermedio del runner conservati. Il collegamento getter/startup resta prova statica e la sessione della route sintetica; nessuna discovery/trust/ownership runtime attestata.

### Esito Task58 — goal mode

[Task58 concluso nel perimetro locale](https://github.com/skunklabs-uk/agent-os/issues/58#issuecomment-6125278461), candidato `95ebcf61d3b45ace3a76d33d6dc612b867b05b81` su base c2be206. Due handle nativi e fixture Settings reale; due file, logica e asserzioni preservate. RED dei due getter e GREEN24/24. Review indipendente sullo SHA esatto senza finding; mutazione della disabilitazione rilevata, default nativo e modalità web/array vuoto verificati separatamente. GoalRuntime e continuation restano sintetici; nessuna automazione o sessione reale attestata.

### Checkpoint corrente — port completo in Task52

Task52 riprende la qualificazione del candidato95ebcf61, dopo gli incrementi53–58. Stesso writer e checkout isolato; coordinatore soltanto su fonti e integrazione. Criterio: esiti reali di typecheck, lint dei file TS/MJS modificati, suite completa e build, con diagnostici e limiti conservati. Nessuna ripetizione della baseline18.1.17.

Comandi iniziali seriali: `bun run typecheck`; ESLint esistente sui soli file TS/MJS del diff0acce624..HEAD; `bun test`; `bun run build`. Bun1.3.14 e dipendenze18.8.7 già qualificate, nessuna installazione, download o cambio pin. Ogni comando massimo10min, fino a40min operativi per il giro iniziale; zero inferenze o servizi pagati. Ambiente whitelist e directory native/config/cache private del port, HOME invariato, PI_AUTO_QA=0 e telemetria Next disabilitata. Rete isolata tramite `unshare -Urn`; per la suite soltanto loopback attivato nel namespace privato, perché i test proxy esistenti usano listener sintetici effimeri. Nessuna esposizione sull'host o avvio dell'app.

Il primo giro non modifica sorgenti: sono ammessi soltanto output generati ignorati. Un errore richiede diagnosi prima della correzione minima e dei controlli pertinenti; non eseguire una build prevedibilmente fallente dopo errori typecheck irrisolti. Scope di eventuali correzioni e review sul nuovo SHA saranno esplicitati nello stesso task. Nessun server, CI, tunnel, merge IWANT o deploy. PASS del checkpoint non equivale a prove integrate di decisioni, ownership, MCP o tablet: queste restano successive e necessarie.

#### Diagnostici reali e correzione delimitata

Il primo typecheck su95ebcf61 fallisce con20 diagnostici in10 file (`port/logs/checkpoint52/typecheck.log`). Build non avviata. Non sono fallimenti della baseline già accettata: emergono dalle API18.8.7 dopo il port parziale.

La correzione necessaria rimane in Task52: dieci file produzione — route auth api-key/login/logout, provider-listing-runtime, goal-mode, omp-types, api-types, rpc-manager, startup-preferences e skills-service — più test pertinenti. Riutilizzare namespace nativi AuthStorage (credentials/keys/oauth), tipo Goal originale, SettingProvenance, evento nativo, cfgSkills; conservare il dominio valido del default thinking anche con inherit. Nessuno shim, cast any o indebolimento del typecheck. Il confronto tra vecchie e nuove API deve preservare validazione, configurazione e rimozione credenziali senza ampliare login/accessi.

RED/GREEN focali con Settings reali isolati; auth/discovery intercettate in processi child, soltanto dati sintetici, nessun AuthStorage proprietario né OAuth reale. Poi riprendere il checkpoint con gli stessi limiti; lint/include test aggiornati al diff effettivo. Una review indipendente sul nuovo SHA copre l'intero delta residuo e i risultati complessivi, senza trasferire automaticamente i verdetti precedenti. Pin/lock, policy auth e protocollo remoto restano invariati; i gap decisionali rilevati sono lavoro successivo.

La [verifica del trasporto in Task52](https://github.com/skunklabs-uk/agent-os/issues/52#issuecomment-6125441043) distingue Secure MCP Tunnel dall'accesso diretto al pannello web: la documentazione non qualifica il secondo percorso. Prerequisiti tunnel/account e raggiungibilità OAuth restano non verificati; nessuna nuova chiave, connessione o esposizione è stata creata. La futura prova fuori rete dovrà coprire entrambe le interfacce richieste.

Il checkpoint ha inoltre esposto una fixture proxy dipendente dal NO_PROXY ambientale: dopo correzione dei due riferimenti auth statici, suite548PASS/1SKIP/1FAIL. La correzione delimitata include solo `lib/http-dispatcher.test.mjs` e sezione proxy README (eventuale commento pertinente): bypass loopback configurato esplicitamente nel child e URL semanticamente equivalente, conservando le asserzioni su percorso diretto e unica richiesta proxy. Nessuna logica networking o ambiente globale modificati. La precedente promessa README di bypass automatico non deve essere mantenuta dopo il comportamento contrario osservato.

La review indipendente del checkpoint sul candidato `b460a1e1c8d5a17039eb95524ecc617d38bf183b` rileva tre finding **Required**: la route SSE elimina i campi nativi sicuri `isTerminal`, `yielded`, `awaitingAsyncWork` da `agent_end`; GoalMode tratta anche `agent_end` non terminale come fine e può schedulare un turno concorrente; README e commento fixture descrivono il proxy Bun come letto soltanto all'avvio, in contrasto con la fonte ufficiale per il pin1.3.14. Il checkpoint resta **FAIL** finché questi punti non sono corretti e riesaminati su SHA nuovo. Lo stesso writer può modificare soltanto route SSE, hook e test pertinenti, GoalMode e test pertinenti, README/commento fixture. Regioni di evento private non vanno inoltrate; l'evento non terminale non deve chiudere lo stato visibile né causare continuazione Goal. Test RED/GREEN focali, typecheck, lint, suite e build sono richiesti dopo la modifica materiale. Nessun server, sessione modello, CI o accesso remoto è autorizzato da questa correzione.

Durante la correzione è emerso che `AGENTS.md` (sezione HTTP proxying) e il commento di `lib/http-dispatcher.ts` ripetono la stessa descrizione obsoleta; `AGENTS.md` attribuisce inoltre a Bun bypass automatico di loopback e assenza di supporto NO_PROXY, contraddetti dalla prova qualificata con Bun1.3.14. Lo scope del medesimo finding comprende ora **solo testo/commenti** in questi due file per allineare le istruzioni e la spiegazione al comportamento osservato e alle note Bun. Nessuna modifica alla logica dispatcher, ai pin o ai test è giustificata da questo completamento documentale. Suite/build già eseguiti sul codice identico non si ripetono solo per questi commenti; reviewer verifica il delta finale.

Il writer ha consegnato il candidato locale `9bf17e739abbced6643834920ac9338270a21533` su parent `b460a1e1c8d5a17039eb95524ecc617d38bf183b`, senza push. Tre RED focali e GREEN38/38; typecheck exit0; suite completa nel namespace con loopback attivo553PASS/1SKIP/0FAIL; build Next a due worker exit0. Il primo run della suite senza `lo up` fallì solo nella fixture proxy: errore del comando conservato, corretto una volta con il comando già qualificato senza modifica del codice proxy. ESLint diretto exit1 per `react-hooks/preserve-manual-memoization` nell'hook, presente identico nel parent; il lint con sola regola esclusa exit0 è diagnostico, **non PASS pieno** del lint. Il warning dynamic-import della route export preesiste. Raw e comandi restano privati nel laboratorio `port/logs/checkpoint52-required/`; il checkout finale è pulito, pin/lock invariati. Review indipendente fresh-context sullo SHA esatto: nessun Critical/Required nel delta; route SSE proietta solo tre booleani sicuri, hook e Goal ignorano la fine non terminale, documentazione proxy allineata. Il test hook è strutturale, non un'esecuzione React. Il checkpoint di compatibilità è quindi qualificato **nel solo perimetro del delta con eccezione lint baseline dichiarata**; non qualifica server, sessione reale, decisioni, ownership, MCP, accesso remoto o tablet. Questi restano requisiti aperti e non ereditano il GO.

### Prossima slice diagnostica — decisioni e riconnessione, Task52

Base locale `9bf17e739abbced6643834920ac9338270a21533`; un solo specialista nel medesimo checkout isolato. Prima di proporre una patch, costruire prove sintetiche delimitate per risposta duplicata/scaduta, due richieste pendenti, timeout/abort, revisione del piano cambiata durante l'attesa, wrapper mancante e riconnessione con pending. Confrontare route, wrapper, hook e contratto provider; distinguere `accepted`, `rejected`, `unknown` e stato finale. Sono ammessi soltanto test/fixture locali e raw privati necessari alla diagnosi, senza modifiche alla logica applicativa o ai documenti condivisi. Comandi focali Bun e typecheck solo se un test lo richiede, massimo10min per comando e30min complessivi, nessun servizio, modello, credenziale, rete esposta o CI. Riportare i casi RED reali, ciò che è già PASS, la superficie minima di eventuale correzione e prerequisiti aperti. Il coordinatore delimita poi la correzione necessaria nello stesso task prima che il writer tocchi produzione; nessuna nuova architettura o ledger deriva automaticamente da questi probe.

I probe sintetici sono al candidato `28da5a85279fb1e3086900182f30d6ccab8fbb24` (test soltanto): wrapper cinque PASS per isolamento di due pending, una sola applicazione, timeout/abort, replay nel wrapper vivo e cancellazione alla distruzione; un RED corretto per piano modificato che viene approvato. Due RED route: risposta decisionale scaduta riceve successo, e wrapper mancante causa `startRpcSession` per una vecchia risposta. Test UI/browser non eseguiti; `get_state` senza pending e un unico slot dialogo restano deduzioni da sorgente.

**Fix seriale delimitato a questi RED:** stesso writer, solo `lib/rpc-manager.ts`, `app/api/agent/[id]/route.ts` e test pertinenti. Il wrapper deve distinguere risposta accettata da ID non pending senza riapplicarla; la route deve rifiutare esplicitamente la risposta scaduta e non creare un wrapper per quel comando. Una risposta valida conserva il percorso esistente. La proposta di piano deve verificare prima dell'approvazione che contenuto e contesto della revisione mostrata siano ancora correnti; se cambiano, lasciare plan mode attivo e chiedere nuova proposta. La fixture route deve simulare fedelmente il nuovo esito del wrapper e coprire anche la risposta valida, altrimenti il RED non può diventare GREEN per la correzione giusta. Niente ledger, nuova API per altri comandi, cambi al client UI, provider/skill o autenticazione in questa slice. RED/GREEN focali, typecheck, lint sui file modificati, suite completa e build locale con limiti del checkpoint; raw privati e review indipendente sullo SHA finale. La successiva slice UI/reconnect deve ancora verificare e correggere visibilità di più pending, chiusura/ack e riconciliazione, senza usare il GO server come acceptance remota.

La review indipendente sul candidato `584e8dae646ed56503846aad97f03bf8c21d6f8c` richiede un'altra correzione prima del GO: il controllo di approvazione confronta solo enabled/percorso/contenuto, ma non `workflow` e `reentry`; una modalità cambiata durante l'attesa può ancora essere approvata. Un confronto mirato con il SDK18.8.7 rileva inoltre un difetto di compatibilità preesistente nella stessa superficie: il tipo locale dichiara `parallel|sequential`, mentre il runtime nativo usa `parallel|iterative`, e il restore di una sessione `iterative` la trasforma in `parallel`. Scope correttivo: stesso writer, `lib/rpc-manager.ts`, solo la dichiarazione PlanModeState in `lib/omp-types.ts` e test pertinenti. Fotografare e confrontare tutti i campi del contesto Plan rilevanti durante la review; conservare workflow `iterative` nativo nel restore, senza migrazione inventata o cambio ad altre modalità. Test RED/GREEN per cambio workflow/reentry e restore iterative, caso invariato ancora approvabile; poi controlli proporzionati e riesame indipendente su nuovo SHA. Route/ack già corretti restano invariati salvo finding concreto. Il candidato584e8 non ha GO e nessuna acceptance UI/remota è acquisita.

La review del successivo candidato `ae9f4db31164947d52844a091f974601885f069d` individua una corsa ancora aperta: il codice legge PlanModeState **prima** dell'ultima lettura asincrona del piano; un cambio di stato durante quell'`await` può applicare l'approvazione vecchia. Spostare la lettura e il confronto dello stato dopo l'ultimo `await`, immediatamente prima della transizione sincrona, con regressione che intercali il cambio. Per il restore, il test sintetico inietta un campo `workflow: iterative`, ma OMP18.8.7 registra nativamente `mode_change(plan, {planFilePath})` senza workflow; il codice attuale corregge solo la mappatura **se il campo esiste**. Non dichiarare ripristino native iterative completo: registrarne il limite e lasciare la persistenza/reconnect reale alla slice di continuità, senza introdurre ora un ledger o modificare il runtime nativo. Aggiungere un controllo che distingua il `mode_change` nativo privo del campo da quello sintetico; il GO eventuale resta circoscritto a ack e guard di approvazione del wrapper vivo. Nuovo SHA e review indipendente richiesti; il candidato ae9f4db non ha GO.

Il candidato locale finale della slice server è `c6ad3376fc6968764ebbc5077e83362485a9f44c`, senza push. Il test di intercalazione ha un RED valido sul parent e GREEN sul nuovo SHA; un primo tentativo RED fallì per mock incompleto ed è conservato separatamente. Writer: 13 prove focali PASS, typecheck/lint changed exit0, suite completa con loopback567PASS/1SKIP/0FAIL e build cpus2 exit0; warning export preesistente. Reviewer Osmani realmente indipendente sullo SHA esatto: nessun Critical/Required nel guard del wrapper vivo; 14 test mirati eseguiti indipendentemente, compresi route stale409, no-owner409, valid200. Raw privati `port/logs/decision-probe/`. L'esito è **PASS circoscritto** ad ack/guard e sessione viva, non alla continuità nativa: il record OMP `mode_change(plan,{planFilePath})` omette workflow, quindi iterative non sopravvive al restore nativo tramite questo port. Il test lo mostra e il limite resta aperto per la continuità. UI, reconnessione, missione reale, tablet, MCP e hosting non sono verificati.

### Prossima slice — comportamento UI delle decisioni, Task52

Prima di implementare, verificare in prova locale sintetica le conseguenze di due richieste pendenti, ack409/errore di rete, risposta valida, scadenza/abort e reconnessione SSE. L'utente deve poter vedere identità/stato attuale della decisione e distinguere invio da applicazione; una risposta non confermata non deve sparire silenziosamente. Confrontare hook, dialogo, route `get_state` e replay del wrapper; annotare quali casi richiedono un test browser/React o app reale invece di sostituirli con asserzioni statiche. Un solo writer nel checkout isolato su base c6ad337, solo test/fixture e raw privati nella diagnosi, senza cambiare ancora logica UI o avviare servizi/modelli. Comandi focali <=10min ciascuno e30min complessivi; il coordinatore delimita il fix solo dopo RED affidabili. Resta aperta anche la continuità del workflow nativo, da affrontare con il percorso minimo quando la prova di reconnect lo rende necessario, senza introdurre un tracker o ledger duplicato.

Diagnosi test-only al candidato `b50755824268f84879a4f0e8293b14fa22a5594b`: 17 PASS comportamentali sintetici nel wrapper/helper HTTP/route/SSE (due ID replay, 409 distinto da 200 e guasto rete), cinque RED **statici** nel hook/dialogo/get_state. Questi ultimi sono inferenze dal sorgente, non prova browser: il secondo pending sostituisce il primo, il dialogo sparisce prima dell'ack, il catch scrive solo in console, scadenza/abort non invalidano la vista e get_state omette i pending. I primi due log del probe con percorso Bun errato sono exit127 e non valgono; raw validi privati `port/logs/decision-probe/ui-*`. Nessuna logica produzione modificata e nessun PASS di suite/build attribuito ai RED intenzionali.

**Fix UI locale delimitato:** un writer sullo stesso checkout, base b507558; file consentiti `lib/rpc-manager.ts` (mappa pending già autorevole), route SSE e GET stato di `app/api/agent/[id]`, `hooks/useAgentSession.ts`, `components/ChatWindow.tsx`, tipi/test direttamente pertinenti. Non creare un ledger né un secondo proprietario: esporre uno snapshot/identità dei pending dal wrapper e un evento di chiusura su risoluzione, timeout, abort/destroy; il consumer riconcilia i replay dopo reconnect e rende ciascuna decisione raggiungibile. Mantenere visibile una risposta finché l'ack è noto; 409 rifiutato e outcome di rete sconosciuto devono essere comunicati, senza ripetere automaticamente approvazioni. Una decisione scaduta o annullata non deve più poter essere inviata. Il client HTTP/route già qualificati non vanno riscritti per comodità. Aggiungere test comportamentali sui confini puri/server e prove UI quanto possibile con dipendenze già presenti; i test statici da soli non qualificano il browser. Nessun nuovo framework, pin, modello, servizio, tunnel, CI o accesso remoto. RED/GREEN, typecheck, lint file cambiati, suite e build locali proporzionati; review indipendente sullo SHA prima di app smoke. Se una prova richiede browser/server reale, dichiararla e delimitarla separatamente prima dell'avvio. La continuità native iterative resta limite distinto, non risolto implicitamente da questo fix.

Lo specialista ha segnalato prima di edit produzione che questa superficie è troppo ampia per una singola patch facilmente revisionabile. Procedere **serialmente A→B→C con lo stesso owner**, senza GO parziale alla UI: A wrapper/stato/SSE con snapshot pending e chiusure, B hook con collezione per ID/reconcile/ack, C ChatWindow con accesso a tutte le decisioni e scadenza. Ogni incremento ha RED/GREEN pertinenti e SHA; typecheck/lint focali a ogni incremento, suite/build complessivi dopo C se i precedenti non introducono un difetto che richieda prima la verifica. Una review indipendente del delta A–C sullo SHA finale, e re-review solo se un finding materiale lo richiede. Nessuna pubblicazione o app smoke prima dell'integrazione B/C. Per A, usare la mappa pending già esistente e verificare anche il precedente schema `extension_ui_request` con `closed:true` usato dal custom UI; non inventare un secondo ledger o protocollo se il segnale esistente basta. Tutti i limiti operativi sopra restano invariati.

Durante C è emerso un limite UX concreto: il candidato supporta i cataloghi `en` e `zh-CN`, ma le nuove etichette/stati del centro decisioni sono stringhe inglesi hardcoded. Lo scope di C comprende ora **solo** le chiavi necessarie nei due cataloghi esistenti `lib/i18n/messages/{en,zh-CN}.ts` e il loro uso in ChatWindow/hook dove il nuovo testo è visibile, senza aggiungere locale, framework o altro copy. Verifiche i18n pertinenti dopo il delta; suite/build già passati sul codice precedente non vengono trasferiti allo SHA con nuovi testi senza controllare almeno typecheck, lint, test copy e build se il bundle cambia. Restano le eccezioni GitNexus indisponibile (tool `detect_changes()` assente) e lint hook baseline già dichiarate: audit manuale di scope è evidenza distinta, non un surrogato dichiarato equivalente.

Il candidato A→B→C è ora `dbeb69291490908e129ac4528c884b743d4626b0` (parent b507558), locale e senza push. Gli incrementi sono A aa432dd, B35e965d, C dbeb692; il checkout è pulito e il diff non cambia pin/lock. Raw privati `port/logs/decision-probe/`: focali finali40PASS, typecheck exit0, suite591PASS/1SKIP/0FAIL e build Next15/15 exit0. Il lint standard resta exit1 per la regola preesistente `react-hooks/preserve-manual-memoization` in handleSend; il run con quella sola regola esclusa è diagnostico, non PASS completo. GitNexus impact/detect_changes non era disponibile: audit manuale e `git diff --check` sono distinti. Review Osmani indipendente sullo SHA è in corso. Non è stato avviato il browser o il server applicativo; nessuna prova di touch, SSE+POST live, sessione reale, tablet o accesso fuori rete è acquisita. Il prossimo gate è il verdetto indipendente; eventuali Required comportano correzione e re-review sul nuovo SHA prima di delimitare lo smoke locale senza modello.

Una ricognizione MCP separata, in sola lettura, ha confermato che il [custom MCP ChatGPT](https://developers.openai.com/api/docs/guides/custom-mcp-server) può usare URL o Tunnel e che il [Secure MCP Tunnel](https://developers.openai.com/api/docs/guides/secure-mcp-tunnels) trasporta MCP senza esporre il pannello web. Nessuna connessione nell'account/tablet è stata verificata. L'RPC OMP18.8.7 al pin indicato sopra usa JSONL stdio; la route `/api/mcp` di omp-web configura client esterni, non espone il coordinatore come server. Il registry del wrapper è nel processo Next/Bun; un bridge separato rischierebbe un secondo owner. Un eventuale handler nello stesso processo resta ipotesi da valutare, non implementazione approvata: il proxy web protegge `/api/*` con Basic, mentre il client ChatGPT richiede un raccordo di autenticazione supportato, più scope/ownership e permessi tunnel/workspace da verificare. Nessun tunnel, nuova dipendenza o servizio è stato creato. C1 resta BLOCCATO per prova effettiva di account/connessione e autorità del percorso; il blocco non sospende la qualificazione locale mobile.

La review indipendente su dbeb692 richiede due correzioni prima del GO del codice UI: quando scompare il controllo attivo, il focus può cadere fuori dal dialogo modale; Escape dai nuovi selector/retry/dismiss può propagarsi alla scorciatoia globale e interrompere l'agente. Delimitazione della correzione nello stesso checkout/owner: solo `components/ChatWindow.tsx` e test UI direttamente pertinenti, con eventuale helper hook solo se indispensabile e motivato prima dell'edit; ripristinare il focus su un controllo sopravvissuto alla transizione e contenere Escape nel centro decisioni senza autorizzare o interrompere il lavoro sottostante. Coprire entrambe le regressioni con test comportamentali per quanto consentito dallo stack esistente, senza nuovo framework; una prova montata/browser è ancora necessaria se i test restano solo SSR/statici. Prima RED affidabile, poi GREEN, typecheck/lint pertinenti e suite/build proporzionati al delta; il lint baseline resta separato. Nuovo SHA, review indipendente delle correzioni e nessun server, modello, push o smoke utente in questa correzione. Il verdetto dbeb692 è **request changes**, non un GO.

La ricognizione della route mobile trova Tailscale installato ma `NeedsLogin` e nessun Serve attivo; il tablet/Tailscale non è verificato. Serve verso localhost richiederebbe entrambi i dispositivi nella tailnet e policy di accesso; un ingress HTTPS già gestito andrebbe identificato e autorizzato dal proprietario. Funnel esporrebbe pubblicamente il pannello privilegiato e richiede una decisione distinta. Nessun percorso fuori LAN è attivo o accettato e Secure MCP Tunnel non lo sostituisce. La scelta operativa resta dopo correzione/review e prova locale, prima di ogni provisioning; non presumere l'accesso del tablet.

Il Product Owner ha poi preferito **Cloudflare** al percorso Tailscale per il tablet. La ricognizione read-only usa ora `homelab/origin/main@300fe85abd686817dab2cfc154a1faeb5b70cef1`: il checkout Homelab locale è indietro di 86 commit e contiene una modifica al runbook rete di altro proprietario, non toccata. La fonte corrente conferma che DNS, Access e configurazioni tunnel sono gestiti in `infra/opentofu/cloudflare-zero-trust/`; il connector del tunnel privato esistente è un Deployment Kubernetes a due repliche e gli ingress HTTP portano al Gateway Traefik. Aggiungervi `127.0.0.1` non raggiungerebbe il pannello su NOVBSCWOLaulMaU. Il PC ha `cloudflared` 2026.9.3 e systemd WSL attivo, ma nessun servizio cloudflared configurato/attivo e nessun listener OMP sulla porta di prova.

**Candidata operativa isolata, ancora da autorizzare nell'owner Homelab:** un tunnel Cloudflare *named* remoto distinto, con il solo connector su NOVBSCWOLaulMaU che raggiunge OMP su loopback; un hostname dedicato, applicazione Access con la policy riusabile Admin Only esistente **prima** della route e validazione dell'AUD/token Access nel connector; pannello avviato dal checkout sorgente `bd102be` con hostname esterno nell'allowlist, autenticazione propria obbligatoria e profilo/missione esplicitamente scelti. Il root OpenTofu corrente gestisce la configurazione di tunnel già esistenti, DNS e Access, ma non crea il nuovo tunnel: un'eventuale PR di Homelab dovrebbe possedere anche quella risorsa e custodire il token del connector senza inserirlo in issue/PR. Prima di selezionarla, confrontare la raggiungibilità cluster→host e il costo di un origin LAN sul tunnel privato già esistente: richiederebbe aprire il pannello fuori loopback e gestire WSL/firewall, quindi non è equivalente al percorso host-local; la fattibilità non è stata provata né esclusa. Aggiungere invece un connector del PC allo stesso tunnel con service `127.0.0.1` non funziona per le repliche Kubernetes che condividono l'ingress. Il launcher/servizio PC, lifecycle WSL e riavvio del pannello sono una responsabilità separata da GitOps Kubernetes; il comportamento dopo sleep/reboot resta da progettare e provare, non è una garanzia. Nome host, permessi Cloudflare, state operativo, policy esatta, costi e approvazione del proprietario restano da verificare prima di una PR/apply. Un `tofu plan` affidabile richiede lo state e gli input operativi correnti senza esporre segreti, e va rifiutato se modifica risorse estranee.

La [guida Cloudflare corrente](https://developers.cloudflare.com/cloudflare-one/access-controls/applications/http-apps/self-hosted-public-app/) richiede protezione Access e validazione del token all'origine; il [Quick Tunnel](https://developers.cloudflare.com/tunnel/get-started/quick-tunnels/) non supporta SSE e non qualifica il flusso OMP. La variante cluster richiederebbe migrazione del workload/stato e ownership Homelab, non giustificata ora. Nessun tunnel/DNS/servizio è stato creato; il prodotto su tablet, SSE dietro Access e la corrispondenza Host/Origin con HTTPS sono prove future, non implicazioni dei test locali. La scelta Cloudflare non è approvazione a esporre il pannello o a fare deploy. Il tunnel MCP sicuro è una corsia separata e non riusa automaticamente l'hostname del pannello.

La correzione dei due Required tastiera è al candidato locale `56d7fb3aba02bd7d853d1fe4c677a191f2984302` (parent dbeb692), solo ChatWindow e test; RED2, GREEN15, typecheck e lint dei file toccati exit0, suite594PASS/1SKIP/0FAIL, build exit0. Un reviewer Osmani diverso dal writer non trova Critical/Required sul nuovo delta e ha rieseguito9 focali, typecheck, lint changed e diff check; non trasferisce a sé suite/build dell'autore. I test focus/Escape sono helper e guard statici: **il comportamento React montato resta BLOCCATO**. Il GO riguarda solo il delta di codice, non la UI reale o il tablet.

**Prossima prova locale senza modello, prima della route Cloudflare:** usare il medesimo SHA e il build già qualificato, profilo OMP usa-e-getta tramite `PI_CODING_AGENT_DIR` in area privata e `PI_AUTO_QA=0`; nessuna sessione/modello/estensione reale. Montare il centro decisioni con due fixture sintetiche nel browser Chromium già presente, esercitando Tab/focus, Escape senza abort, risposta con controllo che scompare, retry/dismiss e selezione; conservare output/screenshot privati e rimuovere la fixture. In separata prova HTTP dell'app compilata, avviare `bun run start` su loopback in namespace di rete isolato con `lo` attivo, verificare GET pagina e sole API non mutanti, poi terminare il processo e controllare che non resti listener. Nessun endpoint pubblico, modello, credenziale, tunnel, CI o deploy. Ciascun comando max10min; errori di setup vanno diagnosticati, non contati come PASS. I test browser/componenti non equivalgono allo smoke dell'utente sul tablet né provano decisioni live nel coordinatore.

Primo comando delimitato, solo fixture React locale compilata con Bun dal commit56d7fb3 in `port/logs/decision-probe/` e Chromium isolato (nessun server/app OMP): `unshare -Urn -- sh -c '/usr/sbin/ip link set lo up && exec /home/iingenito/.local/state/agent-os/remote-control/mobile-compat/bin/bun /home/iingenito/.local/state/agent-os/remote-control/mobile-compat/port/logs/decision-probe/mounted-decision-probe.mjs'`, con stdout/stderr nel log privato. Lo script apre solo il file HTML locale, verifica DOM/focus/Escape con DevTools Protocol, salva screenshot privato, termina Chromium e cancella il profilo temporaneo. Il comando di avvio dell'app completa sarà definito e verificato separatamente prima di quella fase; nessun server è implicitamente autorizzato da questo test di componente.

La prima esecuzione della fixture browser fallì perché Chromium bloccava un modulo `file://` senza `--allow-file-access-from-files`; il log è conservato come errore di setup. Dopo la correzione del solo launcher, il run finale al medesimo SHA ha osservato in Chromium tre ID distinti, Escape contenuto da selector e retry, focus riportato dentro il dialogo dopo submit/retry/dismiss, Tab che torna dal controllo finale al primo, zero eccezioni/errori console; un messaggio informativo React DevTools non è un errore. Screenshot e log restano privati `port/logs/decision-probe/mounted-decision-probe*`. È prova montata con fixture sintetica, non prova dell'app/sessione live o del tablet.

Secondo comando delimitato, HTTP smoke dell'app completa sul build già esistente al medesimo SHA: `timeout 180 unshare -Urnpf -- bash /home/iingenito/.local/state/agent-os/remote-control/mobile-compat/port/logs/decision-probe/local-app-smoke.sh`. Lo script attiva loopback, imposta `PI_CODING_AGENT_DIR` usa-e-getta, `PI_AUTO_QA=0` e telemetria Next disabilitata, avvia Next/Bun solo su `127.0.0.1:30141`, richiede `/`, `/api/agent/running` e `/api/sessions` in lettura, controlla profilo senza sessioni, termina il PID in trap; il namespace PID elimina eventuali figli al termine. Nessun provider o prompt. Conservare exit e raw privati, verificare il processo/listener esterno assente; un errore non si trasforma in PASS.

Lo smoke HTTP locale è PASS al commit56d7fb3: pagina, running e sessions in lettura rispondono; il profilo usa-e-getta ha zero sessioni; nessun listener30141 è rimasto sull'host. Prima della prova fuori rete resta utile una sola ispezione visiva dell'app completa: estendere lo stesso script isolato con Chromium headless già presente, viewport 768×1024, profilo browser temporaneo, screenshot privato della pagina caricata e log console/processo, senza navigazione esterna o mutazioni. Eseguire una volta sul medesimo build, poi terminare app e browser e verificare cleanup. È browser desktop con viewport simulato, non tablet fisico o prova di decisione live.

Ispezione visiva locale dell'app al medesimo SHA: Chromium headless in namespace isolato ha caricato `omp-web` a 768×1024 con profilo OMP vuoto, nessuna eccezione/errore console; schermata autentica dell'empty state `Get Started` conservata privatamente in `port/logs/decision-probe/local-app-smoke/app-browser.png`, raw in `browser.log`. Il rendering conferma solo shell e stato vuoto, non leggibilità/efficacia del centro decisioni dentro l'app. Il comando è terminato e non restano listener30141/9334 sull'host. Restano BLOCCATI flusso SSE+POST in app con decisioni vere, ownership della missione, reconnect, dispositivo e rete esterna; non presentare lo screenshot desktop come prova mobile.

#### Prossima prova delimitata — decisioni native nell'app, senza inferenza

Sul medesimo candidato locale `56d7fb3` e build già qualificato, eseguire una prova integrata in namespace rete/PID isolato: `timeout 240 unshare -Urnpf -- bash /home/iingenito/.local/state/agent-os/remote-control/mobile-compat/port/logs/decision-probe/live-app-run.sh`. Lo script avvia Next/Bun soltanto su loopback30141 con `PI_CODING_AGENT_DIR` e cwd usa-e-getta, `PI_AUTO_QA=0`, `dev.autoqa: false`, nessun provider/modello specificato, nessun prompt e nessuna credenziale letta dal profilo proprietario. Un'estensione temporanea del profilo di test emette due `ctx.ui.confirm` all'avvio della sessione creata via `ensure_session`; il nome sintetico della sessione serve solo a renderla nella lista del browser. Il test legge snapshot e replay SSE, ricarica la pagina mantenendo gli ID, risponde A/B dalla UI, verifica il rifiuto409 di una risposta duplicata e controlla log/console. Browser Chromium e raw restano privati; trap e namespace terminano app/sessione/browser. Il wrapper deve controllare che non rimangano listener sull'host.

Questa prova attraversa server, wrapper OMP e UI con decisioni sintetiche vere, ma non avvia una missione o inferenza, non usa il tablet e non configura Cloudflare. Eventuali errori di setup/visibilità restano FAIL da diagnosticare, senza chiamarli accettazione. Non modificare sorgenti, pin o installazioni per farla passare; se si scopre un difetto applicativo, delimitarne la correzione e review sul nuovo SHA prima di proseguire. La scelta Cloudflare richiede ancora autorità Homelab/Access e successivo OK distinto per deploy.

Primo tentativo FAIL di setup (raw `live-run-jfcWPk2b`, diagnostico `live-run-6S5n9PTm`): `ensure_session` risponde e il wrapper dichiara dispatch, ma pending0 e il log dell'estensione non compare. La discovery read-only trova l'estensione senza errori; il sorgente SDK18.8.7 mostra che `toolNames: []` imposta `restrictToolNames` e costruisce il runner senza estensioni preloaded. Il successivo tentativo userà `toolNames: ["read"]`: il wrapper attiva solo la lettura nativa, mentre non invia alcun prompt e dunque non esegue tool o modello. È correzione della fixture di test, non del prodotto; il fallimento iniziale rimane conservato.

Il tentativo con `toolNames: ["read"]` fallisce prima della UI (`live-run-LYRBiC4F`): HTTP500 `ResolveMessage: Cannot find module './browser/prelude-definition' from ''` durante l'avvio SDK nel server compilato. È un difetto/collisione di caricamento da diagnosticare sul percorso normale; non chiamare il pannello qualificato. Per isolare il solo flusso decisioni, il prossimo profilo usa-e-getta disabilita tramite Settings native i quattro eval preludes browser/computer/ratchet/archive, senza cambiare sorgenti o runtime del proprietario; qualunque PASS sarà circoscritto a questa configurazione. In parallelo una diagnosi read-only separata esamina causa e correzione minima del percorso di default. Nessun altro run o servizio esterno.

Il profilo così delimitato avvia l'estensione e riceve le richieste native, ma il test si ferma prima del browser (`live-run-qJleVcU9`): una `ensure_session` vuota non entra nella lista anche dopo `set_session_name`, perché il SessionManager rinvia il primo file JSONL finché non esiste output durevole e `getRpcSessionInfos()` esclude gli idle non persistiti. Il prossimo tentativo emetterà **solo** il comando `bash` nativo `printf 'synthetic decision probe\\n'` dentro cwd usa-e-getta e namespace isolato, senza modello, per creare una sessione locale persistita con l'handle già esistente; poi verificherà che la lista mostri quell'ID prima della UI. Questa è fixture di visibilità, non prova di avvio/ripresa di missioni reali. Il raw fallito resta conservato.

La prova integrata circoscritta è **PASS** su `56d7fb3` con profilo configurato senza i quattro eval preludes (`live-run-2XJrufaW`): sessione persistita da comando locale sintetico, due `ctx.ui.confirm` nativi con ID distinti, snapshot SSE2 e replay2, UI montata dell'app a 768×1024, reload con gli stessi pending ID, Confirm A e Cancel B ricevuti dall'estensione, duplicato409, pending finale0, nessuna eccezione/errore console. Screenshot autentici `live-app/live-decisions-before.png` e `after.png` e raw privati conservati; ispezione visiva della schermata prima: dialogo leggibile, due voci selezionabili e controlli in viewport, ma è Chromium desktop con viewport tablet, non dispositivo fisico. Nessun listener30141/9335 rimasto, sorgente del candidato pulito e non pubblicato. I tre tentativi falliti sopra restano distinti dal PASS. **BLOCCATI**: startup default con eval prelude, missione vera e continuità owner, Cloudflare/Access, tablet fuori rete, ChatGPT/MCP. Il test non è lo smoke dell'utente e non autorizza deploy.

#### Correzione richiesta prima della qualificazione normale

La diagnosi read-only indipendente sullo SHA `56d7fb3` attribuisce l'HTTP500 al percorso SDK OMP18.8.7: `src/sdk.ts` costruisce il prompt di startup includendo gli eval preludes attivi; `src/tools/browser.ts` usa `require("./browser/prelude-definition")` senza una base di risoluzione nel processo Next/Bun. Il browser prelude è abilitato di default; il file esiste e un `createRequire(import.meta.url)` è già usato altrove nello stesso SDK. Il meccanismo interno che produce `from ''` resta un'inferenza, ma la chiamata e il failure mode sono osservati. Disabilitare il browser in produzione toglierebbe una capacità prevista; `toolNames: []` elimina le estensioni. L'alternativa più semplice utile è una correzione upstream pubblicata e verificata, ma non è disponibile nel pin18.8.7 qualificato; un upgrade routinario non è giustificato. Per sbloccare la missione locale, delimitare un patch vendor **temporaneo** con `bun patch` già fornito da Bun, mantenendo versione18.8.7: solo i require lazy relativi di browser (prelude e ARIA) e computer, con `createRequire(import.meta.url)`, senza nuove dipendenze o API. Rimuovere il patch quando upstream rilascia una correzione equivalente verificata. Proprietà del writer: worktree isolato da `56d7fb3`; file ammessi patch Bun, `package.json`, `bun.lock` e test esistente minimo pertinente. Nessuna modifica di Web UI, auth, deploy o Homelab.

RED è il raw `live-run-LYRBiC4F`; GREEN richiesta: test focalizzato del modulo patchato e sessione `ensure_session` reale, senza prompt/modello, con profilo usa-e-getta e preludes native ai default, estensione sintetica carica, status200 e decisioni pendenti. Poi typecheck, test e build pertinenti sul nuovo SHA; scope audit del lock/patch. Reviewer Osmani indipendente sullo SHA esatto, correzioni Required e re-review se materiali. Il PASS con preludes disabilitati non si trasferisce al default. Nessuna pubblicazione o deploy del candidato; il patch è reversibile e circoscritto al runtime locale di test.

Il primo tentativo `createRequire(import.meta.url)` con specifier relativo non risolve il problema nel server Next/Bun e torna lo stesso HTTP500 (raw `prelude-final-V2owkyS2`): la base effettiva del resolver resta vuota. L'implementer ha corretto il **percorso assoluto** con `fileURLToPath(new URL(..., import.meta.url))` conservando il caricamento lazy, nei soli quattro punti di browser/computer. Nel worktree isolato `task52-prelude-resolver`, candidato locale `bd102be67fc7735ac334cfc8529e3d80c7dee98a` su base `56d7fb3`, `package.json`/`bun.lock` mantengono OMP18.8.7 e aggiungono un unico patch Bun. Dopo reinstallazione offline/frozen, il raw `prelude-final-ozEcDyBu` registra build, typecheck,18 test focali e `ensure_session` default HTTP200 con due pending sintetici; la fixture chiama anche gli import ARIA/computer. Il warning export-route del build preesiste. Nessun push. La review Osmani indipendente sullo SHA è in corso: **nessun GO finale ancora**. GitNexus CLI offline ha indicizzato il worktree, ma i simboli del vendor patch sono fuori indice (`impact` UNKNOWN, `detect-changes` senza simboli); l'audit manuale dei caller e i test runtime sono evidenze distinte, non un esito di impatto GitNexus positivo. Il controllo d'impatto non ha preceduto il primo edit, fatto che resta dichiarato.

La review Osmani indipendente su `bd102be` conferma il raw HTTP200 soltanto per il checkout sorgente, ma classifica **Required per un rilascio npm/desktop**: `npm pack --dry-run` esclude il patch dalla whitelist `files`, npm non applica `patchedDependencies` di Bun e lo staging desktop non copia `patches/` prima dell'installazione frozen. Non pubblicare npm né costruire/consegnare un bundle desktop da questo commit; quei percorsi richiederebbero una correzione e prove proprie prima di essere scelti. Task52 resta nel perimetro locale da sorgente, senza rilascio. Il reviewer richiede inoltre una prova con `ensure_session` **senza** `toolNames` per attestare direttamente il set di capacità predefinito, oltre a due decisioni pendenti; il writer la esegue senza modello né modifica di codice e il reviewer esaminerà il raw sullo stesso SHA. Finché manca tale prova, nessun GO nemmeno per la qualificazione normale da sorgente.

La prova aggiuntiva `prelude-unrestricted-toICDaGa` sullo **stesso** `bd102be` omette `toolNames`: HTTP200, due pending `confirm`, `eval` attivo fra i tool, zero messaggi e nessun prompt/modello; la configurazione usa-e-getta cambia soltanto `dev.autoqa: false`. Il reviewer ha esaminato script, risposte e log e dà **GO circoscritto alla qualificazione del checkout sorgente locale**, senza dichiarare una propria ripetizione del servizio. Il tentativo JSON malformato `prelude-unrestricted-EblocZUo` resta errore separato. Il coordinatore ha integrato serialmente con fast-forward il commit esatto nel checkout `port/source` (HEAD ancora `bd102be`, tree pulito) e riallineato `node_modules` con Bun install offline/frozen; i quattro lazy load risultano presenti. Nessun push del codice, server in ascolto o deploy. La prossima dipendenza non è un'altra suite locale: servono ownership/delivery route durevole, prova di missione/identità, accesso Cloudflare con autorità del proprietario e dispositivo reale; npm/desktop rimangono vietati finché i rispettivi Required non sono corretti e riesaminati.

La verifica della [documentazione OpenAI corrente sul custom MCP](https://developers.openai.com/api/docs/guides/custom-mcp-server) conferma che ChatGPT web può selezionare URL o Tunnel e che l'aggiunta/uso restano soggetti ai permessi del workspace. Il [Secure MCP Tunnel](https://developers.openai.com/api/docs/guides/secure-mcp-tunnels) richiede un tunnel Platform associato al workspace corretto, permessi distinti Read/Manage per crearlo e Read/Use per eseguirlo, client outbound HTTPS e server MCP locale raggiungibile; trasporta richieste, non genera gli strumenti di missione né autorizza l'operatore. L'account e il workspace effettivi non sono stati interrogati/collegati. Quindi C1 richiede prima una prova supportata dell'identità del workspace e delle autorizzazioni, poi un server che implementi davvero il contratto di missione, con auth e lifecycle; il Cloudflare Tunnel del pannello non soddisfa né sostituisce questa corsia. Non installare `tunnel-client`, creare plugin o scegliere `No authentication` solo perché la schermata lo offre.

Il PO ha autorizzato la preparazione della custodia privata del codice e di una PR Homelab, senza apply, servizio persistente o deploy. GitHub [lega la visibilità di un fork all'upstream pubblico](https://docs.github.com/en/pull-requests/reference/forks); dopo approvazione esplicita dell'alternativa è stata creata una **copia Git privata autonoma**, non un fork GitHub, in [`skunklabs-uk/omp-web`](https://github.com/skunklabs-uk/omp-web). `main@0acce6240b27eb7d44d5c9b78187bd95e01270f8` conserva la base upstream MIT e il branch `codex/omp-18.8.7-startup-preferences@bd102be67fc7735ac334cfc8529e3d80c7dee98a` conserva il candidato revisionato; `isPrivate=true`, `isFork=false` e ref remoti verificati. GitHub Actions è disabilitato per il repository nuovo **prima** del push: l'upstream contiene CI su main/PR, publish su tag e un updater orario; nessun run è autorizzato in questa fase. Nessun merge del branch o rilascio npm/desktop; i Required di packaging restano aperti.

La ricognizione MCP read-only sullo stesso SHA trova un seam per riusare il registry RPC nello stesso processo `omp-web` (`lib/rpc-manager.ts`), ma `/api/mcp` è configurazione di OMP come *client*, non un server per ChatGPT. `POST /api/agent/new` genera un UUID nuovo a ogni richiesta e può duplicare lavoro dopo retry; registry e decisioni live sono in memoria, mentre il JSONL conserva solo parte dello stato. Il proxy usa Basic per il pannello, senza autorizzazione per repository/operazione: la [documentazione OpenAI sull'auth](https://developers.openai.com/plugins/build/auth) non consente di presumere che ChatGPT possa presentare quella credenziale. Dunque un handler MCP nello stesso processo è un'ipotesi tecnica, non una funzionalità già approvata: prima occorrono prova dell'account/workspace, idempotenza e identità durevole, auth/scoping e il task implementativo specifico con reviewer. Il tunnel sicuro da solo non risolve questi gap.

**Slice condivisa, prima di MCP o accesso remoto:** l'avvio di una missione identificata deve creare una sola sessione OMP e restituire lo stesso riferimento dopo retry/riconnessione, senza inviare un prompt prima che il binding sia durevole. Il requisito è nel contratto condiviso e il failure mode è osservabile nel nuovo UUID di ogni `POST /api/agent/new`; le lock attuali coalescono solo il singolo avvio e il nome modificabile della sessione non è un'identità. Riutilizzare `SessionManager`/JSONL e il registry già presenti, se bastano, prima di proporre un altro archivio; limitare l'incremento alla singola missione configurata nel laboratorio e al solo `ensure_session`, senza inferenza o comandi MCP. Un esito ambiguo deve essere `unknown`, non un secondo avvio automatico. [Task59](https://github.com/skunklabs-uk/agent-os/issues/59) possiede criteri, file e verifiche; questo piano non autorizza provisioning, autenticazione nuova o deploy.

Task59 ha ora un candidato nel branch privato OMP: [PR #1](https://github.com/skunklabs-uk/omp-web/pull/1) Draft, head `8143d5276661b5ec8b74d7e0acce5604b2cc230e` su base `bd102be`. Il primo head `6114b5` aveva un Required reale: il gate delle radici respingeva con 403 il primo avvio su repository pulito; il writer lo ha corretto e il reviewer Osmani indipendente ha riesaminato lo SHA finale senza Required/Critical. Il probe senza mock, ripetuto dal reviewer, ha osservato root inizialmente vuota, richiesta generica 403, missione configurata 200 due volte con identico ID e un solo JSONL. Test mirati, typecheck e diff-check sono PASS direttamente in review; il writer riporta suite completa 596 PASS / 1 SKIP / 0 FAIL e build isolata exit0 sullo stesso SHA. Questa prova locale non adotta sessioni storiche non marcate, non trasferisce l'ownership di #35 e non prova auth, accesso remoto, tablet o ChatGPT. Actions della copia privata restano disabilitate, quindi nessuna CI è attribuita alla PR; nessun merge o deploy. La prossima slice tecnica deve mantenere il medesimo riferimento di missione nelle operazioni di lettura/comando e introdurre identità/scope prima di MCP remoto, con task e review propri; il trasporto Cloudflare resta dipendente dal piano Homelab completo e da un successivo OK per applicarlo.

**Handoff OMP approvato, non ancora attivato.** Il PO ha scelto il trasferimento verificato di #35 a una nuova sessione OMP dedicata. Il coordinatore corrente resta unico proprietario fino a una sessione OMP file-backed che abbia letto e ricostruito #35, le SPEC Active, questo Plan, Task52 e i blocchi correnti; il marker `missionId+cwd` da solo non costituisce passaggio di consegne. Il worktree separato `mission/35-omp-coordinator` su NOVBSCWOLaulMaU era pulito al preflight su `c7f2cdcdaa7e82b9c8ac699f043f1053881728db`; il binario OMP18.8.7 corrisponde al digest ufficiale `b87f9835a0acdbb81bbbad8273aa2d999b608a208598421a9584cffeb3139a8a`. Il PO ha autorizzato **un solo turno** di lettura con `openai-codex/gpt-6.1-sol` low, massimo 10 minuti e 20 richieste modello, senza subagenti, scritture, servizi, deploy, retry o fallback; l'allowance storica del pilota non si trasferisce. L'accesso dal tablet e ChatGPT resta separatamente BLOCCATO finché non verificato end-to-end.

Il turno OMP delimitato ha usato la sessione durevole `01a131c7-ecba-7000-a4fb-ff906f642f4f` nel profilo privato `~/.local/state/agent-os/remote-control/mission35/agent`, con JSONL `sessions/-projects-personal-.worktrees-agent-os-omp-coordinator/2026-10-12T20-22-28-282Z_01a131c7-ecba-7000-a4fb-ff906f642f4f.jsonl` (SHA256 `e1b8be7a433f99d0f1b5f7026a904b55a4e87040337bc3ee95b60ad9cb87502e`). Il runner ha verificato il binding prima del prompt; un processo successivo senza modello ha ritrovato lo stesso ID, un marker e l'unico JSONL (`handoff/check-binding.mjs`, output `check-binding.json`, SHA256 `2873be338993f93cf8f36933add2887095447044ebb9018b69497097f6ab8c9b`). Il turno è terminato normalmente in circa 77 secondi: un prompt, 14 turni modello, 13 letture, zero retry automatici, nessun tool diverso da `read`, worker, servizio o modifica. La risposta ha ricostruito fase, fonti e blocchi e ha rifiutato esplicitamente di rivendicare l'ownership. Raw e runner restano privati in `~/.local/state/agent-os/remote-control/mission35/handoff/`; il log del turno ha SHA256 `5e0841acec5a8d452d86a40f76cfc5c7fef85545a236d4090b858df74b499dd8`. Le skill erano intenzionalmente disabilitate per quella sola lettura: non attribuirle al turno. Successivamente, senza modello, `omp skill list <worktree> --json` con `PI_CODING_AGENT_DIR` sul profilo privato ha prodotto `handoff/skills-resolved.json` (SHA256 `5235a9b6468f6e7ddcfc17ef674610c4b19e67d9386128c56908f3983fea1674`): 25 skill originali Osmani dal checkout al pin `1401c8b8030e023baeebb31781a6653fe8e93026`, incluso il router, zero warning e nessuna skill estranea nel risultato. L'invocazione effettiva di una skill in una futura sessione operativa non è ancora provata.

La review indipendente con contesto pulito, conservata in `handoff/turn-review.md` (SHA256 `d60ce7e19f30724157b1828c52396df3c427e476aad5b22d5e68af9e4cdf5c3f`), ha dato GO alla sola verifica documentale del primo turno, **NO GO al trasferimento di coordinamento**: il JSONL e il marker non contengono uno stato live affidabile di fase, approvazioni, decisioni e ownership; il runner non ha esercitato le skill; l'autorizzazione modello copriva quel turno soltanto. La distinta review indipendente del presente aggiornamento è conservata in `handoff/plan-diff-review.md` (SHA256 `2617995d69c8ee11b892cbe5a8013373c69569032aa751de1031c1a32d62e4af`); i suoi rilievi sulla provenienza del binding e del resolver sono risolti dai raw separati indicati sopra. Le nove fonti erano accessibili, ma alcuni output sono stati troncati e non costituiscono una rilettura esaustiva. Questa chat resta l'unico coordinatore. Prima di un trasferimento operativo servono una prova di continuità dello stato/decisioni e un limite operativo per i turni successivi, poi registrazione esplicita del passaggio e cessazione del coordinamento concorrente. Nessun accesso remoto, merge o deploy è implicato.

Il PO ha poi autorizzato **un secondo turno delimitato** sulla stessa sessione: lettura/stato con `openai-codex/gpt-6.1-sol` low, massimo 15 minuti/30 richieste, nessun worker, scrittura di progetto, servizio, deploy, retry o fallback. Il preflight separato ha verificato worktree pulito `a5c738beaee5c4a3a7d49b0d872e0990bee7cddd`, binario OMP18.8.7 al digest sopra e profilo AutoQA/retry disabilitati; il controllo successivo è conservato in `handoff/continuity-preflight.txt` SHA256 `9fd3e23ae4a216039f3b4e2824e3b96c3e9db94188405fd2020121f3c940b787`. Il runner ha ripreso l'ID `01a131c7-ecba-7000-a4fb-ff906f642f4f` e risolto 25 skill Osmani. In 91,694 secondi il nuovo transcript registra un prompt, 18 risposte modello, 17 chiamate `read`, zero retry osservati e nessun altro tool; le skill originali `using-agent-skills` e `planning-and-task-breakdown` sono state effettivamente lette al pin, senza rivendicare una slash invocation. Il candidato ha recuperato la conversazione precedente e distinto correttamente le decisioni live sconosciute da zero pending. Ha rilevato anche uno SHA di preflight trascritto con due caratteri in eccesso nel Plan; l'identità Git è stata ricontrollata localmente e corretta sopra. Raw privati: `handoff/run-continuity.log` SHA256 `458ef321a590adb680379823a3b41b150925d059250491305149779761892520`, JSONL aggiornato SHA256 `69cc9f643ce20be66a6e5ec9c3034b9f8b174619f6ca8b99f0ff1f06d4189fc6`. La review indipendente è conservata privatamente in `handoff/continuity-review.md` SHA256 `d2950e565a8e947b23fd7c3736e142173d403722f864d7d36af3ef9eed85d7e8`: **GO al solo turno read-only, NO GO al trasferimento**. La directory skill letta in modo largo era troncata e una prima lettura del contratto era fuori range, poi corretta; non presentare il turno come lettura esaustiva. L'allowance è consumata. Resta da osservare senza mutazioni lo stato OMP live con identità, fase, activity e pending ID/scope/revision prima di un eventuale nuovo limite operativo e passaggio esclusivo. Il semplice ripristino del contesto JSONL non soddisfa questo gate.

Il PO ha autorizzato separatamente **uno smoke locale temporaneo** del pannello, senza prompt/modello o accesso remoto. Sul sorgente privato OMP `8143d5276661b5ec8b74d7e0acce5604b2cc230e`, un build locale con Bun assoluto è PASS (warning preesistente di import dinamico in `app/api/sessions/[id]/export/route.ts`; log privato `handoff/omp-web-build-8143d5.log` SHA256 `bd758a57da11175060f3b0958a51cec1fbdddd23957cf8ac217df0aa84c58792`). Il primo comando di build aveva fallito solo perché lo script npm non trovava `bun` nel PATH; non è contato come build PASS. Dopo review preventiva, lo script ha superato il proprio controllo di namespace di rete separato e ha servito Next solo su loopback30143; il raw non attesta autonomamente il namespace PID o il watchdog complessivo, pur essendo stati impostati dal comando di lancio del coordinatore. `POST ensure_session` ha restituito l'ID #35 già marcato; `GET get_state` ha restituito lo stesso ID/file, `running:true`, nessun prompt in esecuzione e `pendingExtensionUiRequests:[]` **nel processo appena avviato**. I messaggi user/assistant nel JSONL sono rimasti 34; è stato aggiunto soltanto un `session_exit` al termine, senza nuovi messaggi modello. Log privato `handoff/mission-local-state-smoke.log` SHA256 `30c42408948da5d05986c2a0baede85dd2ab982e1006c972920bebe2fb54b0e7`, JSONL dopo lo smoke SHA256 `cb604b7734c339c001f1932c57593901d7e618185be6e4ceebc88f50a6f16cdd`; script SHA256 `73ca5a8b86b1abf4022991b2ced37b20eb7218b980c6a8cddc9a8e860da949e3`. La porta30143 non è rimasta in ascolto. `messageCount:0` nel `get_state` è un placeholder hardcoded del wrapper e non prova la perdita o il recupero della cronologia. La review indipendente conservata in `handoff/local-state-smoke-review.md` SHA256 `4ca174679371ef4d5abb14b2cb0525725ea1f81970e09453e03ac28d76fb2156` dà GO soltanto a questa prova locale di identità/stato istantaneo, NO GO all'ownership: l'avvio dispatcha `session_start` e può avere effetti non registrati nel transcript, mentre fase, attività, revisioni e decisioni precedenti non sono riconciliate. Non è prova di tablet, Cloudflare, ChatGPT/MCP o deploy.

La copia privata contiene ora la [PR OMP #1](https://github.com/skunklabs-uk/omp-web/pull/1), Draft su `8143d52` contro `main@0acce624`; è una superficie di review del port da sorgente e del binding locale, non approvazione npm/desktop o merge. GitHub Actions risulta ancora disabilitato e non ci sono run. Per il proprietario infrastrutturale, dopo controllo duplicati è stata creata solo la [issue Homelab #1514](https://github.com/skunklabs-uk/homelab/issues/1514) e la [PR Draft #1515](https://github.com/skunklabs-uk/homelab/pull/1515), base `300fe85abd686817dab2cfc154a1faeb5b70cef1`, head `cf618eec85f03a1e5515e4ee22f3089f96689f66`. Il diff a due file aggiunge tunnel named remoto, Access derivato dalla policy Developer Workspace, ingress solo `omp-panel.skunklabs.uk` verso loopback30141 con validazione AUD e CNAME dopo la configurazione protetta. Reviewer Osmani indipendente senza Critical/Required; la sua unica osservazione sul contesto loopback WSL è stata corretta e riesaminata sul nuovo SHA. `tofu fmt`, `git diff --check`, init e validate sul provider pin 5.26.0 sono PASS; i due check Trivy iniziali della PR sul nuovo head sono PASS, nessun rerun. Lo state operativo copiato in contesto protetto era serial 107: il piano completo **non è applicabile**, perché oltre alle quattro creazioni propone numerosi update DNS estranei già noti nel root Homelab. Il contesto temporaneo con input decifrati è stato eliminato; non è stato fatto apply né creato alcun tunnel/DNS/servizio. Risolvere quel drift con l'owner e rifare il piano completo prima di un eventuale OK distinto per deploy; non usare un target plan come finta prova del gate pieno. Restano non osservati policy effettiva, collisioni Cloudflare, disponibilità host dopo sleep/reboot, missione reale, HTTPS/SSE/POST e tablet fuori LAN.

### Prossima slice di sicurezza — scope della missione, Task60

L'audit read-only indipendente sul privato OMP `8143d5276661b5ec8b74d7e0acce5604b2cc230e` individua un blocco prima di qualunque esposizione remota: `proxy.ts` autentica l'operatore ma non limita missione e operazioni; la creazione generica senza `missionId`, i comandi per ID arbitrari e le route amministrative restano raggiungibili. Inoltre l'auth web può essere `open` in assenza di credenziale. Il contratto condiviso e le SPEC mobile/MCP richiedono una sola missione e rifiuto fuori scope. [Task60](https://github.com/skunklabs-uk/agent-os/issues/60) possiede criteri e file della slice fail-closed: in modalità missione, negare per default, conservare soltanto `ensure_session` esatto e letture dell'ID bound, senza mutazioni; configurazione parziale o auth aperta non devono aprire il pannello. Writer in worktree separato, RED/GREEN, controlli locali e review Osmani indipendente sul nuovo SHA. È un prerequisito tecnico, **non** accettazione del pannello: comandi con scope, UI/touch, decisioni durevoli, ownership, Cloudflare, tablet e ChatGPT richiedono prove successive. Nessun modello OMP, servizio, CI, merge o deploy deriva da Task60.

Task60 ha ora il candidato verificato `df3e8d86af0afa9c3c976c2be291d46d37136313` sulla [PR OMP #1 Draft](https://github.com/skunklabs-uk/omp-web/pull/1), base di slice `8143d5276661b5ec8b74d7e0acce5604b2cc230e`. La prima review su `0944cd4` ha individuato un Required reale: la GET SSE a freddo avviava il wrapper e poteva emettere `session_start`. Il nuovo head restituisce 409 senza avviare OMP se il wrapper della missione non è vivo; la SSE live e la modalità non-missione conservano il comportamento precedente. Re-review Osmani indipendente sul nuovo SHA: nessun Critical/Required residuo nello scope, test focali ripetuti e `git diff --check` pulito. Writer: RED/GREEN, typecheck, lint dei file modificati, probe reali senza modello, suite finale 601 PASS / 1 SKIP / 0 FAIL e build PASS, con warning export già noto. Il primo giro completo dopo il fix ha fallito per timeout di una fixture SSE non modificata e conseguente SIGTERM di un child; log originale conservato, test isolato e retry della suite PASS. Il lint completo resta FAIL per sette errori e due warning React in file non toccati; non attribuire un PASS globale. Raw privati `~/.local/state/agent-os/remote-control/mobile-compat/port/logs/task60/`. La PR è ancora Draft, Actions disabilitate e senza run; nessun merge o deploy. Dopo restart, la SSE bound risponde 409 finché `ensure_session` autenticato non riattiva il wrapper. Questa slice non qualifica HTTP live, pagina UI, comando remoto, stato storico delle decisioni o accesso tablet/ChatGPT; la modalità missione nega il resto dell'API e quindi richiede un successivo percorso UI/comandi esplicitamente scoped prima dell'uso remoto.

### Prossima slice mobile — vista missione in sola lettura, Task61

La ricognizione sul nuovo head OMP conferma che `AppShell` e `useAgentSession` ordinari dipendono da API ora vietate e dal bootstrap di sessioni generiche: sbloccarli integralmente aggirerebbe il gate. Il wrapper offre attività, specialisti e ID pending solo nello stato live; il marker non conserva fase, metodo, ownership o decisioni. [Task61](https://github.com/skunklabs-uk/agent-os/issues/61) delimita una root autenticata e una proiezione minima del solo ID bound, con stato sconosciuto/non aggiornato esplicito e senza auto-`ensure_session`. Writer separato, test locali e review indipendente; una prova browser richiede distinta autorità operativa. Il percorso dei comandi/approvazioni richiederà successivi task e la verifica dell'ownership OMP; l'allowance dei due turni modello non si trasferisce a questa UI. Nessun accesso fuori rete o deploy è autorizzato da Task61.

Il codice di Task61 è ora nel ramo della [PR OMP #1 Draft](https://github.com/skunklabs-uk/omp-web/pull/1) a `dc8cee17ed662a4c732c5b202c9cb9f3888f66e5` (base di slice `df3e8d86af0afa9c3c976c2be291d46d37136313`). Due candidati intermedi non hanno avuto GO: `ef625a7` lasciava live uno snapshot dopo una fetch sospesa e mancavano test comportamentali; `a2c87fe` convertiva campi runtime assenti in falsi/array vuoti e usava testo che attribuiva senza prova la perdita del contatto. Il writer ha aggiunto deadline, abort, controllo dell'età della risposta anche con timer sospesi, proiezione rigorosa e test fake-clock/fetch; il reviewer Osmani indipendente ha riesaminato l'head finale senza Critical/Required nel codice. Verifiche sull'esatto head: typecheck exit0, lint dei file cambiati exit0 (ripetuto anche dal coordinatore dopo l'integrazione fast-forward), suite Bun607 PASS / 1 SKIP / 0 FAIL, build Next exit0 in275,53s con warning export preesistente; `git diff --check` e worktree puliti. I primi run della suite erano FAIL per leak di mock e poi timeout sotto build concorrente; i build intermedi terminati con exit143 non sono PASS. Raw privati `~/.local/state/agent-os/remote-control/mobile-compat/port/logs/task61-*.log`; il build ha generato solo include temporanei in `tsconfig.json` e output `.next-task61`, rimossi dopo controllo. Actions della PR restano disabilitate, zero run; nessun merge o deploy. La pagina è osservativa, non consente ancora resume da UI, comandi, risposte o approvazioni, e non prova il trasferimento della coordinazione a OMP.

Il PO ha autorizzato un nuovo smoke HTTP locale una tantum sull'head `dc8cee1`. Il build isolato `.next-mission-smoke` sullo SHA esatto è PASS, log privato `handoff/status-smoke/build.log` SHA256 `9e753db59124cfb7163da1f72bb4afa1cfb80f7401cc1c3ef459dd0368a846e3`; il primo comando di invocazione aveva fallito per PATH WSL e non è contato come PASS. Lo script `handoff/status-smoke/run.sh` SHA256 `6974c9fb553a9066d6adb388ecac94e2ff76d4e23625dc18383103493e9bc60d` è stato lanciato dal coordinatore con `unshare -Urnpf`, watchdog 240 secondi, controllo di namespace distinto/sola interfaccia `lo` e Next su `127.0.0.1:30143`. Exit0 in circa cinque secondi; `run.log` SHA256 `38ced5444b0c9e682fe34ca06cfba769c83358b840469b3f7d6a0229a9a44517`. Root anonima 401, root autenticata 200 con missione e ID bound, GET cold `unknown`, `ensure_session` restituisce lo stesso ID, GET live contiene solo la proiezione prevista; ID estraneo, API amministrativa e POST comando hanno dato 403. Dopo il run nessun listener su30143; il JSONL ha ancora 34 messaggi user/assistant ma un nuovo record `session_exit` (SHA256 finale `a94c61db4e0a89576ba7be1e948aa07e855f715572d4e0175723b5ce3ef86524`). Il server ha dispatchato `session_start`: la prova **non** dimostra assenza di altri effetti delle estensioni. La review indipendente `handoff/status-smoke/review.md` SHA256 `d3db607283efa68e78621d735d2ea9e27a9bdfcae720bc53790491038cdddde3` concede GO solo a questi fatti HTTP locali, NO GO all'accettazione mobile; non è stato provato browser/hydration/polling reale, pending non vuoti, tablet, Cloudflare, ChatGPT/MCP o ownership. Il raw del comando launcher/watchdog non è conservato separatamente dallo stream del coordinatore, perciò l'isolamento osservato è supportato da script/comando e controlli ma non da una traccia kernel autonoma. [Task61](https://github.com/skunklabs-uk/agent-os/issues/61#issuecomment-6139080267) è chiusa come slice limitata, mentre la missione #35 resta aperta ai gate successivi.

### Slice mobile — ricollegamento esplicito della vista, Task62

L'audit read-only successivo a Task61 ha confermato che la UI osserva la sessione bound ma non offre l'azione esplicita già presente nell'API per ricollegare il wrapper dopo restart; non sono emersi task duplicati. [Task62](https://github.com/skunklabs-uk/agent-os/issues/62) possiede la slice. Un writer nel worktree `mission-reattach` ha aggiunto soltanto il pulsante manuale e test a `MissionStatus.tsx`, senza cambiare l'endpoint: invia l'esatto `ensure_session` configurato, blocca il doppio tap, accetta solo l'ID bound e riavvia la lettura GET; timeout, auth negata, mismatch o esito ambiguo non diventano live. La review Osmani indipendente ha dato GO al codice iniziale `882db6a`, poi NO GO alla frase troppo categorica su `59eb3e1` (gli effetti di `session_start` non sono completamente provati), infine GO al testo qualificato e ai controlli sull'esatto `f7338b746602e40f888996350502ce8dc8ed4cf6`, senza Critical/Required residui. Il nuovo head è stato integrato per fast-forward nella [PR OMP #1 Draft](https://github.com/skunklabs-uk/omp-web/pull/1), Actions ancora disabilitate/zero run, nessun merge o deploy. RED e GREEN focali conservati; suite finale 611 PASS / 1 SKIP / 0 FAIL, typecheck, lint mirato, build isolato e diff-check exit0. Il build su `59eb3e1` interrotto dopo il finding exit130 non è PASS. Manifest privato `~/.local/state/agent-os/remote-control/mobile-compat/port/logs/task62/final-verification-manifest.txt` SHA256 `099718303515f5465d32864ba783b05b108bad858b47bb285a7aade29a7dff3c`, review `review.md` SHA256 `20a116a5e69dc4ca10713c2734668769fecfd6d676506f4c7ec5fcdb2f505709`. Al checkpoint del codice, nessun tap in browser, runtime reale #35, tablet o MCP era stato provato. Il ricollegamento non conferma la ripresa del lavoro, fase, ownership o decisioni storiche.

La prova browser locale autorizzata è stata eseguita sul medesimo head `f7338b746602e40f888996350502ce8dc8ed4cf6`, con Chrome headless a viewport 820×1180, profilo e missione sintetici, Next su loopback in namespace isolato e nessun prompt/modello. Il primo avvio si è fermato **prima di Chrome** per `ERR_REQUIRE_ESM` nello script di prova; non è un PASS del prodotto. Corretto il solo import dello script e ottenuta l'autorizzazione a un nuovo avvio, il run `handoff/browser-smoke/run.X2uF53` è terminato con exit0: cold `unknown` senza POST, tastiera/focus sul pulsante, un tocco emulato e un solo `POST ensure_session` per l'ID bound, successiva osservazione `live`, poi `stale` immediato dopo GET503 iniettato. Le 20 richieste browser sono rimaste su loopback; il server ha comunque dispatchato `session_start`. Un solo JSONL sintetico, tre record e zero messaggi user/assistant; nessun listener/processo residuo. Raw e screenshot autentici restano privati nella directory del run: `browser-results.json` SHA256 `c30b3c39d4bf1908a2e2676f24585952ba0d7618bde1edf29dc80bc4f445a978`, schermate cold/live/stale SHA256 rispettivamente `4bc13aaa7a38512975ffd09adce126bd7b9f005ae543b9d95b4737509adb9e87`, `b4430d9f5d157b49184c2c03928169cc3055ec6377a48e026b45baaa5e42ee79`, `6a1143ad235003b6436ac13481afa303f2fc0b2a7524760611ca3a526ed4aca1`. Review indipendente `handoff/browser-smoke/runtime-review.md` SHA256 `d4258bd2476e82341abe186dd0add500d717f1fc5c9281021ef49f8a5beda78a`: GO solo al flusso locale cold→touch→live→stale, nessun Required/Critical nello scope; NO GO ad accettazione mobile/deploy. La pagina è ancora diagnostica e austera, giudicata 2/5 per adeguatezza all'utente; non è prova da tablet reale, Cloudflare/Access, ChatGPT/MCP, ownership #35 o decisioni storiche. Il controllo usa CDP/Puppeteer, non il server Chrome DevTools MCP nativo.

La ricognizione successiva, in sola lettura, ha classificato **READY soltanto la riconciliazione delle fonti in Task52; BLOCCATI comandi, approvazioni e accettazione mobile**. Il marker JSONL identifica missione/cwd/sessione ma non trasferisce ownership; il Plan `c685d41` documenta Osmani, fase Tasks/readiness e questa chat come coordinatore; il worktree OMP, inizialmente fermo a `ca8a900`, è stato poi allineato con fast-forward a `4ed6750` senza modifiche locali; il suo aggiornamento futuro resta esplicito. Lo stato live del wrapper fornisce attività e specialisti, ma dopo restart torna sconosciuto. Le richieste UI native e lo snapshot del wrapper hanno ID/metodo/scadenza, non scope e revisione strutturati; il JSONL storico non ricostruisce pending live. `get_state` completo contiene dati interni e non va pubblicato. Non proiettare metodo/fase/owner documentali come stato runtime corrente né una lista pending vuota da processo nuovo come assenza di decisioni precedenti. Prima di aprire una slice di comando o una proiezione decisionale completa, occorre identificare il collegamento autorevole a ownership e richiesta esatta con scope/revisione, senza un nuovo ledger se le fonti esistenti bastano. Il solo bootstrap di sessione vuota non è avvio del lavoro. Il pannello diagnostico valutato 2/5 resta una criticità di consegna, da correggere insieme a uno stato/azioni veritieri prima dello smoke tablet. La ricognizione MCP conferma separatamente che `app/api/mcp/route.ts` configura OMP come client, non è un server ChatGPT; C1 resta BLOCCATO per verifica del workspace/permessi e del percorso autenticato, senza installare o esporre un bridge. La [PR OMP #1](https://github.com/skunklabs-uk/omp-web/pull/1) Draft è stata riallineata al vero head `f7338b7`, mantenendo espliciti i gate aperti.

### Verifica dell'account ChatGPT e prossimo confine MCP — 2026-10-13

Il PO dichiara di usare il workspace ChatGPT **Personale**. Tre schermate autentiche, finalmente lette dal filesystem locale, mostrano nel client ChatGPT l'opzione `Tunnel` selezionata con campo `tunnel_...` ancora vuoto, e in Platform una lista «No tunnels yet» più il modulo «Create tunnel» con una organizzazione personale e un workspace ChatGPT selezionati. Le schermate non dimostrano che l'ID scelto in Platform corrisponda al workspace attivo in ChatGPT, né che la creazione sarebbe accettata dal server; il pulsante `Create` è disabilitato perché nome e descrizione sono vuoti. Raw privati in `~/.local/state/agent-os/remote-control/mcp-account-check/`, digest SHA256 rispettivamente `9fd9fce8e3ccc2024411b39866bcf85ff767823528a18a4f67e8544972ce5ff7`, `2213a41acbea09bb4908d04b91eb5b47dc648fe6f922ed23cce55d3ae3ed32e6` e `0ec6be7c2892ccc2f5212d406073ddf70fea106a0dd94cc8622f40bca404e906`. Durante questa verifica non abbiamo creato tunnel, plugin, chiavi o server. **PASS:** disponibilità del form nel client/Platform e workspace dichiarato. **BLOCCATO:** permesso effettivo, collegamento, auth e prova dal tablet fuori LAN.

L'audit indipendente sul candidato OMP `f7338b746602e40f888996350502ce8dc8ed4cf6` conferma una strada **solo locale e read-only** per una prima slice MCP: route nuova nello stesso processo Bun/Next, distinta da `/api/mcp` (che configura OMP come client), lookup della missione già vincolata tramite `lib/mission-session.ts` e del wrapper vivo tramite `getRpcSession`, proiezione dei soli campi sicuri già usati da `GET /api/agent/[id]` dopo estrazione di una piccola funzione condivisa. Nessun bootstrap automatico, prompt, comando o stato documentale spacciato per osservazione runtime. Il SDK TypeScript MCP v2.3.1 offre un [handler HTTP Request/Response](https://github.com/modelcontextprotocol/typescript-sdk/blob/v2.3.1/docs/serving/http.md), ma l'innesto in Next/Bun non è verificato. Il proxy attuale applica Basic e una allowlist di missione a `/api/*`; le [opzioni documentate per il custom MCP ChatGPT](https://developers.openai.com/api/docs/guides/custom-mcp-server) sono OAuth, nessuna autenticazione oppure OAuth facoltativo, non Basic o un header API key personalizzato. La futura route richiederebbe quindi un raccordo di autenticazione e un aggiornamento esplicito dell'allowlist che conservi host e scope esatti. Spostarla fuori dal matcher per eludere i controlli è escluso. Una slice esecutiva richiede prima un task con file, dipendenza e test esatti e il raccordo di autenticazione approvato nel suo perimetro; la proposta di status-only non soddisfa da sola delega, decisioni o interruzione della SPEC. Un tunnel futuro è solo trasporto, non autorizzazione dell'operatore. #52 conserva questa preparazione; non si crea un task duplicato né si anticipa la dipendenza MCP prima della decisione sul confine di auth.

### Terzo turno OMP di preparazione handoff — 2026-10-13

Il PO ha autorizzato un solo altro turno sulla **stessa** sessione #35 `01a131c7-ecba-7000-a4fb-ff906f642f4f`: `openai-codex/gpt-6.1-sol` low, massimo 15 minuti/30 richieste, sola lettura, senza subagenti, scritture di progetto, servizi, tunnel, deploy, retry o fallback. L'autorizzazione è **consumata**. Il preflight ha trovato il worktree OMP pulito a `b0b4db9f83d5277bea2700ff6d5335a84f7b27f5`, OMP18.8.7 e le due skill Osmani lette al pin `1401c8b8030e023baeebb31781a6653fe8e93026`; il runner ha controllato il livello low. L'esecuzione è durata 2m48s: 16 turni modello, 15 chiamate `read`, zero retry osservati, nessun altro tool nel delta JSONL. Le 104 righe iniziali corrispondono byte per byte al transcript precedente; le 49 nuove contengono un prompt, letture, risposta e `session_exit` normale. Il log privato `handoff/run-handoff-prep-turn3.log` ha SHA256 `3a94ce257c503f3217866e6dc7cbcd8fa34e946f335ad1b8b18f37136b4260ab`; JSONL finale SHA256 `d1329031fb1abed4a51106c41bf53fb265b25c843597595b4cf85c7823a0bb6b`. Il worktree è rimasto pulito. Le letture iniziali delle issue erano troncate; i commenti recenti sono stati recuperati, ma i body non sono stati interamente riverificati. Non si attribuisce al turno una slash invocation delle skill o assenza assoluta di effetti di inizializzazione runtime.

La review indipendente privata in `~/.local/state/agent-os/remote-control/mission35/handoff/turn3-runtime-review.md`, SHA256 `dbbe49387b8383b6f2d22c4e16a82698217b83a2104e17e1745c7aac03f10a25`, dà **GO alla sola ricognizione read-only, NO GO al passaggio di ownership**. L'output del launcher mostrava `turn_exit=0`, ma il wrapper del tool riportava `exit_code:1`: la discordanza resta irrisolta, mentre log e `session_exit` attestano la fine del turno OMP. Non sono stati osservati nello stato live fase, attività e pending con ID/scope/revisione; né la continuità delle decisioni dopo restart, né una registrazione di esclusività e limiti per turni operativi successivi. Il marker/JSONL non colmano queste lacune. **Codex rimane l'unico coordinatore**. Prossima azione indipendente: ricostruire nelle fonti esistenti il legame fra decisione, scope e revisione e delimitare una prova live che possa confutarlo, senza aprire un secondo ledger o avviare un modello sotto l'allowance consumata. Comandi, approvazioni, tablet fuori LAN, ChatGPT/MCP, merge e deploy restano fuori da questo GO.

### Ripresa Codex e correlazione decisionale — 2026-10-13

La richiesta corrente del PO autorizza la correzione locale del gap in Task52 e gli incrementi necessari del pannello entro lo scope approvato. Il remoto `docs/mobile-mcp-plan` coincide con `1403d832124605a7d1aed55fd512d81dde3d4c9b`; OMP PR1 Draft coincide con `f7338b746602e40f888996350502ce8dc8ed4cf6`. Homelab PR1515 Draft resta a `cf618eec85f03a1e5515e4ee22f3089f96689f66`, mentre main è avanzato a `61f292721ae63c642fe2eb6d0efa5eb102a6341d`: il vecchio full plan non autorizza operazioni sullo stato corrente. IWANT PR640 è OPEN/Ready a `f8b342b82716b6e319bfef67814eee9d9ff0b9c6`, senza autorità di merge. Actions OMP disabilitate, verificate via API.

Questo Plan è la fonte documentale di missione, coordinatore, ruolo della sessione OMP e scope. I quattro campi espliciti sopra rendono verificabili decisioni già acquisite; non attribuiscono ownership a OMP né autorizzano esecuzione. La richiesta del PO e le decisioni #35/#52 prevalgono sulla mera presenza di marker, JSONL o configurazione. Il terzo turno OMP è consumato; nessun altro turno, servizio, tunnel, deploy o apply è incluso.

**Necessità e perimetro minimo del fix:** il contratto provider già richiede richiesta esatta, scope e revisione. La fixture documentata in #52 ha mostrato 14 PASS/1 FAIL: stesso ID e piano, HEAD avanzato, approvazione erroneamente applicata. Il controllo esistente confronta contenuto e PlanModeState ma non la revisione Git. Eliminare le approvazioni non soddisfa il requisito; il riuso di pending ID, Plan e Git è sufficiente senza nuovo ledger, database o policy engine. KEEP pending vivo e guard del piano; REPLACE l'identità incompleta con il confronto della revisione applicabile e della fonte corrente. Costo: helper minimo nel port, wrapper, test comportamentali e README; nessuna dipendenza o stato durevole nuovo nell'incremento A. Owner del codice: writer isolato; delle fonti condivise: coordinatore OMP corrente. Il controllo resta finché esistono approvazioni scoped; si rimuove solo con un equivalente provider nativo verificato.

**Incremento A, Task52:** catturare HEAD e contesto della proposta prima dell'attesa; prima di applicare la risposta confrontare richiesta/sessione, piano, contesto e revisione corrente. Qualunque configurazione missione attiva o incompleta mantiene il divieto di approvazioni in questo incremento. La review ha eliminato il parser del Plan privo di effetto osservabile: non serve classificare observer/unknown per respingerli entrambi. Dopo restart un vecchio ID resta non applicabile; pending vuoti non attestano continuità. Nessuna API di missione viene aperta da A.

**Verifica:** conservare il RED riportato dal PO senza rilanciarlo per conferma; aggiungere regressioni focali per revisione e authority mismatch, poi GREEN, typecheck/lint pertinenti e smoke diretto del wrapper con repository usa-e-getta. Test e smoke sintetici non sono stato OMP vivo. Un reviewer indipendente esamina ogni SHA materiale prima dell'integrazione seriale. Limiti locali già approvati: zero inferenze, rete isolata, massimo10min per comando e40min per checkpoint; nessuna nuova installazione o CI. Prova live e browser applicativo richiedono una nuova autorizzazione delimitata, distinta dai precedenti avvii una tantum.

**Dipendenze:** A → comandi/pannello scoped → prova live autorizzata. In parallelo resta autorizzata la preparazione read-only di OAuth/account MCP e drift DNS con l'owner Homelab. Nuovi accessi, autenticazione operativa, risorse, merge, deploy/apply e smoke dal tablet restano gate distinti; #35/#52 restano aperte.

### Decisione concorrente precedente — superseded

Un'altra sessione ha registrato **«Codex unico, Osmani»** dopo aver rilevato le modifiche OMP/Pocock. Questa nota ricostruisce il conflitto; è stata superata dalla successiva decisione esplicita del Product Owner a favore di OMP/Pocock in questa chat, riportata sotto. Non governa il coordinatore o il metodo correnti. Nessun processo estraneo è stato terminato o modificato.

Il PO ha anche approvato il raccordo di codice **OMP esecutore sotto Codex**: nessun trasferimento della missione né secondo coordinatore. La sessione già qualificata resta observer finché un incarico e la relativa autorità operativa non sono attivati esplicitamente. L'approvazione del raccordo non concede nuovi turni modello o avvii della vera #35.

Nuova prova autorizzata: **un solo avvio app/browser locale, massimo240s**, namespace rete/PID isolato, loopback, repository/profilo usa-e-getta, decisioni native sintetiche e Chromium già installato, senza inferenza, tunnel, CI o deploy. Questa autorità è distinta dal terzo turno OMP consumato; l'esito verrà registrato solo dopo l'esecuzione.

Il PO richiede di riusare i sistemi Homelab prima di proporre un issuer esterno. Inventario sulla revisione corrente `61f2927` e documentazione primaria hanno identificato **Cloudflare Access Managed OAuth**, n8n MCP/OAuth nativo e Dex incluso in ArgoCD, non tre issuer esterni già qualificati per Agent OS. L'opzione Managed OAuth è il primo riuso da qualificare; Auth0 non è selezionato. API delle app esistenti non espongono `oauth_configuration`: assenza del campo non prova enablement né diniego. Permessi/associazione Platform e ChatGPT restano esterni al repository.

### Comandi dell'esecutore subordinato — perimetro di codice approvato

Il raccordo non crea un secondo coordinatore. Il coordinatore OMP corrente assegna nel Plan l'incarico dell'esecutore e le operazioni consentite; i campi mantengono observer/observe finché il trial reale non qualifica una nuova autorità. La UI distingue questa authority documentale dallo stato osservato, senza dichiarare ripresa della missione dopo un semplice `ensure_session`.

**Incremento B, Task52:** riusare binding, registry e native SessionManager per i soli comandi start/resume, stato/risultati, risposta esatta a domanda/decisione, direzione e interruzione dell'incarico OMP autorizzato. L'owner è il coordinatore OMP corrente. Ogni mutazione richiede missione, ID bound, scope, revisione e fonte Plan correnti; ruolo observer, fonte ambigua o revisione cambiata sono respinti prima dell'invio. Una decisione resta associata al pending vivo e al contesto mostrato; dopo restart non ricostruirne l'autorità dai marker.

**Ricezione ed esito:** una risposta HTTP positiva attesta ricezione, non completamento. Riutilizzare eventi nativi e sessione durevole per la prova dell'esito; un riferimento stabile di comando deve sopravvivere a riconnessione senza ripetere un prompt. Un eventuale record nativo di ricezione è tracciabilità del comando, non ownership o crash recovery. Se manca l'esito dopo restart, riportare unknown e non ripetere automaticamente. Nessun database, scheduler o secondo ledger.

**Incremento C:** UI nello stesso pannello, con identità/authority, attività degli specialisti e risultati, domande e decisioni raggiungibili, operazioni consentite e conseguenze visibili. Nessun bootstrap o prompt su render/poll; doppi tap, richieste stale e risposta di rete ambigua non devono avviare lavoro duplicato. Touch, tastiera, focus, reflow e screenshot autentici si verificano nel nuovo smoke autorizzato. Quella prova resta sintetica e senza inferenza; avvio/ripresa vera di #35, risultati lunghi, interruzione attiva e tablet richiedono i rispettivi limiti operativi.

**Necessità e costo cumulativo:** le API generiche attuali non identificano l'incarico e `prompt` risponde prima dell'esito nativo; riaprirle integralmente viola il confine già approvato. KEEP wrapper/registry/pending/SessionManager; REPLACE solo il dispatch generico per la missione con allowlist e correlazione native. I consumer web/MCP useranno lo stesso provider, non implementazioni autonome. File applicativi strettamente pertinenti saranno delimitati dal coordinatore sul nuovo SHA A revisionato, poi writer isolato, verifiche focali/smoke e review indipendente. Nessuna nuova dipendenza, installazione o esecuzione di modelli deriva da B/C.

### Decisione corrente dopo il conflitto — OMP/Pocock

Dopo la segnalazione della modifica concorrente, il Product Owner ha scelto
**«OMP/Pocock in questa chat»** come coordinatore unico. La sessione corrente
è `01a136e1-3183-72bb-aeca-d82f1bc60b6c`; la sessione Codex concorrente deve
cessare le scritture sulla missione. Il Plan conserva la storia senza
attribuirle autorità futura. Il provider file-backed rimane observer e non
si identifica con questa sessione di coordinamento.

Il Product Owner ha scelto **Cloudflare Access Managed OAuth + URL** per MCP:
riuso di Admin Only e dell'app OMP, nessun issuer custom o chiave OpenAI di
trasporto. La prima slice C1 implementa solo `mission_status` nello stesso
processo Next/Bun, senza bootstrap o trasferimento di ownership. I comandi
residui B/C e la prova nel client reale restano necessari al completamento.

È acquisito il **rilascio operativo condizionato** delle sole quattro risorse
OMP e dei servizi pannello/connector nello stesso WSL, dopo review sullo SHA
esatto e check applicabili verdi. Nessun cambiamento a cluster o altri servizi.
Il full plan provider 5.28.0 sullo state108 contiene 4 create/77 no-op,
nessun update/delete; hash e custodia restano nel runbook Homelab autorevole.
Il vecchio piano1515/107 non è recuperato e non viene equiparato a quello nuovo.

Nuova allowance del provider: **massimo15 minuti / 30 richieste modello**,
`openai-codex/gpt-6.1-sol` low, credenziali esistenti, zero retry/fallback.
È un limite operativo, non monetario. Prima del trial configurare solo il
catalogo Pocock qualificato, leggere le fonti correnti e verificare identità,
fase, scope e decisioni; niente ownership concessa da un marker. Conservare
l'esito effettivo e riesaminarlo indipendentemente prima di passaggi live.
Lo smoke autentico tablet/ChatGPT rimane distinto dalle prove del coordinatore.

Il PO ha autorizzato una deroga circoscritta al gate GitNexus del port: in questo
runtime non sono disponibili server MCP, binario o indice; anche LSP TypeScript
è assente. La qualificazione usa riferimenti e callsite verificati, typecheck,
smoke comportamentali e review indipendenti sullo SHA esatto. Non si installano
tool o indici e non si attestano controlli GitNexus non eseguiti.

Il PO ha scelto **JWT Access anche per il browser della sola missione**:
nessuna password aggiuntiva o fallback Basic. L'app verifica firma, issuer,
AUD, scadenza e identità utente; mantiene Host/Origin e allowlist bounded.
La modalità ordinaria di omp-web conserva Basic e recovery. Prima di questa
scelta i tre store previsti non contenevano una password nativa. Il nuovo
comportamento richiede check e review dello SHA aggiornato, non trasferisce
le review dell'incremento precedente.

Il profilo privato mantiene i 27 skill originali e i sei role model
`openai-codex/gpt-6.1-sol:low`. WebSocket prewarm e listing automatico delle
skill sono disattivati con impostazioni native: quest'ultimo schedulava
inferenze one-shot per comprimere descrizioni prima della costruzione
dell'agent. Discovery e `skill://` restano reali; nessuna cache fittizia,
copia di skill o modifica al profilo globale. La scelta serve al bootstrap
senza inferenza, non attesta l'applicazione del metodo al trial.
`onFirstChatDispatch` registra soltanto il primo dispatch e le sue eccezioni
sono catturate dal SDK: non è un contatore o un limite delle 30 richieste.
Il conteggio del trial deve comprendere anche richieste secondarie e retry
HTTP; resta una frontiera da qualificare prima dell'inferenza.

Cloudflare `a57e2ed6464a26275a1f423fde487db0d801345c`: review Pocock Standards
e Spec entrambe GO; i due check Trivy del run `38478963891` sono SUCCESS sullo
stesso head. Nessun apply. Checkpoint port `eaf2582`: 635 PASS, 1 skip, 0 FAIL,
typecheck e lint pertinente verdi, build verde con warning nella route export
non modificata. Il successivo `d014caf` integra JWT browser e due fix lifecycle
con RED/GREEN: non completare al primo `agent_end`; rispondere alla domanda
nativa di startup senza restare dietro la readiness che essa sblocca.
Focali e typecheck di quest'ultimo candidato sono verdi; nuova build, superficie
browser e review finali restano da eseguire. Lo smoke autentico del dispositivo
e di ChatGPT non è sostituito da queste prove.

Dopo l'indagine dei retry indipendenti del SDK, il PO ha scelto **«Tentativi
nativi inclusi nel cap»** per il trial. Questa decisione supera il precedente
zero-retry end-to-end: ogni dispatch HTTP modello, compresi retry interni e
chiamate secondarie, consuma il massimo30 entro15 minuti. Restano vietati
retry manuali e fallback. Prima del provider reale occorre provare counter
globale/deadline e copertura dei binding di fetch su endpoint locale, senza
crediti. I turni e i soli span non attestano questo conteggio.

### Ripresa e raccordo del candidato — 2026-10-14

La PR Homelab1515 è **merged** a
`c766e746703501073e71472ed5787ec144c18acf`: il merge ha vincolato
`a57e2ed6464a26275a1f423fde487db0d801345c`, già coperto dalle due review GO
e dai check Trivy indicati sopra. Questo completa la consegna IaC,
**non l'apply**: nessun servizio o risorsa OMP è qui attestato come attivo.

Il candidato port `8f8e91811500cd3e9a4e328276a360adc3f962a8` ha
628 PASS, 1 skip, 0 FAIL nella suite finale; typecheck, lint pertinente e
build sono verdi. Il browser sulla build Next reale, senza modelli, ha
mostrato rifiuto della conferma e risposta editor applicati alla sessione
nativa originale, senza overflow a 390 e 820 pixel. L'approvazione finale
del piano **non è provata**: la fixture è scaduta prima della lettura
dell'esito. Queste prove non sostituiscono tablet o ChatGPT personali.
Le due review finali non hanno restituito un verdetto per
`turn_rate_limit_exceeded`: nessun GO trasferito dal checkpoint precedente.

Il remoto privato `custody` conserva il candidato concorrente della PR1
`7373c4e2a3c48b3d3d4e5b97df36ca50b7637dc7`. Non è sovrascritto.
Le correzioni di admission/outcome nei commit `63a88c4` e `c5f3111`
sono confrontate con il provider locale prima della qualificazione finale.
La dichiarazione Codex/Osmani del checkpoint concorrente non supera
la scelta esplicita OMP/Pocock del PO riportata in questa fonte e nel
commento #35 `6155470815`; non si termina alcun processo altrui.

**Cap temporaneo, owner coordinatore OMP:** il limite approvato non è
coperto dal solo primo dispatch, dai turni o da `retry.enabled:false`.
Il SDK mantiene retry HTTP autonomi e richieste secondarie; si riusa
il binding fetch nativo con un preload locale, senza proxy, nuovo
ledger o modifica del SDK. Il beneficio da provare è bloccare ogni
dispatch modello oltre il cap/deadline, compresi quelli secondari.
Il preload viene rimosso alla conclusione del trial; non diventa
infrastruttura permanente. La qualificazione della copertura resta
necessaria prima dell'inferenza.

Sul solo loopback isolato il counter ha osservato: cap30 con 30 POST
fisici e blocco del31; deadline25ms con una richiesta ammessa,
abort e blocco successivo; retry503 con3 POST fisici e3 conteggiati;
errore SSE con2 POST fisici e blocco del terzo al cap2. Nessuna
richiesta a pagamento. Il modello della fixture è materializzato
dal builder nativo: il precedente oggetto incompleto falliva prima
del trasporto e non qualificava i retry.

**Retro intermedia:** la correzione richiesta è chiudere il ciclo
comportamento → prova app reale → review SHA → rilascio → acceptance,
non aggiungere un'altra implementazione parallela. Il remoto privato
si chiama `custody`, non `origin`: verificare il target prima del fetch
evita di interrogare il repository upstream sbagliato. Il closeout
terminale resta NO finché mancano review, rilascio e acceptance reali.

## Qualifica P1 e stop operativo delimitato — 2026-10-14

**Candidato:** [`16faf8d63130981f771e404d40f314d4543ba93b`](https://github.com/skunklabs-uk/omp-web/commit/16faf8d63130981f771e404d40f314d4543ba93b),
base `91319e0a3c9dcea4978f6bb9fd7b2da373353de5`, custodito nel branch
`mission35/pocock-bootstrap-controls`. Il branch concorrente della PR1
`f861bb8` e il remoto documentale `449feab` restano intatti: questa qualifica
non si trasferisce alle loro superfici né costituisce un merge.

**Prove:** [archivio P1](evidence/mobile-bootstrap-16faf8d.tar.gz), SHA256
`f2a288a490f55d7579d22c18e36a74fcbfbb86e0977a4c4415029fdd76e44320`.
Contiene manifest di 38 file, log dei check, review originali, JSON nativi,
screenshot e fixture riproducibili; esclude assertion, auth, journal e state.
Il controllo privacy è delimitato all'allowlist e ai pattern dichiarati.
Le fixture sono temporanee: i percorsi WSL del preflight non sono portabili
sul Pod e non autorizzano l'esecuzione del trial con identità sostitutive.

| Gate | Esito ed evidenza osservata | Residuo |
|---|---|---|
| Causa e regressione | SÌ: test RED sulla ricevuta sovrascritta; build originale con `confirm` reale di `session_start`, risposta/abort disabilitati anche dopo timeout | Nessun risultato della prima fixture `.mjs`, non scoperta dal loader, è usato come prova |
| P1 sul candidato | SÌ: canali lavoro/risposta/abort distinti; controlli attivi a 6435 ms con HTTP iniziale pendente; in una prova dedicata click di risposta a2969ms, native future `false` e readiness completata; doppio click reale produce un solo POST risposta | L'ack dell'abort non risolve da solo la domanda startup |
| Timeout e continuità | SÌ: dopo 11210 ms abort nativo chiamato e risolto una volta; domanda ancora pendente, poi risposta `true`; reload conserva tre ID, GET dell'ID iniziale senza nuovi POST | Non prova continuità dopo restart del processo |
| Decisioni e confini | SÌ: confirm `false`, editor e Plan approvato verificati nel runtime prima del teardown; stale/401 e reconnect senza POST; observer, scope errato, cross-site e binding estraneo respinti | Viewport 390/820 senza overflow; non è tablet personale |
| Check e review | SÌ locale: 629 PASS, 1 skip, 0 FAIL; lint pertinente; build production con typecheck; warning preesistente sull'export dinamico. Standards 0 rilievi, Spec 0 rilievi sullo SHA esatto | Check GitHub sul nuovo SHA: 0 check-run e 0 status, aggregato `pending`; nessun retry o merge |
| Seam e limiti trial | SÌ locale: registry nativo costruito prima del budget, discovery GET passa nel fetch late-bound; cap30 blocca il31, deadline e stream abortiti, OAuth sintetico escluso, retry503 conteggiati3/3, errore SSE bloccato al cap2 | Nove scenari sintetici, zero richieste a pagamento; non esecuzione del provider bound |
| Deadline dal lancio | SÌ in scala: refresh OAuth nativo tenuto pendente prima del primo modello; timer SDK a1501ms, timeout OS a3009ms con exit124; POST modello0 | Prima del trial reale servono watchdog OS900s e guard SDK890s, installati prima degli import |
| Trial originale | NO: SSH verso `192.168.1.22:22` rifiutato; nessun host WSL configurato tra gli accessi disponibili | Operatore: rendere disponibile accesso autorizzato al WSL originale e verificare assenza di altro writer; poi riconciliare Plan/binding/auth senza copie |
| Rilascio e acceptance | NO: origin WSL e custodia operativa non raggiungibili, full plan corrente non prodotto | Riprendere dal gate Cloudflare esistente; dopo il rilascio, operatore su tablet reale fuori LAN e ChatGPT personale |

Le esecuzioni early/late/ordinary, early-input e doubletap hanno verificato
zero messaggi d'inferenza,
zero POST modello esterni e cleanup nativo con exit0. Le schede sono chiuse
prima del teardown. L'aspettativa del coordinator nel preflight è aggiornata
alla successione corrente, preservando il controllo fail-closed; lo script
bound non è stato eseguito né il provider promosso da `observer/observe`.

**Riesame cumulativo RFC-0001 §§2/6/7:** KEEP identità/sessione e autorità
native, ricevute persistite, source pin, CF Access/MCP nativo e pilot accettati.
DELETE dalla soluzione proposta ledger, broker, coordinator e preload
permanenti aggiuntivi; nessun servizio o codice concorrente è stato rimosso.
REPLACE il gate globale e lo slot browser condiviso con tre istanze del
commander esistente; conteggi di bottoni/testo con l'invariante senza POST;
aspettative fixture con future e stato nativi osservati.

**Retro intermedia:** il loader scarta `.mjs`; le risposte mantengono
`acknowledged` anche quando la future è risolta; un dialogo chiuso si riapre
dal controllo reale. Le fixture sono state corrette, non gli esiti di
prodotto adattati alle asserzioni. Applicati TDD, code-review a due assi e
writing-for-agents originali al pin scelto; `ask-matt` letto per il percorso,
senza attestare nuove invocazioni user-only. Retro terminale, metodo del
provider nel trial, tablet e ChatGPT restano non attestati; humanize-writing
non disponibile. Nessun nuovo framework, issue, servizio o retry CI.

**Decisione:** SÌ alla correzione P1 locale, NO al closeout della missione.
Plan Active, #35/#52 aperte. Il solo blocco operativo non invalida il lavoro
locale concluso; per riprendere occorre l'accesso WSL descritto sopra,
non una conferma meccanica né un trasferimento dell'ownership.

## Coda operativa condivisa — mandato del PO del 2026-10-14

**Obiettivo e done:** completare i due percorsi delle SPEC Active, sullo
stesso provider bound: pannello mobile reale e ChatGPT personale, compreso
il rilascio autorizzato. Il P1 locale già qualificato non chiude la missione.
La richiesta corrente autorizza lavoro non distruttivo, integrazione,
verifica e documentazione; costi nuovi, rischi rilevanti e operazioni
irreversibili restano al PO. Restano applicabili i gate di deploy esistenti.

Questa sezione è la coda corrente, non un secondo ledger: gli ID sotto sono
slice delle issue già esistenti. Priorità e dipendenze sono proiezioni del
lavoro approvato, non nuove condizioni di stop. Owner di integrazione,
verifica dei risultati e continuità: coordinatore OMP corrente.

| ID / priorità | Responsabile / stato | Dipendenze | Risultato atteso e done verificabile | Ultima attività / prossima azione |
|---|---|---|---|---|
| #52/P1 — P0 | Coordinatore OMP / completato | Nessuna | Risposta e abort indipendenti dal bootstrap; ricevuta originale e scoping preservati | `16faf8d`, browser production, check e due review sopra / riusare le prove; ripeterle solo sul codice materialmente cambiato |
| #52/INTEGRAZIONE — P0 | Coordinatore OMP / qualificato localmente | OUTCOMES, SPECIALISTI, SCROLL | Candidato unico con P1 preservato, check/smoke e review pertinenti sul nuovo SHA | `8fc6e67` pubblicato sul branch proprio; suite627 PASS/1skip/0FAIL, typecheck/lint/build exit0, Standards GO e Spec GO / usare questo candidato nei gate di rilascio, senza trasferire il GO alla PR1 concorrente |
| #52/OUTCOMES — P0 | Coordinatore OMP; implementazione `IntegrateNativeOutcomes` conclusa / qualificato localmente | Base16faf8d e hunk pertinenti PR1 | Esiti answer/abort correlati e flush fallito non presentato come durable completion; nessun replay o regressione prompt/steer/P1 | Browser production: confirm/editor/Plan e abort nativi con ricevute completed; route MCP restituisce gli stessi esiti. Reload e doppio click senza replay; failure di flush coperta dalla regressione / prova originale dopo ACCESSO |
| #52/SPECIALISTI — P0 | Coordinatore OMP; implementazione `ExposeNativeSpecialists` conclusa / qualificato localmente | Snapshot e API native esistenti | Stato e risultati di specialisti attivi/conclusi nella proiezione comune, senza journal o campi privati | Due P2 riprodotti con4 test RED e corretti; browser/MCP concordi, risultato completo distinto dall'anteprima, follow-up stesso ID/file senza risultato vecchio. Bus e writer SDK reali con dati sintetici, non esecuzione specialisti / verificare sul percorso originale |
| #52/SCROLL — P0 | Coordinatore OMP / qualificato localmente | Layout missione esistente | Contenuto raggiungibile con scroll reale del pannello a390/820, non solo assenza overflow orizzontale | RED16fa conservato; GREEN8fc: main844px, scrollHeight2669px, scrollTop1825px e fondo visibile, windowY0; screenshot390/820 / acceptance sul tablet reale dopo rilascio |
| #35/ACCESSO — P0 | Coordinatore OMP sul WSL originale / disponibile | Identità originale e checkout preservati | Operare sul WSL senza cambiare ID/CWD/auth | CWD bound portato solo FF e87c349→fd4f820; parser applicativo reale legge successore01a13b77 e observer/observe, cinque mutazioni negate, journal invariato / mantenere queste authority e identità nei gate successivi |
| #35/TRIAL — P1 | Coordinatore OMP / concluso nel perimetro read-only | Nessuna nuova allowance | Unico trial bound con cap/deadline ed esito/metodo revisionati | Report operatore exit0,107097ms,14HTTPmodello/30,0blocked/failed; review indipendente positiva per la lettura pertinente, limite delle fonti arretrate preservato; risposta e preload temporanei archiviati e rimossi / nessun retry o secondo trial, non promuovere observer |
| #1514/RILASCIO — P1 | Coordinatore OMP; operatore per custodia / bloccato dallo sblocco Vaultwarden | Custodia token scelta dal PO, servizio permanente e piano allora corrente | Rilascio nello stesso WSL con gate Cloudflare e smoke HTTPS/Access/SSE/POST soddisfatti | Full plan4createOMP/0update/0delete e canary user-manager qualificati, no apply; Vaultwarden scelto esplicitamente, destinazione vault.skunklabs.uk e CLI locked / operatore sblocca nel proprio terminale privato; completare custodia del solo nuovo token senza condividere BW_SESSION, poi piano fresco e servizi |
| #35/MOBILE — P1 | Coordinatore OMP; operatore per dispositivo/login / bloccato | #1514/RILASCIO | Criteri mobile-control provati sul tablet reale fuori LAN | Solo viewport390/820 provati / guidare l'operatore sul percorso reale dopo il rilascio |
| #35/CHATGPT — P1 | Coordinatore OMP; operatore per account/login / bloccato | #1514/RILASCIO | OAuth e tool MCP reali dal ChatGPT personale, stessa sessione e receipt/outcome | Nessuna acceptance personale / esercitare il client reale dopo il rilascio |
| #35/COORDINAMENTO — P0 | Coordinatore entrante OMP/Pocock / fonti riconciliate, preparazione operativa | Esiti verificati e limiti del PO | Unico writer, provider observer e fonti recuperabili | Successore01a13b77, checkout nuovi e prove recuperate; trial originario non attribuito al successore / pubblicare il Plan senza overwrite dei branch concorrenti; completare solo gate raggiungibili, nessuna acceptance anticipata |

**Supervisione:** i job della sessione notificano esiti e messaggi al
coordinatore. Il lavoro indipendente procede mentre sono attivi; nessun
polling o retry cieco sostituisce la verifica. Alla consegna di un risultato,
il coordinatore controlla fonti, diff e prove prima di dichiararlo concluso.
Un errore correggibile porta a correzione o cambio strategia; un prerequisito
esterno mancante lascia bloccata soltanto la slice dipendente.

**Continuità:** nessun supervisore persistente esterno è qui configurato.
La fine della sessione non implica che agenti o monitoraggio continuino.
Prima della sospensione si registrano owner, esito, blocker e prossima
azione reali; alla ripresa si rilegge questa coda e lo stato dei job, senza
presumere processi attivi. Non si avviano daemon, scheduler o nuovi tracker.
`interview-me` non è disponibile tra le skill montate: eventuali decisioni
indispensabili saranno raccolte con lo strumento di domande disponibile;
le operazioni manuali avranno passi e risultato atteso, senza segreti.

### Integrazione locale necessaria dopo la ricognizione

`ReconcileDeliveryHead` ha identificato due gap ancora eseguibili senza WSL:
il watcher ignora eventi nativi specifici di risposta/abort e sopprime
errori di flush terminale; la proiezione specialisti scarta i conclusi e
mostra soltanto ID/agent/status. Sono gap dei requisiti di esito osservabile,
durabilità e team visibility delle SPEC, non nuovi obiettivi.

Si mantiene la base `16faf8d`: lock rilasciato dopo admission, bypass della
readiness per risposta/abort, tre canali e correlazione nativa prompt/steer.
Si riusano soltanto gli hunk pertinenti della PR1 per esiti/persistenza.
Specialisti e risultati devono provenire da snapshot/transcript nativi,
con proiezione allowlist condivisa browser/MCP, senza un altro registry.
L'integrazione UI rimane al coordinatore per evitare scritture concorrenti.
Ogni modifica sarà provata su comportamento osservabile e sul nuovo head.

**Alternative scartate:** merge integrale della PR1 ripristinerebbe P1;
rendere obbligatorio il browser storage duplicherebbe il journal nativo
senza necessità ancora provata. ALS, continuazioni implicite e compressione
skill restano esclusi finché i confini della base già eliminano quel bisogno.
Non si riabilitano funzionalità negate per poi aggiungere nuovi controlli.

### Sblocco manuale minimo del WSL originale

Questi passi identificano il contesto: non avviano OMP, trial o deploy e non
richiedono nuove porte o credenziali. Eseguirli soltanto sul PC Windows
originale, non nel terminale del Developer Workspace.

1. Aprire dal menu Start la distribuzione WSL usata per il lavoro originale
   oppure il suo terminale già aperto. Se non è riconoscibile, PowerShell
   `wsl.exe --list --verbose` elenca le distribuzioni; non crearne una nuova.
2. Nel terminale Linux eseguire `hostname` e `id -un`. L'utenza attesa è
   `iingenito`; verificare poi soltanto la presenza dei materiali, senza
   aprire il file sessione o la directory delle credenziali:

   ```bash
   p=/home/iingenito/projects/personal/.worktrees/agent-os-omp-coordinator
   test -d "$p" && printf 'CWD originale presente\n' || printf 'CWD originale mancante\n'
   s=/home/iingenito/.local/state/agent-os/remote-control/mission35/agent/sessions/-projects-personal-.worktrees-agent-os-omp-coordinator/2026-10-12T20-22-28-282Z_01a131c7-ecba-7000-a4fb-ff906f642f4f.jsonl
   test -f "$s" && printf 'Sessione originale presente\n' || printf 'Sessione originale mancante\n'
   ```

3. Lasciare il terminale disponibile e comunicare solo se CWD/sessione sono
   presenti e se esiste già un accesso remoto autorizzato utilizzabile.
   Non avviare un'altra OMP e non terminare il writer precedente: il
   coordinatore deve prima verificarne lo stato. La presenza dei file non
   dimostra né writer unico né validità dell'auth.

Se il solo terminale locale è disponibile, il passo successivo sarà
un'istruzione assistita precisa sullo stesso WSL. Se esiste un canale remoto
già autorizzato, serve soltanto il riferimento non segreto per riusarlo.
Se il PC non è disponibile, #35/ACCESSO resta bloccato: non è un motivo per
simulare continuità sul Pod. Un nuovo SSH/tunnel/permesso non è installato
implicitamente come diagnostica.

### Candidato integrato qualificato — 2026-10-14

Fonte esatta `8fc6e67c021be66547e76f9d216c9a7b0340f924`, pubblicata
fast-forward in `skunklabs-uk/omp-web`, branch
`mission35/pocock-bootstrap-controls`. La PR1 a `f861bb8` e il branch
documentale concorrente a `449feab` restano preservati; nessun merge.

**Standards:** GO codice, nessun finding sul cumulativo dal fixed point
`f7338b746602e40f888996350502ce8dc8ed4cf6`, con le dodici euristiche Fowler
della skill originale Pocock. Il precedente NO-GO di `5c9e26a` conteneva
due P2: un yield terminale senza dati sovrascriveva le sezioni incrementali;
un follow-up poteva recuperare risultati dei turni precedenti nello stesso
journal. Quattro regressioni RED conservate, poi GREEN con leaf nativa e
assembler nativo, senza secondo registry.

**Spec:** GO codice, nessun finding sul medesimo SHA e fixed point.
Entrambe le review sono statiche; il runtime è stato verificato dal
coordinatore. Nessuno dei verdetti certifica rilascio o acceptance remota.

**Verifiche eseguite:** suite627 PASS/1 SKIP/0 FAIL; typecheck, lint
pertinente e build exit0. Build ID `xZaoa-In3fKM-Mh3eVOd7`;
warning preesistente della dipendenza dinamica nella route export conservato.
GitHub sullo SHA pubblicato: check-run0, status0, aggregato `pending`,
Actions disabilitato; nessun verde CI dichiarato, retry o merge.

Sul build production esatto, tre fixture concluse con cleanup nativo exit0:

- Risposta bootstrap effettiva a2953ms; doppio click reale, un solo POST.
- Dopo oltre8s, lavoro `unknown` ma risposta e abort disponibili; abort SDK
  una volta, confirm ancora pendente, poi risposta e readiness. Ricevute
  answer/abort `completed` e stessa correlazione via route MCP.
- Reload e query del comando originale: in totale un POST ensure_session,
  uno answer e uno abort, nessun replay. Gli altri canali ripartono
  conservativamente da `unknown` finché non si consulta la loro ricevuta;
  il risultato nativo completato resta osservabile separatamente.
- Confirm falso, editor e Plan approvato verificati sullo stato SDK prima
  del teardown; stale401 e reconnect senza POST, observer e confini respinti.
- Specialisti attivi, risultato completo di20 righe, errore e unavailable
  visibili; browser e route MCP concordi. Il follow-up sullo stesso ID/file
  cancella il vecchio risultato e mostra soltanto quello del turno corrente.
- Scroll interno effettivo e fondo raggiunto; nessun overflow orizzontale
  a390/820. Screenshot reali inclusi, non equivalenti al tablet fuori LAN.

I lifecycle e i messaggi specialisti sono sintetici, su bus, AgentSession,
SessionManager e writer SDK reali; nessuno specialista/modello è stato
eseguito. JWT/JWKS sono sintetici, verifier e gate applicativi originali.
Il client HTTP MCP esercita la route reale, non ChatGPT personale.
Trasporto fetch esterno negato, tentativi GET negati conservati nei raw;
nessun dispatch modello POST o credenziale originale.

**Prove durevoli:** `tasks/evidence/mobile-integration-8fc6e67.tar.gz`,
SHA256 `59f45443e363f0e7209c1222e1b41ec5ee81a99c237b102368d56cfbdeccf351`.
Archivio estratto in directory nuova: manifest30/30 OK. Include raw
suite/build/RED, entrambe le review finali e il NO-GO precedente, risultati
nativi/browser, screenshot e tre sorgenti di riproduzione. Solo allowlist:
nessuna assertion, chiave privata, auth, SQLite o sessione JSONL originale.
Scansione di materiale con forma JWT/token/chiave privata superata.

**Prossima azione:** sblocco ACCESSO con i passi manuali sopra. Trial,
custodia/full plan, rilascio, tablet fuori LAN e ChatGPT personale restano
bloccati nelle rispettive slice; nessun apply, deploy o trial originale.
Non esiste monitoraggio persistente dopo la fine di questa sessione.

### Preflight metadata sul WSL originale — riscontro operatore

Il PO ha eseguito il comando isolato nel WSL `NOVBSCWOLaulMaU`, utente
`iingenito`, dopo il fast-forward del CWD bound a `e87c349`. Gli hash dei
due script recuperati coincidono con le copie custodite. Risultato completo
redatto in `tasks/evidence/native-metadata-original-e87c349.json`, con
provenienza esplicita: output fornito dall'operatore, non esecuzione diretta
dal Developer Workspace.

`metadata-ready`, stage `dispose`,3875ms; Bun1.3.14, SDK18.8.7,
sessione/CWD originali, modello `openai-codex/gpt-6.1-sol` low,27skill al
pin originale, auth nativa disponibile, solo read, retry/fallback/AutoQA
disabilitati. Coordinatore corrente e provider observer/observe corretti.
Zero dispatch modello, nessun prompt; metodo del trial non ancora provato.

Il journal non è byte-identico:153→154entry persistite, tipo dell'entry
aggiunta non identificato in questo output. Restano96messaggi con identico
hash del prefisso originale, ruoli invariati, un binding con hash invariato,
nessun cambio modello/thinking. Non si promette immutabilità dei metadati.
Il controllo OS non ha rilevato writer applicativi sul file; le sole
eccezioni di accesso erano systemd e sd-pam. Non è un lock globale né una
garanzia contro avvii successivi: durante il trial non si avviano altri
writer e non si aggiorna il checkout originale.

Questo checkpoint metadata è storico: il successivo trial unico è concluso
e revisionato sotto. Nessuna nuova allowance deriva dalla ripresa.

### Trial originale concluso — esito e metodo revisionati

Riscontro del PO: unico lancio `--trial` nel WSL originale, exit0,
`trial-read-only-complete-review-required`, stage dispose,107097ms dal
lancio. Report redatto in `tasks/evidence/native-trial-original-e87c349.json`,
con provenienza operatore esplicita. Il SHA prima del trial coincide col
SHA dopo il metadata: catena delle due osservazioni verificata.

Counter HTTP:14 richieste modello ammesse su30,0bloccate,0fallite,
reason null. `modelDispatches:1` è il marker del primo dispatch principale,
non il totale HTTP. Il lancio unico è consumato: remaining16 non concede
un retry o un secondo trial. Fine osservata entro890s SDK e900s operativi;
il report descrive l'obbligo del watchdog OS, non ne attesta da solo l'installazione.

Stesso ID/CWD, modello/thinking, authority observer/observe e binding;
prefisso dei96messaggi precedenti invariato. Aggiunti un messaggio utente,
14assistant e13toolResult; totale124messaggi. Fine nativa terminale,
stopReason stop; nessun trasferimento ownership o continuità dei pending
dimostrata. Letture riuscite: ask-matt1, currentPlan4, boundPlan2, altre6.
Questi conteggi non sostituiscono la review dell'applicazione del metodo.

La risposta finale originale è stata letta direttamente nel WSL e
revisionata da `TrialSafetyReview` con contesto separato, insieme ai report
metadata/trial e agli originali Pocock `ask-matt`/`PHASE-BOUNDARIES`.
SÌ alla sola qualificazione della lettura pertinente: riuso di SPEC/ticket,
percorso read-only, nessuna invocazione inventata, TDD/delega/scritture
correttamente non applicabili. La fonte `agent-os-pocock-reconcile` richiesta
dal vecchio prompt è arretrata; il trial rileva il drift, non qualifica la
successione attuale né l'integrazione8fc6e67. Non si ripete per correggere
quel drift. Nessun GO di ownership, pending, rilascio o dispositivo.

Prove: [archivio della review](evidence/native-trial-method-review-e87c349.tar.gz),
SHA256 `53c3e440bed2224f2fd483b26c591f91eb53748202839c6534f652e3bc91feeb`,
cinque membri verificati: sola risposta finale, review originale,
provenienza e due sorgenti temporanei del trial. Nessun journal/auth.
Dopo recupero e verifica, eliminate la directory della risposta privata
`/tmp/mission35-native-pocock-review-1dBwvK` e la copia temporanea
`preflight-current.arXmlK`; le fonti storiche e i checkout originali restano.

### Full plan corrente nel WSL — nessun apply

Root corrente Homelab `11dea14f`, discendente del merge1515 `c766e746`;
nessun delta del modulo Cloudflare rispetto all'head revisionato `a57e2ed`.
Procedura del runbook: input Vault del candidato, state/environment operativi,
contesto privato, init lock readonly, validate e full plan con refresh.
Exit2: soltanto le quattro creazioni OMP, zero update/delete. Nessun
`-target`, `-refresh=false`, intervento sullo state o provisioning parallelo.
State operativo SHA256 prima/dopo
`5ef022423e40234cecd94606a7b0bfbbf9d361cd2c4ee0db7093ed8586fc1229`.
Piano SHA256 `fc161d3299a02188c5ecd95f9c2ee02418a7e9113bf88a3ec38a9b974142eaa8`.
[Proiezione redatta](evidence/cloudflare-fullplan-original-wsl-20261014.json).
Eliminato il contesto con input/state/piano sensibili; prima dell'eventuale
apply servirà il piano allora corrente. Nessuna risorsa Cloudflare o
servizio operativo persistente attivato.

Tool presenti: Bun1.3.14, OpenTofu1.13.1, cloudflared2026.10.0,
manager systemd utente running con linger già attivo. Nessuna unità
OMP/cloudflared permanente registrata; Bitwarden è locked.

Il sorgente recuperato8fc6e67 ha installazione frozen/ignore-scripts/offline
exit0 e nuova build WSL isolata dalla rete exit0 in351,1s, con typecheck
nativo e warning export preesistente. Non è una nuova fullsuite:
le prove627PASS/1skip dell'head invariato restano attribuite al coordinatore
precedente. GitHub: Actions disabilitato, check-run0/status0, aggregato
pending; nessuna CI verde o rilancio.

Canary temporanea del manager utente sul build production: origin
127.0.0.1:30141, stessa netnamespace WSL; configurazione Access senza AUD
reale dà503, Host estraneo403. Restart nativo cambia PID e conserva503;
stop exit0, unità collected/not-found, MainPID0 e nessun listener30141.
Non è autenticazione positiva, SSE o Cloudflare: non esiste un connector
OMP in esecuzione. Le richieste sono state respinte dal proxy, senza
aprire una sessione nativa; SHA del journal bound invariato prima/dopo.
[Prova build/lifecycle](evidence/wsl-source-build-lifecycle-8fc6e67.json).

Il parser applicativo originale è stato esercitato anche nel CWD bound
dopo il FF e87c349→`fd4f8207f3ba447474f4d459e61910511a4f00f6`:
successore01a13b77, stesso provider observer/observe, cinque mutazioni
negate; sourceRevision
`6b9f5473e46d7f3e7725d2af92bc7b2bae71a9b1829fb3698a0a9e68e838843a`.
Journal invariato, rete isolata, nessuna sessione aperta e profilo temporaneo
rimosso. Il presente successore documentale non cambia quei campi authority;
il riferimento e l'hash della fonte restano specifici allo smoke fd4f820.

Review indipendenti della ripresa su fd4f820: Standards0finding e
Spec0finding, assi statici separati; nessuna verifica runtime attribuita
ai reviewer. App `485840f43e4188ac48cb193338a80c5c8edad629` pubblicata
FF sul branch proprio: successor di8fc6e67 con la sola correzione
README19, che distingue storia native e attach/ownership/pending live.
Riesame Standards0 e Spec0 sul solo delta documentale, senza nuovi check
di codice identico né trasferimento della qualifica runtime a un codice nuovo.

**Decisione corrente del PO:** custodia **Vaultwarden esistente**, scelta
esplicita nella ripresa. Destinazione nativa verificata:
`https://vault.skunklabs.uk`; la CLI è locked. Non adottare SOPS come
custodia alternativa del token senza nuova scelta del PO.
Prima dell'apply occorre lo sblocco interattivo nel terminale privato
dell'operatore e la procedura di custodia del solo token OMP; `BW_SESSION`
resta soltanto nella shell autenticata, fuori chat, Git e file persistenti.
La custodia sarà completata da quella shell, non copiando la sessione
unlock al coordinatore. Nessuna richiesta di master password o token.
Il full plan positivo non autorizza apply prima di quel gate; il provider
observer e l'allowance consumata non autorizzano lavoro lungo/interruzione
reali. Tablet fuori LAN e ChatGPT personale restano acceptance del PO.
Nessun cambio credenziali, profilo globale, unità altrui, cluster, costi o CI.
