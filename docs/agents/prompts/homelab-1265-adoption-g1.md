# Adozione del collegamento seriale per Agent OS

**Stato: Active**

## Autorità e incarico

Missione approvata dal Product Owner: [Homelab #1265](https://github.com/skunklabs-uk/homelab/issues/1265), continuazione della #1252 per tutti i 32 repository. Questo incarico riguarda soltanto l'adozione documentale di `skunklabs-uk/agent-os`; non modifica RFC, requisiti, template, script o regole della Software Factory.

Leggi integralmente la RFC-0001 corrente fornita dal parent e `AGENTS.md`. La richiesta verificata dal parent contiene branch, head, assignment e generation: usa quella revisione, senza ricostruire i parametri da GitHub. Non avviare altri consumer o processi modello.

## Fonti da leggere nel checkout

- `README.md`.
- `requirements/REQ-0001-software-factory.md`, integralmente: requisito Active del progetto.
- `rfcs/RFC-0001-principles.md`, integralmente, confrontandola con la fonte corrente fornita dal parent.
- `scripts/init-project.sh` e `scripts/test-init-project.sh`, in sola lettura per distinguere bootstrap e relative verifiche dal collegamento seriale.

`software-factory.md` e `backlog/decision-review-process.md` sono Draft; le review e `tasks/WAVE-0001-validate-req-0001.md` sono Archived. Non usarli come nuove istruzioni operative. I template sono lo scheletro per altri progetti e non istruzioni per questo incarico.

Il runbook autorevole del collegamento è [WORKSPACE-HANDOFF.md](https://github.com/skunklabs-uk/developer-workspace/blob/main/docs/WORKSPACE-HANDOFF.md); il lifecycle runtime appartiene al [README Homelab](https://github.com/skunklabs-uk/homelab/blob/main/gitops/apps/developer-workspace/README.md). Il coordinatore ha verificato queste fonti sul producer `599dbc40d18892865443bfe9fb2606237b3c06c8` e Homelab `008506bc4e2853a96eff247221b77ef5b77be42c`. Non interrogare fonti esterne dalla sandbox.

## Modifica richiesta

Modifica soltanto `README.md`, aggiungendo una sezione breve in italiano per l'operatore del collegamento. Conserva le informazioni esistenti sul requisito, sulla RFC e sul bootstrap dei nuovi progetti. La sezione deve spiegare:

1. Un incarico richiede repository e thread ammessi, branch/head esatti e prompt corrente; un solo consumer seriale esegue il task in un checkout isolato.
2. Il report è distinto dalla pubblicazione. Una modifica richiede `publish_paths` con file esatti e una PR Draft nello stesso repository; il parent pubblica e il coordinatore rilegge SHA/diff e completa RETURN. Il child non esegue commit, push, merge o rollout.
3. Il repository contiene documentazione e lo script di bootstrap con i suoi test; al candidate iniziale non contiene workflow GitHub Actions. Distingui le verifiche del bootstrap dalla review documentale del task. Non eseguire gli script, creare progetti o introdurre CI per questo incarico.
4. Agent OS non distribuisce un'applicazione HTTP: la preview web non è applicabile a questo incarico documentale. Restano necessari review del diff e RETURN. Questa nota descrive l'adozione di Agent OS come repository; non attesta il completamento globale di REQ-0001.
5. Rimanda ai due runbook proprietari per enrollment, selezione GitOps, recupero e stato persistente; non copiare un catalogo dei progetti, configurazioni operative o credenziali nel README.

Non dichiarare già completati la review finale, il merge o la CI di questo incarico. La prova di consegna verrà acquisita dal parent dopo il risultato; il coordinatore completerà il closeout e rimuoverà questo prompt.

## Confini e verifica

- Nessuna modifica a RFC, REQ, AGENTS, template, script, workflow o policy centrali.
- Nessuna rete dei comandi, installazione di tool, esecuzione del bootstrap, credenziale, API esterna o filesystem fuori dal checkout.
- Nessun nuovo test per documentazione non consumata da codice.
- Verifica la sezione rispetto ai file letti e controlla che il diff riguardi soltanto `README.md`. Applica una review tecnica e una revisione della chiarezza del testo; usa `humanize-writing` solo se disponibile nel perimetro, senza installarla o fingere una review indipendente.

Restituisci in italiano: modifica effettuata, fonti e head esaminato, verifiche realmente eseguite, limiti e gate ancora spettanti al coordinatore. Non inventare output, URL di risultato o commit di pubblicazione.
