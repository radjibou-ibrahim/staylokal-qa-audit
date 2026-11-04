# Publication LinkedIn — Mini-audit QA StayLokal

Un fichier importé dans une application web est-il forcément envoyé sur un serveur ?

Pour explorer cette question, j'ai réalisé un mini-audit QA de StayLokal avec Windows, Google Chrome et Chrome DevTools.

Deux opérations ont été observées :

**1. Import d'un PDF**
- Le document apparaît dans l'espace de travail.
- Dans la vue Fetch/XHR observée, aucune requête identifiable comme un transfert du PDF n'était visible.

**2. Création d'une archive ZIP**
- L'application affiche « COMPLETED LOCALLY ».
- Aucune nouvelle requête Fetch/XHR n'a été observée au déclenchement de cette opération.

Après le clic sur le téléchargement de l'archive, aucune requête supplémentaire n'a été observée selon le test réalisé.

**Conclusion prudente :** les observations sont cohérentes avec un traitement local pour ces opérations précises. Elles ne prouvent pas l'absence de transmission dans toute l'application ; des tests complémentaires restent nécessaires.

Cette démarche illustre une partie essentielle du métier QA : formuler une hypothèse, concevoir un test, observer le comportement réel et communiquer des conclusions fondées sur les preuves.

#QualityAssurance #SoftwareTesting #QA #WebTesting #Privacy #ChromeDevTools
