# Prompt, handoff e scelta del modello

**Stato: Active.**

## Classificazione di prompt e handoff

In ChatGPT, Codex, Work e OMP, inclusi i sottoagenti OMP, ogni prompt o handoff generato deve iniziare con un proprio front matter YAML valido, delimitato da righe `---`, e includere una sola volta i campi obbligatori `task_class`, `model_profile` e `model`. `task_class` deve avere uno di questi valori:

- `light`: semplice;
- `standard`: ordinario;
- `complex`: articolato o ambiguo;
- `escalation`: eccezionalmente difficile o critico.
`model_profile` deve ripetere esattamente il valore di `task_class` (`light`, `standard`, `complex` o `escalation`). È il profilo del singolo incarico, non il profilo di configurazione OMP selezionato con `--profile` (`personal`, per esempio).

`model` è il campo nativo OMP per selezionare un ruolo (`"@smol"`, `"@default"`, `"@slow"`, `"@escalation"`) o un selettore esatto `provider/model-id`. Se il valore inizia con `@`, racchiuderlo tra virgolette nel YAML, per esempio `model: "@smol"`. La tabella in «Scelta del modello» definisce la corrispondenza. Usare un ruolo solo se la sua assegnazione effettiva punta al modello di riferimento; altrimenti indicare il selettore esatto. `escalation` è un ruolo personalizzato da definire nel profilo OMP attivo.

Aggiungere `project`, `repo` e `branch` solo quando noti e pertinenti; altrimenti ometterli, senza inventare valori né chiedere chiarimenti per completarli. Se si producono più prompt o handoff, ciascuno ha il proprio front matter. Le normali risposte conversazionali sono escluse.

Per esempio, per una escalation selezionata tramite il ruolo dedicato:

```yaml
---
task_class: escalation
model_profile: escalation
model: "@escalation"
---
```

Per usare un ruolo OMP, il valore deve essere un alias, non il nome nudo:

```yaml
---
task_class: light
model_profile: light
model: "@smol"
---
```

Prima della consegna verificare il front matter e la conformità di ciascun prompt o handoff. `task_class` e `model_profile` descrivono la classe dell'incarico; `model` dichiara il modello richiesto. OMP interpreta `model` nel front matter delle definizioni dei propri agenti; in un normale prompt o handoff testuale il campo non cambia da solo il modello della sessione. Il client o il dispatcher deve applicarlo con le proprie capacità native. Non attiva routing LiteLLM né costituisce enforcement tecnico.

## Scelta del modello

Per ogni incarico, principale o delegato, valutare difficoltà, ambiguità e conseguenze dell'errore. Quando il client consente di scegliere il modello all'avvio o per una delega, selezionarne uno adeguato. `model_profile` deve corrispondere a `task_class`; `model` deve contenere l'alias OMP quotato indicato solo quando il profilo attivo lo assegna al modello di riferimento.

| `task_class` | `model_profile` | Alias OMP da usare in `model` (valore YAML) | Modello di riferimento |
| --- | --- | --- | --- |
| `light` | `light` | `"@smol"` | `gpt-6-luna` |
| `standard` | `standard` | `"@default"` | `gpt-6.1-terra` |
| `complex` | `complex` | `"@slow"` | `gpt-6.1-sol` |
| `escalation` | `escalation` | `"@escalation"` | `gpt-6-astra` |

Se il ruolo OMP non è assegnato al modello di riferimento, valorizzare `model` con il selettore esatto disponibile, per esempio `openai-codex/gpt-6.1-sol`. Non presumere che un ruolo abbia la stessa assegnazione in profili OMP diversi.

La difficoltà non dipende soltanto dal tipo di attività. Rispettare la scelta esplicita dell'utente e usare solo modelli e provider disponibili e autorizzati nel contesto. Non presumere di poter cambiare il modello della sessione in corso. Se il client non consente la selezione o il modello non è disponibile, segnalare il limite senza dichiarare che la selezione sia avvenuta.

Per attività circoscritte e a basso rischio, valutare la delega a un modello economico adeguato: ricerca di file e riferimenti, recupero di documentazione e testi, lettura, filtraggio ed estrazione di informazioni dai log, raccolta di evidenze e risultati dei test, e attività elementari equivalenti. Il coordinatore conserva la responsabilità dell'interpretazione, delle decisioni e della verifica dei risultati. Delegare solo quando il beneficio atteso supera l'overhead; altrimenti svolgere direttamente l'operazione. Difficoltà, ambiguità o criticità possono richiedere un modello superiore anche per queste attività.

Usare le capacità native del client per la selezione. La classificazione richiesta sopra non seleziona automaticamente il modello né attiva routing LiteLLM; la guida non garantisce una scelta sempre corretta o una riduzione della spesa.
