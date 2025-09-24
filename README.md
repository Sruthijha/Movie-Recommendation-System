# 🎬 Movie Recommendation System

A **content-based movie recommender system** built using Python, Pandas, scikit-learn, and Streamlit.  
The system recommends movies similar to a selected movie based on their descriptions, genres, keywords, cast, and crew.  
Movie posters are fetched dynamically using the **TMDB API**.  

---

## Features
- Data preprocessing: Clean and structure the TMDB 5000 dataset (movies + credits).  
- Tag generation: Combine overview, genres, keywords, cast, and crew into text tags.  
- Stemming: Reduce words to their root form for better similarity matching.  
- Vectorization: Convert text into numerical vectors using CountVectorizer.  
- Cosine Similarity: Compute similarity scores between movies.  
- Interactive app: Built with Streamlit for real-time recommendations.  
- Poster fetching: Uses TMDB API to display movie posters.  

---

## Tech Stack
- **Language**: Python 3  
- **Libraries**: pandas, numpy, scikit-learn, nltk, streamlit, requests  
- **Dataset**: [TMDB 5000 Movie Dataset](https://www.kaggle.com/datasets/tmdb/tmdb-movie-metadata)  
- **API**: [TMDB API](https://www.themoviedb.org/documentation/api)  

---

## Workflow
1. **Load & Merge Data**: Combine `tmdb_5000_movies.csv` and `tmdb_5000_credits.csv`.  
2. **Select Features**: Keep `movie_id`, `title`, `overview`, `genres`, `keywords`, `cast`, and `crew`.  
3. **Preprocess Data**:  
   - Convert JSON-like strings to Python lists.  
   - Extract top 3 cast members and director.  
   - Clean text and remove spaces in multi-word entities.  
   - Apply stemming with PorterStemmer.  
4. **Generate Tags**: Concatenate processed columns into a single `tags` column.  
5. **Vectorize**: Convert tags into feature vectors with CountVectorizer (`max_features=5000`, `stop_words='english'`).  
6. **Compute Similarity**: Use cosine similarity on vectors.  
7. **Save Artifacts**: Store `movies.pkl` and `similarity.pkl` for reuse.  
8. **Build App**: Streamlit app for interactive recommendations.  

---
