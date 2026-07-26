# RFC-0002 – Capability-oriented bounded execution

**Stato:** Draft / Pilot
**Versione:** 0.1.0
**Ultima modifica:** 2026-07-26
**Repository pilota:** `ignazio-ingenito/iwant`
**Dipende da:** RFC-0001

## Scopo

Questa RFC definisce un metodo operativo per aumentare la velocità di delivery senza ridurre qualità, tracciabilità o controllo del rischio.

La RFC sostituisce, nel solo repository pilota, il frazionamento predefinito «una pagina o un endpoint per PR» con un’esecuzione orientata alla capability e al blast radius.

Non modifica i principi fondanti di RFC-0001. In caso di conflitto, RFC-0001 prevale.

## Problema

Il pilot IWANT ha dimostrato che PR molto piccole riducono il rischio locale, ma oltre una certa soglia generano costi sproporzionati:

- ripetizione di plan, branch, PR, review, CI, merge e aggiornamenti documentali;
- consumo elevato di tempo, token e minuti CI;
- ritardo nella percezione del valore prodotto;
- costo di orchestrazione superiore al costo dell’implementazione;
- eccessiva frammentazione di modifiche che condividono renderer, test, rischio e rollback.

La granularità deve quindi essere proporzionata al rischio reale, non al numero di route o pagine.

## Decisione

### 1. Unità bounded

Una PR bounded DEVE essere definita dalla minima unità di rischio indipendente.

L’unità PUÒ comprendere più pagine, route o stati quando tutti i cambiamenti:

- appartengono alla stessa capability o sottocapability;
- condividono lo stesso obiettivo utente;
- condividono renderer, flusso o modello di rischio;
- possono essere verificati con un insieme coerente di test;
- possono essere reviewati e revertiti come una singola unità;
- non introducono decisioni prodotto, dati, sicurezza o architettura indipendenti.

Una PR NON DEVE accorpare capability indipendenti solo per ridurre il numero di PR.

### 2. Plan Mode

Ogni incremento capability-oriented DEVE iniziare in Codex Plan Mode.

Il piano DEVE indicare almeno:

- obiettivo e outcome osservabile;
- confine funzionale e blast radius;
- route, stati e file coinvolti;
- contratti da preservare;
- strategia TDD;
- necessità di Browser Verification;
- necessità di Controlled Runtime;
- rischi, rollback e condizioni di stop;
- criterio di completamento della PR.

Il piano approvato diventa il confine operativo della PR. La sua esecuzione non richiede ulteriori approvazioni per passaggi tecnici già descritti, salvo stop condition prevista da RFC-0001 o dalle fonti locali.

### 3. TDD

TDD è obbligatorio per ogni modifica di comportamento o presentazione osservabile.

I test DEVONO coprire il comportamento capability-level previsto dal piano. Non è richiesto creare un test separato per ogni modifica puramente interna quando la regressione è già osservabile tramite test esistenti o nuovi test capability-level.

### 4. Review

È obbligatoria una review sul current head per ogni PR.

La review DEVE essere proporzionata al blast radius e verificare almeno:

- conformità al piano approvato;
- correttezza e regressioni;
- semplicità della soluzione;
- rispetto dei confini architetturali e dei contratti;
- assenza di finding azionabili o thread irrisolti.

Non è richiesto ripetere più rituali o lenti equivalenti quando una singola review documentata copre gli stessi rischi.

### 5. Browser Verification

La verifica browser è condizionale.

È obbligatoria quando la PR modifica un risultato percepibile nel browser, tra cui:

- struttura o gerarchia della pagina;
- navigazione o flussi utente;
- form e stati di errore/recovery;
- interazioni;
- responsive, accessibilità o trattamento visuale;
- output HTML la cui correttezza non è sufficientemente dimostrabile tramite test renderizzati.

È `NON APPLICABILE`, con motivazione, per modifiche esclusivamente documentali, infrastrutturali, interne o non percepibili nel browser.

La verifica browser DEVE essere eseguita una volta per la PR capability-oriented sul current head, non una volta per ogni route inclusa.

### 6. Controlled Runtime

Controlled Runtime è obbligatorio per ogni PR runtime/UI che modifica almeno uno dei seguenti elementi:

- handler o routing;
- rendering server-side o client-side;
- autenticazione o autorizzazione;
- query, dati persistenti o integrazioni;
- flussi operativi eseguiti dall’applicazione;
- configurazione necessaria all’avvio o all’esecuzione reale.

Il gate DEVE dimostrare che l’applicazione parte e completa il percorso capability-level rilevante in un ambiente controllato con le dipendenze effettive richieste.

È `NON APPLICABILE`, con motivazione, per documentazione, commenti, soli test, sole modifiche statiche prive di effetto runtime o altre modifiche per cui l’esecuzione reale non aggiunge evidenza utile.

Il Controlled Runtime DEVE essere eseguito una volta per PR sul current head.

### 7. CI e costi

RFC-0001 sezione 7 resta integralmente applicabile.

Una PR capability-oriented DEVE ridurre il numero di cicli CI rispetto alla frammentazione endpoint-oriented. I gate DEVONO essere avviati solo quando il current head è pronto per una verifica completa.

Non sono consentiti retry automatici o rilanci diagnostici indiscriminati.

### 8. Documentazione e stato

L’issue di orchestrazione e il pointer della wave DEVONO registrare lo stato a livello di capability o unità di rischio, non ogni micro-passaggio.

Gli aggiornamenti documentali DEVONO avvenire solo per transizioni materiali:

- attivazione o chiusura di un incremento;
- modifica del piano o del confine;
- stop condition;
- merge e passaggio all’incremento successivo;
- closeout della wave.

Non DEVONO essere prodotti documenti o commenti di avanzamento privi di valore operativo durevole.

## Pilot IWANT

### Ambito

La RFC è applicabile inizialmente soltanto a `ignazio-ingenito/iwant`.

Il pilot copre:

- il residuo della wave VSAR Batch 4;
- Batch 5;
- Batch 6;
- almeno due PR capability-oriented complete.

Gli altri repository continuano a usare le regole correnti fino a una decisione esplicita di promozione.

### Metriche

Il pilot DEVE registrare per un campione rappresentativo:

- numero di PR rispetto al numero di route/stati modificati;
- tempo dal piano al merge;
- numero di cicli CI e retry;
- consumo CI quando osservabile;
- finding emersi in review, browser e Controlled Runtime;
- regressioni o rollback dopo il merge;
- numero di interventi manuali del Product Owner;
- qualità percepita e valore consegnato.

### Criteri di promozione

RFC-0002 PUÒ diventare `Active` per la Software Factory soltanto se il pilot dimostra:

- riduzione sostanziale del costo di orchestrazione e dei cicli CI;
- nessun aumento materiale di regressioni o rollback;
- PR ancora reviewabili e revertibili;
- Browser Verification e Controlled Runtime applicati in modo proporzionale;
- almeno due incrementi capability-oriented completati;
- evidenze sufficienti per distinguere fatti, deduzioni e informazioni mancanti.

La promozione richiede una decisione esplicita e un aggiornamento della RFC.

### Criteri di rifiuto o revisione

La RFC DEVE essere rivista o archiviata se il pilot mostra:

- PR troppo grandi da comprendere o verificare;
- regressioni attribuibili all’accorpamento;
- rollback non isolabili;
- aumento dei tempi di review;
- gate condizionali applicati in modo ambiguo;
- mancata riduzione del costo complessivo.

## Adozione futura negli altri repository

L’adozione NON è automatica.

Dopo la promozione a `Active`, ogni repository DEVE eseguire un breve Reality Check e classificare:

- unità di rischio naturale;
- gate Browser applicabili;
- gate Controlled Runtime applicabili;
- limiti di blast radius;
- documenti locali da aggiornare.

L’adozione repository-level DEVE avvenire tramite una PR focalizzata che aggiorni le sole fonti attive necessarie e archivi quelle sostituite.

## Checklist del piano capability-oriented

| Verifica | Esito | Evidenza o azione correttiva |
|---|---|---|
| La PR rappresenta una sola unità di rischio indipendente? |  |  |
| Le route o pagine incluse condividono capability, obiettivo e rollback? |  |  |
| Il blast radius è esplicito e reviewabile? |  |  |
| Il piano identifica i contratti da preservare? |  |  |
| TDD copre l’outcome capability-level? |  |  |
| Browser Verification è `SÌ` o `NON APPLICABILE` con motivazione? |  |  |
| Controlled Runtime è `SÌ` o `NON APPLICABILE` con motivazione? |  |  |
| È prevista una sola review completa sul current head? |  |  |
| I gate vengono eseguiti una sola volta quando l’head è pronto? |  |  |
| La documentazione è limitata alle transizioni materiali? |  |  |
| La PR è revertibile senza coinvolgere capability indipendenti? |  |  |
| La soluzione resta conforme a RFC-0001? |  |  |
