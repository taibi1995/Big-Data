# 🚕 Analyse Big Data des Taxis aux États-Unis

> Traitement et analyse à grande échelle des données de courses de taxis à New York (Yellow Cab & FHV) avec Apache Spark. Visualisations géospatiales et analyse de tendances de l'industrie.

---

## 🎯 Objectif

Exploiter les données publiques des taxis new-yorkais (plusieurs dizaines de millions de lignes) pour extraire des **insights sur les tendances de l'industrie** : zones de forte activité, pics horaires, évolution de la demande, impact des VTC (FHV) sur les taxis traditionnels.

---

## 📦 Données

| Jeu de données | Description | Volume |
|---|---|---|
| **Yellow Cab** | Taxis jaunes traditionnels | ~50M+ courses |
| **FHV (For-Hire Vehicles)** | Uber, Lyft, autres VTC | ~30M+ courses |

Source : [NYC Taxi & Limousine Commission (TLC)](https://www.nyc.gov/site/tlc/about/tlc-trip-record-data.page)

Variables clés : `pickup_datetime`, `dropoff_datetime`, `pickup_location_id`, `dropoff_location_id`, `fare_amount`, `trip_distance`, `passenger_count`

---

## 🔬 Méthodologie

```
Ingestion (Parquet/CSV) → Traitement Spark → Agrégations → Visualisation
```

### 1. Traitement avec Apache Spark
- Lecture de fichiers Parquet multi-partitions
- Nettoyage : suppression des outliers (distances négatives, tarifs aberrants)
- Agrégations temporelles (heure, jour, mois, année)
- Jointures avec les zones géographiques TLC

### 2. Analyses réalisées
- 📍 **Heatmap géospatiale** des zones de prise en charge les plus actives
- 📈 **Évolution annuelle** du nombre de courses Yellow vs FHV (2015–2023)
- ⏰ **Distribution horaire** de la demande (rush hours, nuits de weekend)
- 💰 **Analyse tarifaire** : tarif moyen par zone et par tranche horaire
- 🔄 **Part de marché** Yellow Cab vs VTC dans le temps

---

## 📊 Visualisations

Les visualisations interactives ont été produites avec :
- **Plotly** — graphiques interactifs (évolutions temporelles, distributions)
- **Geopandas + Folium** — cartes choroplèthes et heatmaps géospatiales
- **Seaborn / Matplotlib** — analyses exploratoires

---

## 🚀 Lancer le projet

```bash
# Cloner le repo
git clone https://github.com/taibi1995/Big-Data.git
cd Big-Data

# Installer les dépendances
pip install -r requirements.txt

# Télécharger les données (lien TLC)
# Voir instructions dans data/README.md

# Lancer le notebook principal
jupyter notebook notebooks/analyse_taxis.ipynb
```

### Prérequis
- Python 3.9+
- Apache Spark 3.x (ou PySpark)
- Java 8 ou 11

---

## 🛠️ Technologies

`Apache Spark` · `PySpark` · `Python` · `Pandas` · `Plotly` · `Seaborn` · `Geopandas` · `Folium` · `Jupyter Notebook`

---

## 💡 Insights clés

- Les VTC (FHV) ont **dépassé les taxis jaunes** en volume de courses dès 2017
- Manhattan Midtown & JFK Airport concentrent **plus de 40%** des prises en charge
- Les vendredi et samedi soirs entre 22h et 2h représentent les pics de demande les plus élevés

---

## 👤 Auteur

**Younes Taibi** — [LinkedIn](https://www.linkedin.com/in/younes-taibi-47690a23a/) · [GitHub](https://github.com/taibi1995)
