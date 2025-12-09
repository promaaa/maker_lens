# MakerLens

MakerLens est une application web conçue pour accompagner les makers dans la création et le recyclage d'objets. Elle permet de découvrir, rechercher et consulter des tutoriels techniques structurés (low-tech, Arduino, bricolage).

## Fonctionnalités

- **Mode Création** : Rechercher des tutoriels pour fabriquer un objet à partir de zéro
- **Mode Recyclage** : Trouver des idées pour réutiliser et transformer des objets existants
- **Navigation** : Explorer les tutoriels tendance de la communauté maker
- **Filtres avancés** : Trier par difficulté, durée estimée et coût

## Structure du projet

```
maker_lens/
├── interface/           # Application web (HTML, CSS, JS)
│   ├── index.html       # Point d'e´ntrée principal
│   ├── css/             # Feuilles de style
│   ├── js/              # Scripts JavaScript (recherche, génération)
│   └── assets/          # Images et ressources statiques
├── donnees/             # Données JSON des tutoriels
│   ├── data_exemple.json    # Base de données des tutoriels
│   ├── harmonizer.py        # Convertisseur JSON vers HTML
│   └── STRUCTURE.md         # Documentation du format JSON
├── scripts_recuperation/    # Scripts Python de scraping
└── documentation/           # Documentation et tutoriels générés
```

## Installation et lancement

### Option 1 : Ouverture locale

Ouvrir le fichier `interface/index.html` directement dans un navigateur web.

### Option 2 : Version en ligne

Accéder à l'application via GitHub Pages : [https://promaaa.github.io/maker_lens/](https://promaaa.github.io/maker_lens/)

### Option 3 : Serveur local (recommandé pour le développement)

```bash
cd interface
python3 -m http.server 8000
```

Puis ouvrir [http://localhost:8000](http://localhost:8000) dans un navigateur.

## Format des données

Les tutoriels sont stockés au format JSON avec une structure standardisée :

| Champ | Description |
|-------|-------------|
| `titre` | Nom du tutoriel |
| `difficulte` | Facile, Moyen ou Difficile |
| `duree` | Temps estimé de réalisation |
| `cout` | Fourchette de prix |
| `materiaux` | Liste des matériaux nécessaires |
| `outils` | Liste des outils requis |
| `etapes` | Instructions détaillées par étape |

La documentation complète du format est disponible dans `donnees/STRUCTURE.md`.

## Ajouter un tutoriel

1. Éditer le fichier `donnees/data_exemple.json`
2. Suivre la structure décrite dans `donnees/STRUCTURE.md`
3. Générer la version HTML avec le convertisseur :
   ```bash
   cd donnees
   python3 harmonizer.py
   ```

## Technologies utilisées

- HTML5, CSS3, JavaScript (vanilla)
- Fuse.js pour la recherche floue
- Python 3 + Jinja2 pour la génération HTML
- BeautifulSoup pour le scraping de tutoriels

## Auteurs

Equipe MakerLens - Projet Fil Rouge TAF COUAD 2025

## Licence

Ce projet est distribué sous licence MIT. Voir le fichier `LICENSE` pour plus de détails.
