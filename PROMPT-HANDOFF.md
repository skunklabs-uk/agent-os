# Classificazione di prompt e handoff

**Stato: Active.**

In ChatGPT, Codex, Work e OMP, inclusi i sottoagenti OMP, ogni prompt o handoff generato deve iniziare con un proprio front matter YAML valido, delimitato da righe `---`. L'unico campo obbligatorio è `task_class`, presente una sola volta con uno di questi valori:

- `light`: semplice;
- `standard`: ordinario;
- `complex`: articolato o ambiguo;
- `escalation`: eccezionalmente difficile o critico.

Aggiungere `project`, `repo` e `branch` solo quando noti e pertinenti; altrimenti ometterli, senza inventare valori né chiedere chiarimenti per completarli. Se si producono più prompt o handoff, ciascuno ha il proprio front matter. Le normali risposte conversazionali sono escluse.

Prima della consegna verificare il front matter e la conformità di ciascun prompt o handoff. La classificazione descrive il lavoro: non attiva automaticamente routing, scelta del modello o metadati API. Questa istruzione guida il modello e non costituisce enforcement tecnico.
