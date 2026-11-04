# Périmètre et approche de test

## Objectif
Observer certaines opérations de traitement de fichiers de StayLokal dans Chrome DevTools afin de repérer d'éventuelles requêtes réseau visibles qui sembleraient transmettre le fichier de test.

## Environnement
- Système : Windows
- Navigateur : Google Chrome
- Application : https://staylokal.app/
- Outil : Chrome DevTools — Network
- Vues utilisées : Fetch/XHR et All, selon les observations rapportées.

## Scénarios inclus
1. Importer un PDF de test non sensible.
2. Observer les requêtes réseau visibles après l'import.
3. Créer une archive ZIP à partir du fichier importé.
4. Observer Network pendant la création de l'archive.
5. Télécharger l'archive et observer Network.

## Méthode
1. Ouvrir DevTools avec F12.
2. Sélectionner Network et effacer la liste avant l'action.
3. Observer Fetch/XHR, puis All lorsque nécessaire.
4. Déclencher une seule action à la fois.
5. Examiner les requêtes suspectes : méthode, domaine, en-têtes, payload et taille transférée.
6. Consigner uniquement les observations étayées par les captures ou le compte rendu direct du testeur.

## Limites
- Pas d'analyse complète du code source.
- Pas d'analyse forensique complète du navigateur.
- Toutes les fonctionnalités et tous les mécanismes réseau ne sont pas couverts.
- Pas d'accès aux journaux serveur ni à l'infrastructure.
- Aucune garantie définitive d'absence de transmission de données.

L'absence de nouvelle requête Fetch/XHR visible ne prouve pas, à elle seule, l'absence de toute communication réseau. Les autres types de requêtes, service workers, WebSockets, beacons et parcours non testés peuvent nécessiter une analyse distincte.

Aucun niveau de sévérité n'est attribué aux observations positives actuelles. Tout défaut futur devra être reproductible et documenté avant d'être signalé.
