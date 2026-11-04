# Cas de test

## QA-001 — Importer un PDF et observer le réseau

**Objectif :** Vérifier si l'import du PDF de test déclenche une requête visible qui semble envoyer le fichier.

**Préconditions :** StayLokal ouvert dans Chrome ; DevTools Network disponible ; PDF de test non sensible préparé.

**Étapes :**
1. Effacer la liste Network.
2. Sélectionner Fetch/XHR.
3. Importer le PDF dans l'espace de travail StayLokal.
4. Observer les requêtes visibles.
5. Noter toute requête suspecte pour examen.

**Attendu :** Si ce parcours est traité localement, aucune requête contenant le fichier ou son contenu ne doit être observée.

**Observé :** Le PDF apparaît dans l'espace de travail. Sur la capture fournie, la liste Fetch/XHR visible contient des ressources JavaScript et `pdf.worker.min.js`. Aucune requête identifiable comme un transfert du fichier n'est apparente.

**Statut :** PASS — observation limitée, ne prouve pas la confidentialité de toute l'application.

## QA-002 — Créer une archive ZIP et observer le réseau

**Objectif :** Observer le trafic réseau pendant la création d'une archive ZIP à partir du fichier importé.

**Étapes :**
1. Garder DevTools Network ouvert.
2. Effacer la liste des requêtes.
3. Déclencher **Create ZIP**.
4. Observer Fetch/XHR et le message de fin de traitement.

**Attendu :** Si l'archive est créée localement, aucune requête transmettant le fichier ne doit être observée.

**Observé :** L'application affiche **COMPLETED LOCALLY**. Le testeur indique qu'aucune nouvelle requête Fetch/XHR n'apparaît après le clic sur Create ZIP.

**Statut :** PASS — comportement cohérent avec un traitement local pour cette action.

## QA-003 — Télécharger le ZIP et observer le réseau

**Objectif :** Vérifier si le clic sur le téléchargement de l'archive déclenche une requête supplémentaire visible.

**Étapes :**
1. Garder Network ouvert et sélectionner All.
2. Effacer la liste.
3. Cliquer sur le contrôle de téléchargement de l'archive.
4. Observer l'apparition éventuelle d'une nouvelle requête.

**Attendu :** Aucun envoi inattendu du fichier source ne doit être observé.

**Observé :** Le testeur indique qu'aucune requête supplémentaire n'apparaît après le téléchargement.

**Statut :** PASS — selon l'observation du testeur ; tous les mécanismes et détails du téléchargement n'ont pas été vérifiés indépendamment.

## Scénarios complémentaires
- Répéter avec d'autres types et tailles de fichiers.
- Observer toutes les catégories de requêtes pendant chaque opération.
- Examiner les service workers et WebSockets si nécessaire.
- Inspecter les payloads et destinations des requêtes suspectes.
- Tester séparément les autres fonctionnalités de StayLokal.
