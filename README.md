# Calisthénie Coach

Application web autonome (sans dépendance, aucun serveur requis) : cours introductif, bibliothèque de mouvements illustrés, programme personnalisé évolutif et suivi de progression pour l'entraînement au poids du corps.

## Structure du dépôt

```
.
├── index.html               # l'application (tout est inclus : HTML/CSS/JS)
├── manifest.json             # configuration PWA (icône, nom, couleurs)
├── sw.js                      # service worker : mise en cache pour l'usage hors-ligne
├── icon-180.png               # icône iOS (écran d'accueil)
├── icon-192.png               # icône Android
├── icon-512.png               # icône Android / splash
└── icon-512-maskable.png      # icône adaptative Android (fond plein, sans marge)
```

Aucune étape de build : ce sont des fichiers statiques, prêts à être servis tels quels.

## Déployer sur GitHub Pages

1. Crée un dépôt GitHub et pousse ces fichiers à la racine (branche `main`).
2. Dans le dépôt : **Settings → Pages**.
3. Sous **Build and deployment**, choisis **Deploy from a branch**, branche `main`, dossier `/ (root)`.
4. Enregistre. L'app sera accessible après 1 à 2 minutes à une adresse du type :
   `https://<ton-nom-utilisateur>.github.io/<nom-du-depot>/`

Aucune configuration supplémentaire n'est nécessaire — le manifest et le service worker utilisent des chemins relatifs.

## Installer l'app sur ton téléphone

Une fois le dépôt en ligne, ouvre l'URL GitHub Pages sur ton téléphone.

**iPhone (Safari) :**
1. Ouvre l'URL dans Safari.
2. Appuie sur l'icône de partage (carré avec flèche vers le haut).
3. Choisis **Sur l'écran d'accueil**, puis **Ajouter**.

**Android (Chrome) :**
1. Ouvre l'URL dans Chrome.
2. Un bandeau **Installer l'application** apparaît automatiquement (sinon : menu ⋮ → **Installer l'application**).
3. Confirme l'installation.

Dans les deux cas, l'icône se lance en plein écran, sans barre de navigateur, comme une app native.

## Données et confidentialité

Le programme, l'historique des séances et les badges sont enregistrés **localement sur l'appareil** (`localStorage` du navigateur), pas sur un serveur. Rien n'est envoyé nulle part. Cela signifie aussi que les données sont propres à chaque appareil/navigateur : pas de synchronisation entre ton téléphone et un ordinateur par exemple.

## Mettre à jour l'app

Pour republier une nouvelle version : remplace les fichiers modifiés dans le dépôt et pousse (`git push`). GitHub Pages redéploie automatiquement. Le service worker met en cache la version précédente le temps d'un chargement ; un rafraîchissement (ou une réouverture) récupère la nouvelle version.
