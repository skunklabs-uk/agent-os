# POC #32 — probe report-only Codex native multi-agent

## Missione

Verificare sul runtime Codex realmente usato dal consumer Developer Workspace che la capability native multi-agent sia effettivamente disponibile e utilizzabile con l'autenticazione ChatGPT corrente.

Questo è un probe di capacità, non il benchmark single vs multi.

## Vincoli

- Leggi e applica `AGENTS.md` e RFC-0001 correnti già fornite dal collegamento.
- Non modificare alcun file.
- Non fare commit, push, PR, merge, deploy o dispatch/rerun CI.
- Non invocare un secondo processo `codex`, non usare il launcher `/usr/local/bin/codex` e non tentare update della CLI.
- Non usare web/network.
- Usa esclusivamente il multi-agent **nativo della sessione Codex corrente**.
- Non simulare una delega: se `spawn_agent`/equivalente non è disponibile o fallisce, dichiaralo chiaramente come esito del probe.
- Non allargare sandbox o permessi.

## Probe

1. Senza leggere direttamente il contenuto richiesto, delega a **esattamente un subagent nativo** questo incarico:
   - leggere `README.md`;
   - restituire il primo heading Markdown;
   - restituire anche lo SHA-256 del contenuto completo di `README.md` usando strumenti locali disponibili.
2. Attendi il risultato del subagent.
3. Verifica localmente, nel root agent, lo SHA-256 di `README.md` e confrontalo con quello restituito dal subagent.
4. Non delegare altri task.

## Output richiesto

Nel summary finale riporta soltanto:

- versione Codex della sessione se osservabile senza avviare un nuovo Codex; altrimenti `NON OSSERVABILE DAL CHILD`;
- se un vero subagent è stato creato: `SÌ/NO`;
- identificatore/task-name/nickname del subagent, se il tool lo espone;
- primo heading restituito dal subagent;
- SHA-256 restituito dal subagent;
- SHA-256 verificato dal root;
- confronto hash: `PASS/FAIL`;
- numero totale di subagent creati;
- `git status --short` finale;
- eventuali limiti del probe.

Il probe è PASS soltanto se un vero subagent viene creato, termina correttamente, gli hash coincidono e il checkout resta pulito.
