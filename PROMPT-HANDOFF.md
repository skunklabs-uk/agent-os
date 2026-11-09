# Prompt, handoff e scelta del modello

**Stato: Active.**

## Classificazione di prompt e handoff

In ChatGPT, Codex, Work e OMP, inclusi i sottoagenti OMP, ogni prompt o handoff generato deve iniziare con un proprio front matter YAML valido, delimitato da righe `---`. L'unico campo obbligatorio è `task_class`, presente una sola volta con uno di questi valori:

- `light`: semplice;
- `standard`: ordinario;
- `complex`: articolato o ambiguo;
- `escalation`: eccezionalmente difficile o critico.

Aggiungere `project`, `repo` e `branch` solo quando noti e pertinenti; altrimenti ometterli, senza inventare valori né chiedere chiarimenti per completarli. Se si producono più prompt o handoff, ciascuno ha il proprio front matter. Le normali risposte conversazionali sono escluse.

Prima della consegna verificare il front matter e la conformità di ciascun prompt o handoff. La classificazione descrive il lavoro: non attiva automaticamente routing, scelta del modello o metadati API. Questa istruzione guida il modello e non costituisce enforcement tecnico.

## Scelta del modello

Per ogni incarico, principale o delegato, valutare difficoltà, ambiguità e conseguenze dell'errore. Quando il client consente di scegliere il modello all'avvio o per una delega, selezionarne uno adeguato:

| Tipo di incarico | Modello di riferimento |
| --- | --- |
| Semplice e circoscritto | `gpt-6-luna` |
| Ordinario | `gpt-6.1-terra` |
| Complesso o ambiguo | `gpt-6.1-sol` |
| Eccezionalmente difficile o critico | `gpt-6-astra` |

La difficoltà non dipende soltanto dal tipo di attività. Rispettare la scelta esplicita dell'utente e usare solo modelli e provider disponibili e autorizzati nel contesto. Non presumere di poter cambiare il modello della sessione in corso. Se il client non consente la selezione o il modello non è disponibile, segnalare il limite senza dichiarare che la selezione sia avvenuta.

Usare le capacità native del client per la selezione. La classificazione richiesta sopra non seleziona automaticamente il modello né attiva routing LiteLLM; la guida non garantisce una scelta sempre corretta o una riduzione della spesa.
