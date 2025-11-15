# Analyse de Musique - Projet SKKU Language Technology

Projet d'analyse linguistique des paroles de chansons populaires en France, Espagne et Corée.

## 🎯 Objectif

Ce projet vise à analyser et comparer les paroles des top 20 chansons de trois pays (France, Espagne, Corée) afin de :
- analyser la fréquence des mots par pays
- identifier les mots communs entre les langues
- effectuer une analyse de sentiment
- calculer la similarité sémantique entre chansons
- recommander des chansons similaires basées sur le contenu et le sentiment

## 📊 Fonctionnalités

### 1. Prétraitement des données
- nettoyage des paroles (suppression des balises, normalisation)
- tokenisation
- étiquetage morphosyntaxique (pos tagging)
- lemmatisation
- suppression des mots vides (stop words)
- limitation des doublons

### 2. Analyse de fréquence
- calcul des 20 mots les plus fréquents par pays
- génération de nuages de mots (word clouds)
- identification du vocabulaire commun entre les trois langues

### 3. Analyse de sentiment
- analyse de sentiment par section (intro, verse, chorus, etc.)
- classification positive/neutre/négative
- calcul du sentiment global par pays

### 4. Similarité sémantique
- comparaison de similarité avec spacy (cosine similarity)
- comparaison de similarité avec sbert (sentence transformers)
- identification des chansons les plus similaires entre pays

### 5. Système de recommandation
- recommandation de chansons similaires basée sur la similarité sémantique
- filtrage par sentiment (recommandations avec même sentiment)
- top 3 recommandations par chanson

## 📈 Résultats principaux

### Analyse de sentiment
- **corée** : positif (0.55) - les chansons coréennes montrent un sentiment globalement positif
- **france** : neutre (-0.03) - sentiment équilibré
- **espagne** : neutre (-0.19) - légèrement négatif mais proche du neutre

### Vocabulaire
- **mots les plus fréquents** : baby, time, night, love, heart, etc.
- **vocabulaire commun** : 100+ mots partagés entre les trois langues

### Système de recommandation musicale
- système fonctionnel qui recommande les 3 chansons similaires d'une chanson donnée basé sur la similarité sémantique et le sentiment

## 📝 Notes importantes

- **langue d'analyse** : les paroles sont analysées en anglais (traductions des paroles originales)
- **modèle de sentiment** : `distilbert-base-uncased-finetuned-sst-2-english` (optimisé pour l'anglais)
- **modèles de similarité** :
  - spaCy : `en_core_web_lg` (modèle large pour l'anglais)
  - sBERT : `all-MiniLM-L6-v2` (modèle compact et rapide)
- **recommandations** : basées sur la similarité sémantique (sBERT) et le filtrage par sentiment
- **données** : les fichiers `TOP20_*.txt` contiennent les paroles des top 20 chansons de chaque pays

## 📦 Dépendances principales
- `nltk` - traitement du langage naturel
- `spacy` - similarité sémantique avec modèles pré-entraînés
- `transformers` - analyse de sentiment avec distilbert
- `sentence-transformers` - embeddings sémantiques avec sbert
- `wordcloud` - visualisation des mots les plus fréquents
- `matplotlib` - visualisation des données
- `pandas` - manipulation des données

## 🚀 Installation

### Prérequis
- python 3.7+
- jupyter notebook ou jupyter lab

### Installation des dépendances

```bash
# installer les packages python
pip install nltk spacy transformers sentence-transformers wordcloud matplotlib pandas

# télécharger les modèles spacy
python -m spacy download en_core_web_lg

```

## 💻 Utilisation

1. **ouvrir le notebook jupyter** :
   ```bash
   jupyter notebook MusicAnalysis.ipynb
   ```
   ou
   ```bash
   jupyter lab MusicAnalysis.ipynb
   ```

2. **exécuter les cellules dans l'ordre** :
   - le notebook est organisé en sections (I à VII)
   - exécuter toutes les cellules pour obtenir les résultats complets
   - certaines cellules peuvent prendre du temps (téléchargement des modèles, calculs de similarité)

3. **utiliser le système de recommandation** :
   - exécuter la section VII (Songs Recommendations)
   - le système recommande des chansons similaires basées sur la similarité sémantique et le sentiment

## 📁 Structure du projet

```
.
├── MusicAnalysis.ipynb
├── TOP20_fr.txt          # paroles des top 20 chansons françaises
├── TOP20_es.txt          # paroles des top 20 chansons espagnoles
├── TOP20_kr.txt          # paroles des top 20 chansons coréennes
├── stop_words_english.txt # mots vides supplémentaires
├── Final_report.pdf   # rapport final
└── README.md
```

## 👥 Auteur

Alexis DHERMY, Pablo Picó Salort