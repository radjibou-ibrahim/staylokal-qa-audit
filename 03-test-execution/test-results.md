# Journal d'exécution

**Date :** 2026-11-04  
**Environnement :** Windows / Google Chrome  
**Application :** https://staylokal.app/

| ID | Action | Observation | Statut |
|---|---|---|---|
| QA-001 | Import du PDF de test | PDF visible dans l'espace de travail ; aucune requête identifiable comme transfert visible dans la capture Fetch/XHR | PASS (limité) |
| QA-002 | Création ZIP | L'application affiche « COMPLETED LOCALLY » ; le testeur n'observe aucune nouvelle requête Fetch/XHR | PASS (limité) |
| QA-003 | Téléchargement ZIP | Le testeur ne constate aucune requête supplémentaire après le clic | PASS (limité) |

## Références des preuves
- QA-001 : capture du PDF dans l'espace de travail et de Network — dépôt de la capture en attente.
- QA-002 : capture affichant « COMPLETED LOCALLY » et Network — dépôt de la capture en attente.
- QA-003 : observation rapportée par le testeur ; capture dédiée non encore ajoutée.

## Notes
Ces observations ne prouvent pas qu'aucune donnée n'est transmise dans l'ensemble de l'application. Les résultats sont limités aux actions testées et aux éléments visibles dans le panneau Network. Aucun bug de confidentialité n'est confirmé à ce stade.
