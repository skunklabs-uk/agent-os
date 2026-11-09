# Scelta del modello per incarico

**Stato: Active.**

Per ogni incarico, principale o delegato, valutare difficoltà, ambiguità e conseguenze dell'errore. Quando il client consente di scegliere il modello all'avvio o per una delega, selezionarne uno adeguato:

| Tipo di incarico | Modello di riferimento |
| --- | --- |
| Semplice e circoscritto | `gpt-6-luna` |
| Ordinario | `gpt-6.1-terra` |
| Complesso o ambiguo | `gpt-6.1-sol` |
| Eccezionalmente difficile o critico | `gpt-6-astra` |

La difficoltà non dipende soltanto dal tipo di attività. Rispettare la scelta esplicita dell'utente e usare solo modelli e provider disponibili e autorizzati nel contesto. Non presumere di poter cambiare il modello della sessione in corso. Se il client non consente la selezione o il modello non è disponibile, segnalare il limite senza dichiarare che la selezione sia avvenuta.

Usare le capacità native del client per la selezione; non è richiesta una chiamata separata per classificare l'incarico né un front matter o una classe esplicita nei prompt. Questa istruzione guida la scelta dell'agente e non garantisce che sia sempre corretta o che riduca la spesa. Non attiva automaticamente il routing LiteLLM.
