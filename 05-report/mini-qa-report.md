# StayLokal — Rapport préliminaire de mini-audit QA

**Date :** 2026-11-04  
**Environnement :** Windows / Google Chrome  
**Périmètre :** import PDF, création ZIP et observations réseau lors du téléchargement ZIP  
**État :** Préliminaire — tests complémentaires recommandés

## Objectif
Observer si certaines opérations de traitement de fichiers de StayLokal génèrent des requêtes réseau visibles qui semblent transmettre le fichier source.

## Résultats

### QA-001 — Import PDF
Le PDF de test apparaît dans l'espace de travail. La capture Fetch/XHR fournie montre des ressources JavaScript et `pdf.worker.min.js`. Aucune requête identifiable comme transfert du PDF n'est apparente dans la liste visible.

**Résultat :** aucun transfert identifiable du fichier observé dans la vue capturée.

### QA-002 — Création ZIP
L'application affiche **COMPLETED LOCALLY** après l'opération. Le testeur indique qu'aucune nouvelle requête Fetch/XHR n'apparaît au clic sur Create ZIP.

**Résultat :** comportement cohérent avec un traitement local pour cette opération.

### QA-003 — Téléchargement ZIP
Le testeur indique qu'aucune requête supplémentaire n'apparaît après le clic sur le téléchargement de l'archive.

**Résultat :** aucune requête supplémentaire observée selon le compte rendu du testeur.

## Conclusion
Le comportement observé dans les parcours testés est cohérent avec un traitement local des fichiers. Aucun transfert du fichier n'a été identifié dans les observations Network fournies.

Il s'agit d'une observation limitée côté navigateur, et non d'un audit complet de confidentialité ou de sécurité. Elle ne démontre pas qu'aucune donnée n'est jamais transmise par une autre fonctionnalité ou un autre mécanisme réseau. Des tests complémentaires sont nécessaires avant toute conclusion plus générale.

## Défauts
Aucun défaut reproductible n'a été confirmé dans le périmètre actuel. Le rapport consigne pour le moment des observations positives plutôt que des bugs.

## Tests complémentaires recommandés
1. Répéter les parcours avec d'autres types de fichiers.
2. Observer toutes les catégories de requêtes pendant le parcours complet.
3. Examiner les service workers, WebSockets et destinations suspectes, le cas échéant.
4. Inspecter les payloads et tailles transférées des requêtes pertinentes.
5. Étendre la couverture fonctionnelle aux autres outils de traitement de fichiers.
