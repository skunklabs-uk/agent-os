# AGENTS.md

## Scopo

Questo file contiene le regole operative minime per lavorare nel repository. Le sue istruzioni sono vincolanti; ogni deroga richiede autorizzazione esplicita.

## Fonti autorevoli

Prima di proporre o applicare modifiche, leggere:

1. `requirements/REQ-0001-software-factory.md`
2. `rfcs/RFC-0001-principles.md`
3. gli altri documenti con stato `Active` direttamente pertinenti al task

I documenti con stato `Draft` possono essere usati come materiale di lavoro, ma non costituiscono regole approvate.

I documenti con stato `Archived` non devono essere usati come istruzioni operative.

## Regole obbligatorie

- Applicare i principi definiti in `rfcs/RFC-0001-principles.md`.
- Proporre la soluzione più semplice che soddisfa tutti i requisiti applicabili.
- Non introdurre componenti, documenti, astrazioni o automazioni senza una necessità verificabile.
- Non inventare informazioni mancanti.
- Usare deduzioni solo quando sono chiaramente e logicamente derivabili da fatti disponibili.
- Per ogni deduzione, indicare i fatti di partenza e il passaggio logico.
- Se manca un'informazione necessaria per una decisione rilevante, fermarsi e richiederla.
- Non bloccare il lavoro per informazioni che non influenzano il task.
- Evitare duplicazioni: ogni informazione operativa deve avere una sola fonte autorevole.
- Aggiornare, sostituire o archiviare i documenti resi obsoleti da una modifica.
- Non creare un nuovo documento quando uno esistente può contenere l'informazione senza perdere chiarezza.
- Usare Conventional Commits per commit e titoli delle Pull Request.

## Governo del lavoro attivo

- Il lavoro attivo si individua solo tramite la fonte esplicita del lavoro corrente: richiesta dell'utente, Pull Request o task approvato. Non si deduce da nome, data o ultima modifica.
- Una wave `Draft` non autorizza l'esecuzione. Una wave `Active` autorizza solo obiettivo, scope, non-obiettivi, verifiche e condizioni di stop dichiarati nella wave.
- Ogni repository può avere al massimo una wave `Active` alla volta. Wave `Active` appartenenti a repository diversi possono coesistere ed essere eseguite in parallelo. Quando non esiste una wave attiva nel repository corrente, governa la fonte esplicita del lavoro corrente.
- L'autorità della wave cessa alla chiusura. L'integrazione finale resta soggetta all'approvazione richiesta e alle regole di merge applicabili.

## Arresto e prosecuzione

Fermarsi solo quando il lavoro richiede una decisione non documentata, supera lo scope approvato, viola una fonte `Active`, comporta conseguenze rilevanti non valutate oppure richiede una verifica obbligatoria che resta ineseguibile dopo ragionevoli tentativi.

Prima di fermarsi, indicare condizione applicabile, fatto osservato e decisione o informazione necessaria.

Una condizione di stop si applica al solo perimetro che la richiede. Il blocco di un task, una fase o un'operazione non blocca automaticamente l'intera missione: il lavoro già autorizzato e determinato che non dipende da quella condizione deve proseguire.

Quando un task si chiude e la fonte attiva identifica già il lavoro successivo necessario nella stessa missione, proseguire senza chiedere una conferma meccanica, salvo che si applichi una condizione di stop reale.

Non fermarsi per passaggi già approvati, errori locali correggibili, verifiche risolvibili entro lo scope, stato documentale correggibile in modo univoco o fallback già autorizzati. Dati, schema, contratti, dipendenze e architettura non sono stop automatici quando rientrano nello scope approvato.

## Controlli proporzionali

| Tipo di modifica | Controllo minimo |
|---|---|
| Locale, secondo pattern esistente | Ispezione mirata, modifica minima, test pertinenti, review di correttezza e semplificazione. |
| Comportamento o requisito | Confronto con la fonte autorevole. |
| Contratto, API, dati o comportamento condiviso | Analisi di definizioni, riferimenti e impatto. |
| Dipendenza, runtime, generatore o tooling | Necessità, documentazione corrente e fattibilità. |
| Confine architetturale | Conformità alle decisioni applicabili. |
| Decisione difficile da invertire | Decisione durevole esplicita prima dell'implementazione. |

Non rendere obbligatori per ogni modifica nuovi documenti, nuove RFC, pianificazione aggiuntiva, rilettura completa del repository o review non pertinenti.

### Riconciliazione dei controlli preesistenti

- Applicare il percorso e le classificazioni centrali della sezione 7 di `rfcs/RFC-0001-principles.md`; correggere i rimandi mancanti senza ampliare un controllo ancora da riconciliare.
- Tool, indici e skill esterni non sono prerequisiti universali salvo prova locale specifica. Usare evidenze equivalenti quando soddisfano il requisito e limitare ogni blocco al perimetro che dipende dal controllo.

## Review e chiusura

- Ogni review deve indicare la revisione esaminata. Se modifiche successive cambiano materialmente la superficie valutata, riesaminare la parte interessata e ripetere le verifiche pertinenti.
- Alla chiusura della wave, quando applicabile, aggiornare le fonti rese inesatte, registrare una sola volta i fatti durevoli, archiviare gli artefatti esecutivi conclusi, aggiornare lo stato del lavoro attivo, rimuovere istruzioni obsolete e separare lavoro futuro da decisioni ancora aperte.
- Non archiviare requisiti, decisioni o comportamenti durevoli solo perché la wave è terminata.

### Closeout terminale RFC-0001

Prima del merge terminale, del commit o push che conclude la missione oppure della chiusura dell'issue, completare il closeout previsto da RFC-0001.

Verificare tutte le fonti autorevoli e i documenti `Active` interessati. Aggiornare quelli che mantengono la stessa funzione; archiviare nella stessa modifica quelli conclusi, superati, sostituiti, obsoleti o non più operativi. Prima dell'archiviazione trasferire fatti, decisioni, limiti, requisiti e obblighi di verifica ancora durevoli nella fonte corrente; rimuovere poi il documento da puntatori, indici, tracker, code di lavoro, sezioni sullo stato corrente e istruzioni operative.

I commenti GitHub forniscono tracciabilità, ma non sostituiscono la documentazione autorevole. Quando un'evidenza runtime è un criterio di accettazione, mantenere la missione aperta e non usare `Closes #N` finché tale evidenza manca. `NON APPLICABILE` richiede una motivazione concreta e verificabile.

Commit e push intermedi restano consentiti; quello terminale deve includere il closeout completato.

## Lingua e qualità editoriale

- I testi rivolti a persone devono essere in italiano; codice, identificatori, comandi, percorsi, output e termini tecnici restano nella forma più precisa.
- Prima della pubblicazione, distinguere fatti, deduzioni, decisioni, rischi e azioni, eliminare ripetizioni e affermazioni non supportate, quindi applicare `humanize-writing` quando disponibile.
- La sintesi non deve perdere requisiti, contratti, vincoli, riferimenti, condizioni di stop o significato tecnico.

## Prima di modificare il repository

Verificare:

1. Quale requisito viene soddisfatto?
2. Quali file sono realmente necessari?
3. Esiste un modo più semplice?
4. La modifica introduce duplicazioni?
5. Quali verifiche dimostreranno che il lavoro è corretto?

## Al termine del lavoro

Fornire:

- riepilogo delle modifiche;
- verifiche eseguite e relativo esito;
- eventuali informazioni mancanti;
- eventuali deduzioni utilizzate, con le rispettive fonti;
- documenti aggiornati, sostituiti o archiviati.

Non dichiarare completato un lavoro quando una verifica obbligatoria ha esito negativo.

## Scheletro iniziale dei progetti

- `templates/project/` è la fonte autorevole dello scheletro iniziale destinato ai nuovi repository.
- Lo scheletro deve rispettare `rfcs/RFC-0001-principles.md` e mantenere una sola fonte autorevole per ogni informazione operativa.
- I file copiati in un nuovo repository diventano fonti locali autonome di quel progetto; le modifiche future a `templates/project/` non si propagano automaticamente.
- Il template è autorevole solo come scheletro iniziale e non sostituisce le fonti `Active` del progetto che lo adotta.
- I file approvati nello scheletro non devono essere riscritti senza un requisito concreto e verificabile.
- `scripts/init-project.sh` è il meccanismo canonico per creare un nuovo progetto locale autonomo a partire dallo scheletro.

## Riferimento pubblico

- La versione pubblica di [RFC-0001 – Principi fondanti della Software Factory](https://github.com/skunklabs-uk/agent-os/blob/main/rfcs/RFC-0001-principles.md) corrisponde al file locale `rfcs/RFC-0001-principles.md`.
