# Flashcards faciles — version 2

Application web progressive (PWA) en français, pensée pour iPhone. Aucun compte ni serveur nécessaire pour les fonctions incluses.

## Fonctionnalités
- Paquets de flashcards, ajout/modification/suppression de cartes
- Session de révision, retournement des cartes et mélange
- Répétition espacée locale : réponse sue → intervalles progressifs (1, 3, puis environ 2,2×, plafonné à 60 jours) ; à revoir → nouvelle présentation rapprochée
- Statistiques locales : cartes, révisions, taux de réponses sues, cartes dues et série de jours actifs
- Partage d'un paquet via la feuille de partage iOS si prise en charge, sinon export JSON à envoyer
- Import/export JSON et sauvegarde
- Ajout en lot avec format « Question :: Réponse », une carte par ligne
- Cache de ressources pour ouverture hors ligne après première visite HTTPS

## Limite sur la génération IA
Cette version n'intègre pas de modèle d'IA ni de traitement PDF automatique. Le traitement local en lot accepte le format `Question :: Réponse`. Une génération IA depuis un cours ou PDF nécessiterait un service d'IA externe, une connexion et éventuellement une clé API côté serveur ; ne placez jamais une clé secrète directement dans le code client.

## Installation sur iPhone
Une PWA doit être servie en HTTPS pour permettre le service worker et une expérience installable.
1. Décompressez le ZIP sur un ordinateur.
2. Connectez-vous à GitHub et créez un dépôt (public pour utiliser GitHub Pages gratuitement selon la configuration de compte).
3. Téléversez `index.html`, `manifest.json`, `sw.js` et `icon.svg` à la racine du dépôt, puis validez les changements.
4. Ouvrez **Settings → Pages**.
5. Dans **Build and deployment**, choisissez **Deploy from a branch**, branche `main`, dossier `/ (root)`, puis **Save**.
6. Attendez que GitHub Pages affiche l'adresse du site.
7. Sur l'iPhone, ouvrez cette adresse dans **Safari**.
8. Touchez **Partager → Sur l’écran d’accueil → Ajouter**.
9. Lancez l'icône. Visitez le site une fois en ligne avant de compter sur le mode hors ligne.

## Importer un paquet reçu
Dans l'application, touche **Importer**, sélectionne le fichier `.json` reçu. Les cartes importées sont ajoutées à tes paquets.

## Données et sauvegardes
- Tout est enregistré dans le stockage local du navigateur. Il n'y a pas de synchronisation entre appareils.
- Exporte régulièrement les données. Effacer les données de Safari peut supprimer les cartes.
- Le partage exporte les questions/réponses, pas l'historique de révision.
