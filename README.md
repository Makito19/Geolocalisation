# 📡 Localisation par cartes RSSI avec Réseaux de Neurones

Ce projet vise à estimer la position d’un dispositif dans un environnement industriel à partir de la puissance du signal Wi-Fi reçue depuis plusieurs passerelles (bornes). Pour cela, nous utilisons un réseau de neurones dense entraîné sur des cartes RSSI.

## 📁 Ressources

Toutes les ressources nécessaires (jeux de données, notebooks, etc.) sont disponibles ici :  
🔗 [Dossier Google Drive du projet](https://drive.google.com/drive/folders/1-2S5dzlxJ4ifCGfyutujV0tdofx7L20r?usp=sharing)

## 🗺️ Qu’est-ce qu’une carte RSSI ?

Une carte RSSI ("Received Signal Strength Indication") est une grille 2D qui mesure l’intensité du signal radio reçu depuis un point d’accès sans fil.  
Elle permet :

- de diagnostiquer la couverture d’un réseau sans fil,
- mais aussi de **localiser** un objet, en croisant la force de plusieurs signaux.

Dans ce projet, nous avons 4 cartes RSSI (`RSSI_0.csv`, ..., `RSSI_3.csv`) correspondant à 4 bornes Wi-Fi, mesurant le signal sur une grille (x, y) à intervalles réguliers.

---

## 🎯 Objectif

Construire une **fonction de localisation**, c’est-à-dire un modèle qui prédit la position `(x, y)` d’un point dans l’espace **à partir des 4 mesures RSSI** reçues.

---

## 🧠 Méthodologie

### 1. **Analyse exploratoire**
- Affichage simultané des 4 cartes RSSI.
- Visualisation des zones avec données manquantes.

### 2. **Traitement des données manquantes**
- Plusieurs options explorées :  
  - Interpolation  
  - Moyenne locale  
  - Suppression  
- La méthode retenue est _______________ (à compléter selon ce que tu as choisi).

### 3. **Modélisation par réseau de neurones**
- Architecture : **réseau dense (fully connected)**
- Données d’entrée : `RSSI_0`, `RSSI_1`, `RSSI_2`, `RSSI_3`
- Données de sortie : coordonnées `(x, y)`
- Fonction de perte : **Mean Squared Error (MSE)**
- Métrique utilisée : **R² score**

### 4. **Entraînement du modèle**
- Séparation des données : **80 % apprentissage / 20 % test**
- Suivi de :
  - La perte (Loss) sur les deux ensembles
  - Le score R² au fil des epochs

---

## 📊 Résultats

- 🔁 **Historique Loss et R²** : visualisé pour training et test
- 📏 **Histogramme des distances** entre positions prédites et réelles
- 📈 R² final sur le jeu de test : `_____` (à compléter)
- 📉 Erreur moyenne de localisation : `_____` (à compléter)


