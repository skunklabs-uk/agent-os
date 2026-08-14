# RFC-0001 – Principi fondanti della Software Factory

**Stato:** Active
**Versione:** 0.1.6
**Ultima modifica:** 2026-08-14

## Scopo

Questa RFC definisce i principi che governano le decisioni progettuali, implementative e documentali della Software Factory.

I principi si applicano alla Software Factory stessa e agli artefatti prodotti attraverso di essa.

## Definizione

Una **fonte autorevole** è la fonte designata dal progetto come riferimento ufficiale per una determinata informazione.

Una **fonte attiva approvata** è una fonte autorevole con stato `Active`, oppure un'issue, una pull request, una wave o un altro artefatto operativo esplicitamente approvato dall'utente o dall'autorità competente del progetto. La sola esistenza, apertura o modifica recente di un artefatto non gli conferisce autorità.

Una **missione** è un obiettivo attivo, delimitato e verificabile che produce un risultato utile per il progetto.

---

## 1. Semplicità e proporzionalità

La scelta predefinita DEVE essere la soluzione più semplice che soddisfa tutti i requisiti applicabili.

Qualsiasi complessità aggiuntiva DEVE:

- rispondere a un requisito identificabile;
- produrre un beneficio verificabile;
- non poter essere sostituita da una soluzione più semplice con risultati equivalenti.

Prima di aggiungere un'entità, uno stato, una regola, un concetto, un componente, un'automazione, un'astrazione o un documento, si DEVE verificare:

1. Esiste un modo più semplice per ottenere lo stesso risultato?
2. È possibile eliminare o riutilizzare qualcosa invece di aggiungere?
3. Il beneficio giustifica i costi di implementazione, manutenzione, test e documentazione?

La complessità priva di una giustificazione verificabile è overengineering e NON DEVE essere introdotta.

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

---

## 6. Repository come contesto operativo

Il repository è la fonte autorevole dello stato corrente del progetto.

Ogni informazione operativa DEVE avere un solo punto autorevole. Eventuali riferimenti DEVONO rimandare a tale fonte senza duplicarne il contenuto.

Ogni documento governato da questa RFC DEVE avere uno dei seguenti stati:

- `Draft`: in elaborazione e non ancora vincolante;
- `Active`: approvato e applicabile al lavoro corrente;
- `Archived`: non più applicabile al lavoro corrente.

Gli esecutori DEVONO usare per impostazione predefinita solo i documenti `Active`.

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

### Burden of proof dei test e degli strumenti

I test DEVONO proteggere comportamento osservabile, contratti o invarianti e identificare il failure mode rilevato. Un test che non fallisce quando il comportamento protetto viene violato NON è utile.

Per test, strumenti e workflow di test si DEVE preferire, nell'ordine:

1. eliminazione o nessun test quando un'altra verifica è sufficiente;
2. funzionalità nativa già disponibile;
3. tool standard, stabile e mantenuto;
4. implementazione custom.

Un custom è ammesso solo quando dimostra un gap concreto, l'assenza di un'alternativa standard sufficiente, un vantaggio verificabile, un costo di manutenzione proporzionato e un perimetro minimo.

Tool e framework DEVONO essere usati secondo documentazione upstream corrente, best practice applicabili, use case previsto e configurazione minima sufficiente.

Test di dettagli implementativi, stringhe, topologie, comportamento upstream, coverage fine a sé stessa o attestazioni procedurali partono come candidati `DELETE`, salvo che proteggano un contratto esplicito.

Non si DEVONO creare wrapper, runner o workflow custom quando gli strumenti esistenti offrono già comando, exit code, report o integrazione adeguati.

Una modifica documentale non richiede test quando il documento non è consumato da codice. Un test fuori dallo scope corrente non autorizza un audit o una remediation laterale. Prima di eliminare un test esistente si DEVE verificare che non protegga un invariante unico.

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

---

## 9. Priorità delle issue operative

La priorità rappresenta l'urgenza operativa e l'impegno corrente. NON rappresenta tipo, stato, severità o complessità dell'attività.

Ogni issue operativa DEVE avere esattamente una delle seguenti label:

| Label | Colore | Criterio |
|---|---|---|
| `priority:urgent` | `B60205` | Intervento immediato: incidente attivo, rischio di sicurezza critico o blocco corrente. |
| `priority:high` | `D93F0B` | Prossimo lavoro già impegnato, rischio elevato o scadenza vicina. |
| `priority:medium` | `FBCA04` | Lavoro pianificato e pronto, senza blocco immediato. |
| `priority:low` | `C5DEF5` | Backlog, attività sospesa o opzionale, oppure attesa di evidenze esterne. |

### Classificazione

Le condizioni DEVONO essere valutate nell'ordine seguente:

1. Dependency Dashboard e altri tracker automatici NON DEVONO ricevere una label di priorità.
2. Un incidente attivo, un rischio di sicurezza critico o un blocco corrente che richiede azione immediata è `priority:urgent`.
3. Il prossimo lavoro già impegnato, un'attività ad alto rischio o con scadenza vicina è `priority:high`.
4. Il lavoro pianificato e pronto, senza blocco immediato, è `priority:medium`.
5. Il backlog, il lavoro sospeso o opzionale e le attività in attesa di evidenze esterne sono `priority:low`.

Le pull request NON DEVONO ricevere una priorità propria: usano il contesto dell'issue collegata.

La priorità NON si propaga automaticamente tra issue dipendenti. Ogni issue DEVE essere classificata in base al proprio impatto e alla propria urgenza. Una dipendenza modifica la priorità solo quando soddisfa direttamente uno dei criteri precedenti.

Quando cambiano i fatti, la nuova priorità DEVE sostituire la precedente senza modificare le altre label dell'issue.

### Creazione e triage

Un agente DEVE determinare la priorità prima di creare un'issue operativa e applicarla nella stessa operazione. La creazione è fail-closed: se la label non è disponibile o non può essere applicata, l'issue non è considerata completata e l'agente DEVE segnalare il blocco.

Le issue create da persone o sistemi esterni senza priorità DEVONO essere classificate al primo triage. Se un'issue operativa presenta più priorità, il triage DEVE conservarne una sola. Un tracker automatico classificato per errore DEVE essere privato di tutte le label di priorità.

### Bootstrap dei repository GitHub

Quando esiste il repository GitHub, le quattro label canoniche DEVONO essere predisposte prima della prima issue operativa. Il bootstrap locale definito da `scripts/init-project.sh` resta separato e non richiede accesso a GitHub.

È sufficiente usare l'API GitHub, un connettore equivalente oppure i comandi nativi seguenti, sostituendo `OWNER/REPO`:

```bash
gh label create 'priority:urgent' --repo OWNER/REPO --color B60205 --description 'Act immediately: incident, critical security risk, or current blocker.' --force
gh label create 'priority:high' --repo OWNER/REPO --color D93F0B --description 'Next committed work, high risk, or near-term deadline.' --force
gh label create 'priority:medium' --repo OWNER/REPO --color FBCA04 --description 'Planned and ready work with no immediate blocker.' --force
gh label create 'priority:low' --repo OWNER/REPO --color C5DEF5 --description 'Backlog, hold, optional work, or waiting on external evidence.' --force
```

L'opzione `--force` rende l'operazione idempotente aggiornando colore e descrizione quando una label esiste già.

La verifica finale DEVE confermare:

- le quattro label canoniche con nome, colore e descrizione attesi nel repository;
- esattamente una priorità per ogni issue operativa sottoposta a creazione o triage;
- nessuna priorità per pull request, Dependency Dashboard e altri tracker automatici.


---

## Checklist obbligatoria

Prima di considerare completato un lavoro, verificare:

| Verifica | Esito | Evidenza o azione correttiva |
|---|---|---|
| La soluzione soddisfa tutti i requisiti applicabili? |  |  |
| Esiste un modo più semplice per ottenere lo stesso risultato? |  |  |
| Ogni complessità introdotta ha una giustificazione verificabile? |  |  |
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
| Ogni informazione operativa ha una sola fonte autorevole? |  |  |
| Sono state introdotte duplicazioni evitabili? |  |  |
| I documenti interessati hanno uno stato corretto? |  |  |
| La documentazione attiva rappresenta lo stato corrente del progetto? |  |  |
| Le verifiche producono evidenze osservabili? |  |  |
| Test, strumenti e workflow adottano la soluzione minima nell'ordine previsto e ogni custom supera il relativo burden of proof? |  |  |
