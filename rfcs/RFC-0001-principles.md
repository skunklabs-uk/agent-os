# RFC-0001 – Principi fondanti della Software Factory

**Stato:** Active
**Versione:** 0.1.9
**Ultima modifica:** 2026-08-28

## Scopo

Questa RFC definisce i principi che governano le decisioni progettuali, implementative e documentali della Software Factory.

I principi si applicano alla Software Factory stessa e agli artefatti prodotti attraverso di essa.

## Definizione

Una **fonte autorevole** è la fonte designata dal progetto come riferimento ufficiale per una determinata informazione.

Una **fonte attiva approvata** è una fonte autorevole con stato `Active`, oppure un'issue, una pull request, una wave o un altro artefatto operativo esplicitamente approvato dall'utente o dall'autorità competente del progetto. La sola esistenza, apertura o modifica recente di un artefatto non gli conferisce autorità.

Una **missione** è un obiettivo attivo, delimitato e verificabile che produce un risultato utile per il progetto.

Un **controllo** è qualsiasi gate, verifica, identità, permission, schema, ledger, audit, artifact, wrapper, runner, test, workflow o automazione introdotto per prevenire, rilevare o rendere ricostruibile un failure mode.

Una **verifica o proiezione di un requisito esistente** ne rende osservabile l'applicazione senza introdurre artefatti, stati, workflow, condizioni di stop o obblighi più severi. Non è un controllo aggiuntivo e usa la prova e il perimetro del requisito originario.

Una **prova di necessità** è l'evidenza, prodotta prima dell'implementazione, che dimostra perché un controllo aggiuntivo è necessario e perché le alternative più semplici sono insufficienti.

---

## 1. Semplicità e proporzionalità

La scelta predefinita DEVE essere la soluzione più semplice che soddisfa tutti i requisiti applicabili.

Qualsiasi complessità aggiuntiva DEVE:

- rispondere a un requisito identificabile;
- produrre un beneficio verificabile;
- non poter essere sostituita da una soluzione più semplice con risultati equivalenti.

Prima di aggiungere un'entità, uno stato, una regola, un concetto, un componente, un'automazione, un'astrazione, un controllo o un documento, si DEVE verificare:

1. Esiste un modo più semplice per ottenere lo stesso risultato?
2. È possibile eliminare o riutilizzare qualcosa invece di aggiungere?
3. Il beneficio giustifica i costi di implementazione, manutenzione, test, operatività e documentazione?

Questa verifica DEVE precedere l'implementazione. Per ogni controllo aggiuntivo o soluzione custom, una fonte autorevole DEVE contenere una prova di necessità accettata che identifichi almeno:

1. il requisito, comportamento o invariante protetto;
2. il failure mode concreto e la relativa evidenza;
3. i controlli già esistenti e il gap non coperto;
4. le alternative di eliminazione, riuso, funzionalità nativa e tool standard valutate;
5. la ragione verificabile per cui tali alternative sono insufficienti;
6. il beneficio osservabile atteso e la verifica che lo dimostrerà;
7. il costo complessivo, il perimetro minimo, la reversibilità e, quando temporaneo, la condizione di rimozione.

Il richiamo generico a sicurezza, prudenza, auditabilità, compliance o `fail-closed` NON costituisce da solo una prova di necessità. Una dipendenza creata dalla soluzione proposta NON può essere usata per dimostrare che la stessa soluzione è necessaria.

La proporzionalità DEVE essere valutata sull'intera soluzione corrente, non soltanto sulla singola modifica. Una sequenza di modifiche localmente minime che produce un apparato complessivamente sproporzionato è overengineering.

In assenza della prova richiesta, il controllo o il custom DEVE essere scartato prima dell'implementazione. La complessità priva di una giustificazione verificabile è overengineering e NON DEVE essere introdotta.

Una checklist, una verifica o un richiamo non diventa automaticamente un controllo aggiuntivo per il solo fatto di rendere osservabile un requisito già vigente. Se ne amplia comportamento, perimetro, severità o lifecycle, l'ampliamento è invece un controllo aggiuntivo e richiede una propria prova di necessità.

---

## 2. Concentrazione e chiusura

Il lavoro DEVE essere organizzato per missioni, non per issue, pull request o attività tecniche considerate come fini autonomi.

Ogni repository DEVE avere una sola missione primaria attiva. Una seconda missione è ammessa solo quando la prima è bloccata da una dipendenza esterna documentata e non può avanzare in altro modo utile.

Ogni attività DEVE contribuire direttamente alla missione attiva. Issue, pull request, refactoring, documentazione, analisi, remediation e strumenti sono mezzi subordinati al risultato, non nuovi obiettivi.

Un nuovo fronte di lavoro può essere aperto solo quando è necessario per:

- completare la missione;
- rimuovere un blocco reale e documentato;
- soddisfare un requisito o una verifica obbligatoria.

Le attività utili ma non necessarie al completamento DEVONO essere rinviate. POSSONO essere segnalate sinteticamente, ma NON DEVONO diventare automaticamente implementazione, issue o backlog. Il tracciamento richiede l'autorizzazione dell'utente o di una fonte attiva approvata. Un rischio concreto già confermato DEVE essere segnalato, ma la sua trasformazione in issue o backlog richiede la stessa autorizzazione. La presenza di un miglioramento possibile non è, da sola, una ragione sufficiente per eseguirlo.

Un'attività laterale NON DEVE diventare una nuova issue o pull request quando può essere completata nel lavoro corrente, rinviata senza compromettere i criteri di accettazione oppure evitata.

Prima di aprire una nuova issue, branch, pull request, wave o attività, si DEVE poter indicare:

1. quale missione fa avanzare;
2. quale risultato concreto produce;
3. perché è necessaria adesso;
4. quale condizione ne determina la chiusura.

In assenza di risposte verificabili, l'attività DEVE essere rinviata; l'eventuale tracciamento resta soggetto alla regola precedente.

Il completamento ha priorità sull'espansione dello scope: prima chiudere, poi migliorare.

Un'attività o una pull request NON È completata per il solo fatto che codice e test siano validi. Il closeout è completo solo quando gli artefatti autorevoli del repository rappresentano lo stato finale del lavoro.

Quando il lavoro modifica comportamento, architettura, decisioni, operatività o conoscenza necessaria alla manutenzione futura, il closeout DEVE includere, se applicabile, l'aggiornamento di README, documentazione operativa, ADR e riferimenti interni. Gli artefatti resi inesatti, superati o non più applicabili DEVONO essere aggiornati, sostituiti o archiviati secondo la sezione 6. Le modifiche interne che non incidono su tali elementi NON DEVONO produrre aggiornamenti documentali artificiali.

### Autorizzazione e ampliamento dello scope

L'autorità deriva dalla richiesta dell'utente o da una fonte attiva approvata e copre obiettivo, scope, criteri di accettazione e passaggi tecnici strettamente necessari.

Un passaggio non esplicito può essere eseguito senza nuova autorizzazione solo quando:

1. è necessario per soddisfare un criterio approvato, rimuovere un blocco reale o completare una verifica obbligatoria;
2. è la modifica minima sufficiente;
3. è locale e reversibile;
4. non esistono alternative con conseguenze operative significativamente diverse.

Nuovi obiettivi, deliverable, repository, issue, pull request, wave, dipendenze, automazioni, documenti, refactoring laterali o conseguenze durevoli su architettura, sicurezza, dati, interfacce, deploy, comunicazioni esterne o costi costituiscono ampliamento dello scope quando non sono già autorizzati dalla fonte attiva.

Se una delle condizioni precedenti manca, prima di procedere si DEVONO indicare fatto osservato, ampliamento proposto, necessità, alternative e decisione richiesta.

---

## 3. Implementabilità

Devono essere proposte esclusivamente soluzioni realizzabili con gli strumenti, le risorse e le informazioni effettivamente disponibili.

Una proposta NON DEVE essere presentata come soluzione confermata quando la sua fattibilità non è stata verificata.

Quando la fattibilità dipende da una condizione non verificata, tale condizione DEVE essere dichiarata esplicitamente prima di procedere.

---

## 4. Fatti, deduzioni e informazioni mancanti

Ogni affermazione usata per prendere una decisione DEVE essere classificabile come fatto, deduzione o informazione mancante.

### 4.1 Fatto

Un fatto è un'informazione presente:

- nella documentazione autorevole e attiva del progetto;
- nel codice o nella configurazione verificati;
- in una fonte esterna identificabile e verificata.

La fonte DEVE essere indicata quando non è già evidente dal contesto.

### 4.2 Deduzione

Una deduzione è ammessa esclusivamente quando è chiaramente e logicamente derivabile da fatti disponibili.

Ogni deduzione DEVE:

- indicare i fatti da cui deriva;
- rendere esplicito il passaggio logico;
- non dipendere da ipotesi non dichiarate.

Se sono possibili più interpretazioni ragionevoli, la conclusione NON DEVE essere trattata come deduzione certa.

### 4.3 Informazione mancante

Un'informazione è mancante quando i fatti disponibili non consentono di procedere correttamente o di scegliere tra più alternative rilevanti.

In questo caso:

- non si DEVE inventare;
- non si DEVE interpolare;
- non si DEVE presentare un'ipotesi come fatto;
- si DEVE identificare l'informazione necessaria;
- si DEVE richiedere tale informazione prima di assumere una decisione che ne dipende.

La mancanza di informazioni non rilevanti per il task NON DEVE bloccare il lavoro.

---

## 5. Tracciabilità e contestabilità

Ogni decisione rilevante DEVE poter essere ricondotta a:

- un requisito;
- un vincolo verificato;
- una decisione progettuale già attiva;
- oppure una deduzione conforme al principio precedente.

Una decisione è rilevante quando modifica almeno uno dei seguenti elementi:

- comportamento richiesto;
- architettura;
- interfacce;
- sicurezza;
- dati persistenti;
- dipendenze;
- operatività;
- manutenzione futura;
- documentazione autorevole.

Per ogni decisione rilevante DEVE essere possibile rispondere:

1. Quale problema o requisito affronta?
2. Su quali fatti si basa?
3. Esiste una soluzione più semplice?
4. Quale beneficio giustifica la scelta?
5. Quali artefatti devono essere aggiornati?

Una decisione che non supera queste verifiche DEVE essere modificata o scartata.

La decisione di introdurre, mantenere o rendere obbligatorio un controllo aggiuntivo è sempre rilevante e DEVE rimandare alla relativa prova di necessità. La correttezza interna del controllo, il superamento dei suoi test o l'esistenza di componenti che già dipendono da esso non dimostrano la sua utilità o necessità. Il rimando mancante in una fonte corrente è drift documentale da correggere, non prova automatica che il controllo sia utile o inutile.

La review DEVE verificare sia la conformità dell'implementazione alla fonte attiva sia la conformità della fonte attiva a questa RFC. Una fonte locale non diventa conforme soltanto perché è stata dichiarata `Active` o approvata in precedenza.

---

## 6. Repository come contesto operativo

Il repository è la fonte autorevole dello stato corrente del progetto.

Ogni informazione operativa DEVE avere un solo punto autorevole. Eventuali riferimenti DEVONO rimandare a tale fonte senza duplicarne il contenuto.

Ogni documento governato da questa RFC DEVE avere uno dei seguenti stati:

- `Draft`: in elaborazione e non ancora vincolante;
- `Active`: approvato e applicabile al lavoro corrente;
- `Archived`: non più applicabile al lavoro corrente.

Gli esecutori DEVONO usare per impostazione predefinita solo i documenti `Active`.

Lo stato `Active` non autorizza una fonte a indebolire o bypassare questa RFC. Una fonte attiva che rende obbligatorio un controllo aggiuntivo senza la prova di necessità richiesta è non conforme e NON DEVE autorizzarne l'implementazione o il mantenimento; la fonte DEVE essere corretta prima di procedere.

I documenti `Archived` POSSONO essere consultati per ricostruire una decisione o comprendere il contesto storico, ma NON DEVONO essere trattati come istruzioni operative.

Quando una modifica rende inesatta o superata una fonte autorevole, la stessa modifica DEVE:

- aggiornarla;
- sostituirla indicando la nuova fonte;
- oppure archiviarla.

Un nuovo documento NON DEVE essere creato quando un documento attivo può contenere l'informazione senza perdere chiarezza o coerenza.

---

## 7. Verificabilità operativa

Ogni principio, requisito o regola operativa DEVE poter essere verificato in modo indipendente tramite almeno uno dei seguenti metodi:

- ispezione;
- analisi;
- dimostrazione;
- test.

Ogni verifica DEVE produrre uno dei seguenti esiti:

- `SÌ`;
- `NO`;
- `NON APPLICABILE`.

L'esito DEVE essere accompagnato da un'evidenza o da una motivazione verificabile.

Un esito `NO` DEVE indicare l'azione correttiva necessaria.

Un artefatto che non supera una verifica obbligatoria NON PUÒ diventare `Active` finché la non conformità non viene corretta oppure viene approvata una deroga esplicitamente motivata.

Un principio che non può essere verificato DEVE essere chiarito o riscritto prima di diventare `Active`.

### Burden of proof dei controlli, dei test e degli strumenti

Ogni controllo aggiuntivo parte come candidato `DELETE` o `REPLACE`, non come requisito implicito. Prima dell'implementazione si DEVE preferire, nell'ordine:

1. eliminazione del controllo quando il rischio è già coperto o accettabile;
2. riuso di un comportamento, contratto o verifica già presente;
3. funzionalità nativa già disponibile;
4. tool standard, stabile e mantenuto;
5. implementazione custom.

Un custom è ammesso solo quando la prova di necessità dimostra un gap concreto, l'insufficienza delle alternative precedenti, un vantaggio verificabile, un costo complessivo proporzionato e un perimetro minimo. La prova PUÒ essere registrata nell'issue, nella pull request, nell'ADR o nella fonte attiva già esistente; NON richiede automaticamente un nuovo documento.

La prova di necessità DEVE usare almeno la struttura seguente:

| Campo obbligatorio | Evidenza richiesta |
|---|---|
| Requisito o invariante | Comportamento protetto e fonte autorevole |
| Failure mode | Errore concreto, riproduzione o altra evidenza verificabile |
| Copertura esistente | Controlli già presenti e ragione per cui non coprono il failure mode |
| Alternative | `DELETE`, riuso, funzionalità nativa e tool standard valutati |
| Gap comprovato | Evidenza che l'alternativa più semplice non è sufficiente |
| Beneficio | Risultato osservabile e verifica che lo dimostrerà |
| Costo e perimetro | Componenti, stati, identity, permission, dati, test, workflow, documenti e operatività introdotti |
| Impatto cumulativo | Effetto dell'intero insieme dei controlli, non solo della slice corrente |
| Lifecycle | Owner, reversibilità e criterio `KEEP`, `DELETE` o `REPLACE`; per i controlli temporanei, evento di rimozione |

La necessità NON è dimostrata dal fatto che il controllo sia implementabile, corretto, testato o `fail-closed`. Il controllo DEVE dimostrare il failure mode senza di esso e la prevenzione o rilevazione con esso, oppure fornire una dimostrazione equivalente quando una riproduzione non è sicura o realizzabile. Un controllo non può essere convalidato soltanto dai test che verificano la sua struttura interna.

I test DEVONO proteggere comportamento osservabile, contratti o invarianti e identificare il failure mode rilevato. Un test che non fallisce quando il comportamento protetto viene violato NON è utile.

Tool e framework DEVONO essere usati secondo documentazione upstream corrente, best practice applicabili, use case previsto e configurazione minima sufficiente.

Test di dettagli implementativi, stringhe, topologie, comportamento upstream, coverage fine a sé stessa o attestazioni procedurali partono come candidati `DELETE`, salvo che proteggano un contratto esplicito.

Non si DEVONO creare wrapper, runner, ledger, identity, permission graph, schema o workflow custom quando le capacità esistenti offrono già evidenza, isolamento, idempotenza, recovery o integrazione sufficienti.

### Riconciliazione dei controlli preesistenti

Per un controllo preesistente privo di una prova evidente si DEVE prima cercare la decisione e l'evidenza storica verificabile, quindi valutare nell'ordine:

1. il failure mode concreto osservato;
2. la copertura corrente e il gap ancora presente;
3. le alternative di eliminazione, riuso, funzionalità nativa e tool standard;
4. il costo e l'impatto cumulativo del controllo;
5. la classificazione finale `KEEP`, `DELETE` o `REPLACE`.

Fino alla classificazione, il controllo NON DEVE essere ampliato. Una non conformità o una verifica ineseguibile blocca soltanto il lavoro che dipende da quel controllo; il lavoro indipendente già autorizzato DEVE continuare. Tool, indici e skill esterni non sono prerequisiti universali salvo prova locale specifica: ispezione diretta, analisi dei caller, test focalizzati e strumenti equivalenti restano validi quando producono l'evidenza richiesta.

### Riesame cumulativo obbligatorio

Quando una modifica amplia materialmente la superficie dei controlli e prima del closeout terminale, si DEVE riesaminare l'insieme completo dei controlli collegati alla missione. Il riesame DEVE:

1. confrontare la soluzione corrente con la baseline precedente;
2. identificare componenti, stati, identity, permission, dati persistenti, test, workflow e documenti aggiunti;
3. verificare che ogni controllo protegga ancora un failure mode reale non coperto altrove;
4. classificare ogni controllo come `KEEP`, `DELETE` o `REPLACE`;
5. eliminare o ridurre i controlli duplicati, auto-giustificati, non più necessari o sproporzionati prima di aggiungerne altri.

La review di una singola slice NON è sufficiente quando la complessità emerge dall'accumulo di più slice. Una soluzione può essere rifiutata anche quando ogni componente è localmente corretto, se l'apparato complessivo non supera la verifica di proporzionalità.

Una modifica documentale non richiede test quando il documento non è consumato da codice. Un test fuori dallo scope corrente non autorizza un audit o una remediation laterale. Prima di eliminare un test o controllo esistente si DEVE verificare che non protegga un invariante unico.

### Esiti dei controlli centrali riconciliati

| Controllo | Esito | Evidenza e copertura corrente |
|---|---|---|
| Closeout documentale | `KEEP` | La [PR #23](https://github.com/skunklabs-uk/agent-os/pull/23) registra chiusure con codice e test validi ma fonti autorevoli non riallineate e successivi commit esclusivamente documentali; la [PR #26](https://github.com/skunklabs-uk/agent-os/pull/26) rende osservabile lo stesso requisito nel template. Le sezioni 2 e 6 coprono il failure mode senza nuovi stati o workflow. |
| Guardia economica GitHub Actions | `KEEP` | I run Aeris [`30422769931`](https://github.com/skunklabs-uk/aeris/actions/runs/30422769931) e Homelab [`30607639763`](https://github.com/skunklabs-uk/homelab/actions/runs/30607639763) hanno fallito prima di eseguire step; le annotazioni GitHub indicano pagamenti falliti o spending limit insufficiente. La sezione 8 evita retry costosi e diagnosi applicative prive di segnale. |
| Tassonomia obbligatoria delle priorità issue | `DELETE` | L'[issue #17](https://github.com/skunklabs-uk/agent-os/issues/17) e la [PR #18](https://github.com/skunklabs-uk/agent-os/pull/18) documentano decisione e normalizzazione, ma non un failure mode concreto né un gap che giustifichi tassonomia, bootstrap e fail-closed universali. Le label native e il triage locale restano disponibili senza controllo centrale. |
| Burden of proof e riesame cumulativo | `KEEP` | La wave [`developer-workspace#33`](https://github.com/skunklabs-uk/developer-workspace/issues/33) ha rilevato controlli custom duplicati o auto-validanti in più repository; le PR [`homelab#768`](https://github.com/skunklabs-uk/homelab/pull/768), [`homelab#772`](https://github.com/skunklabs-uk/homelab/pull/772) e [`prosignal#82`](https://github.com/skunklabs-uk/prosignal/pull/82) ne mostrano la successiva eliminazione o sostituzione con capacità standard. Le sezioni 1 e 7 coprono sia la singola aggiunta sia l'accumulo. |

---

## 8. Controllo dei costi e dei retry di GitHub Actions

Ogni esecuzione o rerun di GitHub Actions DEVE essere trattato come uso di una risorsa esterna potenzialmente a pagamento.

- I rerun automatici di workflow o job sono vietati.
- I rerun massivi e il rilancio indiscriminato di tutti i workflow sono vietati.
- Un job fallito prima dell'avvio del primo step NON DEVE essere rilanciato.
- Un job con lista degli step vuota DEVE essere classificato come problema di infrastruttura, billing, quota, permessi o runner, non come failure applicativa.
- Se più workflow falliscono contemporaneamente prima del primo step, la remediation CI DEVE fermarsi.
- L'esaurimento confermato o sospetto del credito GitHub Actions è una condizione di stop immediata.
- Ogni retry che possa consumare ulteriore credito richiede l'autorizzazione esplicita dell'utente o del Product Owner.
- Dopo l'autorizzazione è consentito al massimo un retry per workflow e per commit o head. Ogni ulteriore retry richiede una nuova autorizzazione esplicita.
- Il retry NON DEVE essere usato come strumento diagnostico.
- Prima di considerare un retry, la diagnosi DEVE usare log esistenti, stato del job, annotazioni, billing o quota, permessi, runner e verifiche locali.
- Le verifiche locali e i controlli proporzionali DEVONO essere preferiti prima di attivare CI costosa.
- L'autorizzazione di una wave autonoma NON autorizza implicitamente spesa CI illimitata.
- Le istruzioni «continua fino al verde» o «non fermarti per failure tecniche» NON prevalgono su questa guardia economica.

La stop condition si applica alle esecuzioni o ai retry GitHub Actions e alle operazioni che dipendono dalla loro evidenza; non blocca lavoro indipendente già autorizzato.

---

## Checklist obbligatoria

Prima di considerare completato un lavoro, verificare:

| Verifica | Esito | Evidenza o azione correttiva |
|---|---|---|
| La soluzione soddisfa tutti i requisiti applicabili? |  |  |
| Esiste un modo più semplice per ottenere lo stesso risultato? |  |  |
| Ogni complessità introdotta ha una giustificazione verificabile? |  |  |
| Per ogni nuovo controllo aggiuntivo o custom esiste una prova di necessità accettata prima dell'implementazione? |  |  |
| La prova identifica requisito, failure mode, copertura esistente, alternative, gap, beneficio, costo e lifecycle? |  |  |
| Nessun controllo è giustificato da dipendenze create dallo stesso controllo? |  |  |
| La proporzionalità è stata valutata sull'intera soluzione e non solo sulla singola slice? |  |  |
| I controlli collegati sono stati classificati `KEEP`, `DELETE` o `REPLACE` quando richiesto? |  |  |
| Il lavoro fa avanzare una missione attiva e identificata? |  |  |
| L'apertura di nuovi fronti è necessaria al completamento o alla rimozione di un blocco documentato? |  |  |
| Obiettivo, scope e passaggi non espliciti sono autorizzati dall'utente o da una fonte attiva approvata? |  |  |
| Le attività laterali rinviabili sono state mantenute fuori dal flusso principale? |  |  |
| La fattibilità della soluzione è stata verificata? |  |  |
| I fatti utilizzati provengono da fonti verificabili? |  |  |
| Ogni deduzione cita i fatti e il passaggio logico da cui deriva? |  |  |
| Sono presenti ipotesi non dichiarate? |  |  |
| Mancano informazioni necessarie per assumere decisioni rilevanti? |  |  |
| Le decisioni rilevanti sono tracciabili e contestabili? |  |  |
| Le fonti `Active` interessate sono state riesaminate rispetto a questa RFC, oltre alla verifica dell'implementazione rispetto alle fonti? |  |  |
| Ogni informazione operativa ha una sola fonte autorevole? |  |  |
| Sono state introdotte duplicazioni evitabili? |  |  |
| I documenti interessati hanno uno stato corretto? |  |  |
| La documentazione attiva rappresenta lo stato finale del lavoro, quando la modifica richiede un aggiornamento documentale? |  |  |
| Gli artefatti superati o non più applicabili sono stati aggiornati, sostituiti o archiviati secondo le regole esistenti? |  |  |
| Le verifiche producono evidenze osservabili? |  |  |
| Controlli, test, strumenti e workflow adottano la soluzione minima nell'ordine previsto e ogni custom supera il relativo burden of proof? |  |  |
| Ogni controllo temporaneo ha owner, reversibilità e condizione di rimozione verificabili? |  |  |
