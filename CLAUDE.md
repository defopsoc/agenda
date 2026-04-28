# Agent Agenda — Instructions

## Rôle

Tu gères le fichier `agenda.json` de ce repo.
Ce fichier alimente un calendrier public visible sur GitHub Pages.
Après chaque modification, tu fais un `git add agenda.json && git commit -m "..." && git push`.

## Structure d'un événement

```json
{
  "title" : "Disponible | Occupé | Projet / Mission",
  "start" : "AAAA-MM-JJTHH:MM:SS",
  "end"   : "AAAA-MM-JJTHH:MM:SS",
  "color" : "#22c55e | #ef4444 | #3b82f6"
}
```

Couleurs :
- `#22c55e` → Disponible (vert)
- `#ef4444` → Occupé (rouge)
- `#3b82f6` → Projet / Mission (bleu)

Pour un événement sur toute la journée, utilise le format `"AAAA-MM-JJ"` sans heure.
Pour une plage multi-jours sans heure, `end` doit être le lendemain du dernier jour (convention FullCalendar).

## Commandes reconnues

| Commande naturelle                              | Action                                         |
|-------------------------------------------------|------------------------------------------------|
| "Ajoute disponible le 15 mai de 9h à 17h"      | Ajoute un événement vert                       |
| "Bloque la semaine du 2 juin"                   | Ajoute un événement rouge du 02 au 07 juin     |
| "Marque juillet comme occupé"                   | Ajoute un événement rouge du 01 au 31 juillet  |
| "Ajoute mission du 10 au 20 mai"                | Ajoute un événement bleu                       |
| "Supprime les créneaux de mai"                  | Retire tous les événements dont start contient "2026-05" |
| "Montre les créneaux du mois prochain"          | Affiche les événements du mois suivant (lecture seule) |

## Règles strictes

1. Ne jamais supprimer `index.html` ni `CLAUDE.md`.
2. Toujours valider que le JSON reste valide après modification.
3. Le message de commit doit résumer l'action, ex : `agenda: ajoute disponibilité 15 mai`.
4. Si la demande est ambiguë, demander confirmation avant d'écrire.

## Lien public

https://defopsoc.github.io/agenda
