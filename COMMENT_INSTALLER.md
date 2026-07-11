# Norway Odonata Field Key — comment l'installer comme une vraie appli

Ce dossier contient une PWA (Progressive Web App) : une appli installable, avec
sa propre icône, qui s'ouvre en plein écran sans barre de navigateur, et qui
fonctionne entièrement hors-ligne une fois installée.

## Option A — La plus simple : héberger le dossier (5 min, gratuit)

Un fichier PWA doit être servi en HTTPS pour être "installable" (limitation
technique des navigateurs, pas la mienne). Le plus simple et gratuit :

1. Va sur https://github.com et crée un compte si tu n'en as pas.
2. Crée un nouveau dépôt (repository), par exemple `dragonfly-key`.
3. Dépose les 5 fichiers de ce dossier dedans (index.html, manifest.json,
   sw.js, icon-192.png, icon-512.png) — glisser-déposer sur github.com suffit,
   pas besoin de ligne de commande.
4. Dans les réglages du dépôt → **Pages** → active GitHub Pages sur la
   branche principale.
5. Tu obtiens une adresse du type `https://tonpseudo.github.io/dragonfly-key/`.
   Ouvre-la une fois avec ton téléphone (connecté), puis :
   - **Android/Chrome** : un bandeau "Ajouter à l'écran d'accueil" apparaît
     automatiquement (ou menu ⋮ → "Installer l'application").
   - **iPhone/Safari** : bouton Partager → "Sur l'écran d'accueil".
6. Une fois installée, l'icône apparaît sur ton écran d'accueil. Elle s'ouvre
   en plein écran, sans barre de navigateur, et fonctionne sans connexion
   (le service worker a mis toute l'appli en cache dès la première ouverture).

## Option B — Zéro compte, zéro hébergement

Si tu ne veux rien héberger : installe une appli gratuite de "visionneuse
HTML locale" depuis le Play Store / App Store (ex. recherche "local html
viewer" ou "offline browser"), puis ouvre `index.html` avec. Ça s'affiche
comme une appli, sans barre d'adresse. Le manifest/service worker ne servent
à rien dans ce cas (pas nécessaires : le fichier est déjà 100% autonome et
fonctionne sans connexion dès l'ouverture).

## Option C — Le plus basique

Ouvrir simplement `index.html` avec le navigateur du téléphone. Ça marche
hors-ligne aussi (aucune requête réseau dans le code), mais la barre du
navigateur reste visible.

---
Dans tous les cas, aucune connexion n'est nécessaire une fois l'appli
ouverte/installée — tout le contenu (les 42 espèces) est inclus dans le code.
