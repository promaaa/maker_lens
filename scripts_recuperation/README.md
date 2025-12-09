# Scripts de Récupération

Ce dossier contient les outils permettant de récupérer (scraper) les tutoriels « makers » depuis différents sites, puis de les mettre en forme automatiquement.

## Structure

- **`scripts/`** : Scripts principaux de scraping.
├──  instructables_scraper.py              # Scraper instructables
├──  lowtechlab_scraper.py                 # Scraper lowtechlab
└──  wikifab.py                            # Scraper wikifab
- **`analyseurs/`** : Scripts d'analyse et de parsing des pages.
├──  html_to_json_Instructables.py         # Conversion instructables
├──  html_to_json_lowtech.py               # Conversion lowtechlab
└──  html_to_json_wikifab.py               # Conversion wikifab
- **`donnees_brutes/`** : Données JSON brutes extraites.
- **`pages_brutes/`** : Pages HTML brutes téléchargées.
- **`utilitaires/`** : Fonctions utilitaires partagées.
└──  harmonizer.py                         # Visualisation des pages scraper après la conversion en json

## Utilisation

Consultez les scripts individuels pour les instructions d'exécution.


## Flux de Traitement

```
1  SCRAPING               HTML brut 
   scripts/              pages_brutes/
                              ↓        
2️  CONVERSION               JSON   
   analyseurs/         donnees_brutes/ 
                              ↓
3️  HARMONISATION        JSON structuré
   utilitaires/       donnees_harmonisees/
                              ↓
4  CONCATENATION        Base de données
donnees_harmonisees/    interface/data/
```
