# 🎮 Prédiction de Recommandation de Jeux Steam - Machine Learning & Deep Learning

Ce projet a pour objectif de **prédire si un utilisateur recommande un jeu vidéo** sur Steam en se basant sur le **texte de son avis**. Deux approches sont mises en œuvre : une approche **classique avec du Machine Learning (TF-IDF + Régression Logistique)** et une approche **deep learning avec un réseau de neurones LSTM**.

---

## 🗂️ Jeux de données

- `train.csv` : contient 10 000 avis d’utilisateurs avec le titre du jeu, l’année et l’indication de recommandation.
- `game_overview.csv` : contient 1 000 jeux avec leurs tags et résumés.

Chaque ligne de `train.csv` contient :
- `user_review` : le texte de l’avis
- `user_suggestion` : 1 si l’utilisateur recommande le jeu, 0 sinon

---

## 📊 Analyse exploratoire (EDA)

- Distribution de la longueur des mots et des phrases
- Fréquence des mots selon la classe (recommande ou non)
- Vérification du déséquilibre des classes
- Analyse potentielle des métadonnées du jeu

---

## 🧹 Prétraitement & Nettoyage

- Passage en minuscules, suppression de la ponctuation et des chiffres
- Suppression des stop words
- Lemmatisation
- Tokenisation
- Padding / Troncature des séquences

---

## 🧠 Modèles

### 1. **Régression Logistique (baseline)**
- Texte vectorisé avec **TF-IDF**
- Modèle simple pour comparer les performances

### 2. **Réseau LSTM**
- Texte transformé en séquences numériques
- Utilisation d’une couche `Embedding`
- Entraînement avec la fonction de perte `BinaryCrossentropy`

---

## 💾 Sauvegarde et Prédiction

Le modèle LSTM est sauvegardé avec `model.save()` puis rechargé pour réaliser des prédictions sur de nouvelles données.

---

## 📦 Dépendances

- Python 3.8+
- TensorFlow 2.x
- scikit-learn
- pandas
- matplotlib
- nltk
- seaborn

Installation :

```bash
pip install -r requirements.txt
# steam-review-classifier
