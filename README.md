# Music Analysis - SKKU Language Technology Project

Linguistic analysis project of popular song lyrics from France, Spain, and Korea using NLP (Natural Language Processing).

## 🎯 Objective

This project aims to analyze and compare the lyrics of Spotify's Top 20 songs (December 2024) from three countries (France, Spain, Korea) in order to:
- analyze word frequency by country
- identify common words across languages
- perform sentiment analysis
- calculate semantic similarity between songs
- recommend similar songs based on content and sentiment

## 📊 Features

### 1. Data Preprocessing
- lyrics cleaning (removal of tags, normalization)
- tokenization
- morphosyntactic tagging (POS tagging)
- lemmatization
- stop words removal
- duplicate limitation

### 2. Frequency Analysis
- calculation of the 20 most frequent words per country
- word cloud generation
- identification of common vocabulary across the three languages

### 3. Sentiment Analysis
- sentiment analysis by section (intro, verse, chorus, etc.)
- positive/neutral/negative classification
- global sentiment calculation per country

### 4. Semantic Similarity
- similarity comparison using spaCy (cosine similarity)
- similarity comparison using sBERT (sentence transformers)
- identification of the most similar songs between countries

### 5. Recommendation System
- recommendation of similar songs based on semantic similarity
- sentiment filtering (recommendations with same sentiment)
- top 3 recommendations per song

## 📈 Main Results

### Sentiment Analysis
- **Korea**: positive (0.55) - Korean songs show an overall positive sentiment
- **France**: neutral (-0.03) - balanced sentiment
- **Spain**: neutral (-0.19) - slightly negative but close to neutral

### Vocabulary
- **most frequent words**: baby, time, night, love, heart, etc.
- **common vocabulary**: 100+ words shared across the three languages

### Music Recommendation System
- functional system that recommends the 3 most similar songs for a given song based on semantic similarity and sentiment

## 📝 Important Notes

- **analysis language**: lyrics are analyzed in English (translations of original lyrics)
- **sentiment model**: `distilbert-base-uncased-finetuned-sst-2-english` (optimized for English)
- **similarity models**:
  - spaCy: `en_core_web_lg` (large model for English)
  - sBERT: `all-MiniLM-L6-v2` (compact and fast model)
- **recommendations**: based on semantic similarity (sBERT) and sentiment filtering
- **data**: the `TOP20_*.txt` files contain the lyrics of the top 20 songs from each country

## 📦 Main Dependencies
- `nltk` - natural language processing
- `spacy` - semantic similarity with pre-trained models
- `transformers` - sentiment analysis with distilbert
- `sentence-transformers` - semantic embeddings with sbert
- `wordcloud` - visualization of most frequent words
- `matplotlib` - data visualization
- `pandas` - data manipulation

## 🚀 Installation

### Prerequisites
- python 3.7+
- jupyter notebook or jupyter lab

### Dependency Installation

```bash
# install python packages
pip install nltk spacy transformers sentence-transformers wordcloud matplotlib pandas

# download spacy models
python -m spacy download en_core_web_lg

```

## 💻 Usage

1. **open jupyter notebook**:
   ```bash
   jupyter notebook MusicAnalysis.ipynb
   ```
   or
   ```bash
   jupyter lab MusicAnalysis.ipynb
   ```

2. **execute cells in order**:
   - the notebook is organized in sections (I to VII)
   - execute all cells to get complete results
   - some cells may take time (model downloads, similarity calculations)

3. **use the recommendation system**:
   - execute section VII (Songs Recommendations)
   - the system recommends similar songs based on semantic similarity and sentiment

## 📁 Project Structure

```
.
├── MusicAnalysis.ipynb   # main notebook
├── TOP20_fr.txt          # lyrics of top 20 French songs
├── TOP20_es.txt          # lyrics of top 20 Spanish songs
├── TOP20_kr.txt          # lyrics of top 20 Korean songs
├── stop_words_english.txt # additional stop words
├── Final_report.pdf      # report of the project
└── README.md
```

## 👥 Authors

Alexis DHERMY, Pablo Picó Salort
