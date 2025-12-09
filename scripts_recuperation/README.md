# Scripts de Récupération

Ce dossier contient les outils permettant de récupérer (scraper) les tutoriels « makers » depuis différents sites, puis de les mettre en forme automatiquement.

## Structure
```
- scripts/                          # Scripts principaux de scraping
│   ├── instructables_scraper.py    # Scraper Instructables
│   ├── lowtechlab_scraper.py       # Scraper Lowtech Lab
│   └── wikifab.py                  # Scraper Wikifab
│
- analyseurs/                       # Scripts d'analyse et de parsing des pages
│   ├── html_to_json_Instructables.py  # Conversion Instructables
│   ├── html_to_json_lowtech.py        # Conversion Lowtech Lab
│   └── html_to_json_wikifab.py        # Conversion Wikifab
│
- donnees_brutes/                   # Données JSON brutes extraites
│
- pages_brutes/                     # Pages HTML brutes téléchargées
│
- utilitaires/                      # Fonctions utilitaires partagées
    └── harmonizer.py               # Visualisation des pages scrapers après conversion en JSON
```
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
