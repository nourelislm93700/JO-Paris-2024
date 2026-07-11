# My Paris World 2024 - Guide touristique JO Paris 2024

Site web statique (HTML/CSS/JS) présentant un guide touristique de Paris à l'occasion des Jeux Olympiques 2024 : sites à découvrir, restaurants, activités, calendrier des épreuves, transports et un formulaire de contact/avis.

## Pages du site

| Page | Description |
|---|---|
| `paris.html` | Page principale : présentation de Paris, sites touristiques, restaurants, activités en famille et carte interactive. |
| `Evénements.html` | Guide des Jeux Olympiques de Paris 2024 : dates, lieux, épreuves, billetterie, hébergement. |
| `contact.html` | FAQ et formulaire de contact (identification + description du problème) avec système de feedback de satisfaction. |
| `avis.html` | Formulaire pour laisser un avis sur le site, avec sélection de département (auto-remplissage du code postal). |

> Le menu de navigation référence aussi `Projet web.html` (page d'accueil) et `Transport.html` (informations transport/métro/Navigo), mais ces fichiers ne sont pas présents dans ce dépôt.

## Structure du projet

```
src/
├── paris.html / paris.css              # Page d'accueil (sites, restaurants, activités)
├── Evénements.html / events.css        # Calendrier et informations JO 2024
├── contact.html / contact.css          # FAQ et formulaire de contact
├── avis.html / contact.css             # Formulaire d'avis
├── projet.js                           # Référencé par toutes les pages (absent du dépôt)
├── logoJO.jpg, jeux-olympiques.png     # Logos
├── img*.png / img*.jpg                 # Photos des sites touristiques, restaurants, activités
├── metro*.png, ligne*.png, navigo*.png # Visuels transport (métro, lignes, Pass Navigo)
├── map.png, map1.png, map2.png         # Cartes de Paris
└── *.mp3                               # Sons d'ambiance et guides audio (greedy.mp3, audioNav*, navigo*, paris.mp3, étoile.mp3)
```

## Fonctionnalités

- Navigation par ancre vers les sections "Découvrir", "Restaurants", "Activités" et "Carte" sur la page d'accueil.
- Liens externes vers les sites officiels des monuments, restaurants et activités (Tour Eiffel, Louvre, Château de Versailles, Disneyland Paris, etc.).
- Effets sonores au survol de certains liens (`onmouseover="playSoundParis()"`, `greedy()`).
- Formulaire de contact avec FAQ et boutons de feedback de satisfaction.
- Formulaire d'avis avec remplissage automatique du code postal selon le département sélectionné (JavaScript inline).
- Design entièrement personnalisé en CSS (pas de framework externe type Bootstrap).

## Prérequis

Aucun : le site est 100% statique (HTML/CSS/JS). Un navigateur web suffit.

## Lancer le site en local

Ouvrir directement `src/paris.html` dans un navigateur, ou servir le dossier avec un petit serveur local (recommandé pour que les chemins relatifs et les fichiers audio fonctionnent correctement) :

```bash
cd src
python3 -m http.server 8000
```

Puis ouvrir `http://localhost:8000/paris.html`.

## Limites connues

- `projet.js` est référencé dans les 4 pages mais absent du dépôt : les fonctions `playSoundParis()`, `greedy()`, `defilerMessages()` et `sendFeedback()` ne s'exécuteront pas tant que ce fichier n'est pas ajouté.
- Les pages `Projet web.html` et `Transport.html`, liées depuis le menu, sont absentes du dépôt.
- Les formulaires (`contact.html`) pointent vers `traitement.php`, également absent (nécessiterait un serveur PHP pour être fonctionnel).
- `paris.html` référence une favicon avec un chemin local Windows (`C:\Users\...`) au lieu d'un chemin relatif — à corriger pour un affichage correct hors de la machine d'origine.

## Auteur

Nour El Islam EL-HADJ MIMOUNE
