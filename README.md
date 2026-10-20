# CineGraph-AI — GNN Movie Recommendation Engine

[![Python](https://img.shields.io/badge/Python-3.9+-3776AB.svg?logo=python&logoColor=white)](#)
[![Streamlit](https://img.shields.io/badge/Streamlit-1.x-FF4B4B.svg?logo=streamlit&logoColor=white)](#)
[![GNN Embeddings](https://img.shields.io/badge/Model-GNN%20Graph%20Embeddings-0052CC.svg)](#)
[![Scikit-Learn](https://img.shields.io/badge/scikit--learn-Vector%20Search-F7931E.svg?logo=scikit-learn&logoColor=white)](#)
[![License](https://img.shields.io/badge/License-MIT-green.svg)](#)

A movie recommendation web application powered by **Graph Neural Network (GNN)** node embeddings and vector similarity search. CineGraph-AI maps multi-relational film connectivity (genres, themes, latent graph structures) to generate contextual recommendations tailored to user watch history.

The application serves pre-trained graph embeddings (`movie_gnn_model.pkl`) through an interactive **Streamlit** dashboard for real-time persona simulation and catalog exploration.

---

## Overview

Traditional matrix factorization and collaborative filtering often overlook non-linear topological relationships between movies. CineGraph-AI leverages graph representation learning to project films into a continuous embedding space:

- **Graph Topology Mapping**: Captures deep latent connections between films that go beyond basic tag matching.
- **Centroid-Based User Profiling**: Computes a dynamic user preference vector by averaging embeddings of selected movies (`np.mean`), adapting recommendations as titles are added or removed.
- **Fast Similarity Search**: Calculates cosine similarity against the full catalog vector space in sub-millisecond latency.
- **Deduplication Filter**: Automatically excludes previously watched movies from recommended outputs.

---

## Key Features

- **Pre-trained GNN Embeddings (`movie_gnn_model.pkl`)**: High-dimensional graph representations capturing structural film relationships.
- **Dynamic Watch History Matching**: Real-time Top-K movie ranking based on vector cosine proximity.
- **Interactive Streamlit Interface**: Clean dashboard with sidebar controls for managing watch history and viewing similarity scores.
- **Genre & Metric Filtering**: Filter recommendations by genre, sorted by global rating and popularity indicators.
- **In-Memory Model Caching**: Uses Streamlit's `@st.cache_resource` for instant load times and responsive recalculation.

---

## Installation & Setup

### Prerequisites

- Python 3.9+
- pip & virtualenv

### Quickstart

1. **Clone the repository**:
   ```bash
   git clone https://github.com/MasterPandaa/CineGraph-AI.git
   cd CineGraph-AI
   ```

2. **Create and activate a virtual environment**:
   ```bash
   # Windows
   python -m venv venv
   .\venv\Scripts\activate

   # Linux / macOS
   python3 -m venv venv
   source venv/bin/activate
   ```

3. **Install dependencies**:
   ```bash
   pip install -r requirements.txt
   ```

4. **Launch the Streamlit app**:
   ```bash
   streamlit run app.py
   ```
   Open `http://localhost:8501` in your browser.

---

## Project Structure

```text
CineGraph-AI/
├── app.py                  # Streamlit application interface & recommendation logic
├── requirements.txt        # Python package dependencies
├── movie_gnn_model.pkl     # Pre-trained GNN graph embeddings and metadata
├── Procfile                # Deployment configuration for cloud hosting
└── README.md               # Project documentation
```

---

## License

This project is licensed under the [MIT License](LICENSE).
