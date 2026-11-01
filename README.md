# Movie Recommendation System

A **Machine Learning-based Movie Recommendation System** that uses **Content-Based Filtering** to suggest movies similar to a movie selected by the user. The application is built with Python and Streamlit, and uses the TMDB API to retrieve movie poster images.

<p align="left">
  <a href=https://movie-recommender-hftw7dlefiwwxy3tet9yye.streamlit.app/>Live Demo</a> ·
  <a href="https://github.com/rohanprajapat25/movie-recommender">GitHub Repository</a>
</p>

## Overview

This project demonstrates how a content-based recommendation approach can be used to suggest movies based on similarities stored in a precomputed similarity matrix. Users select a movie from the Streamlit interface and receive a list of recommended movies, with poster images retrieved from TMDB.

## Features

- Select a movie from the available movie list.
- Generate movie recommendations using a precomputed similarity matrix.
- Display recommended movie titles and poster images.
- Retrieve poster information through the TMDB API.
- Interactive web interface built with Streamlit.

## Tech Stack

- **Python** — application logic
- **Pandas** — movie data handling
- **NumPy** — numerical operations
- **Scikit-learn** — machine-learning tools used in the project environment
- **Streamlit** — web application interface
- **Requests** — TMDB API requests
- **TMDB API** — movie poster information
- **Git and Git LFS** — source control and large-file storage

## Project Structure

```text
movie-recommender/
│
├── .streamlit/
│   └── secrets.toml       # Local API secret (not committed to Git)
│
├── app.py                 # Streamlit application
├── movies.pkl             # Serialized movie data
├── similarity.pkl         # Precomputed movie similarity matrix
├── requirements.txt       # Python dependencies
├── .gitignore             # Files excluded from Git
├── .gitattributes         # Git LFS tracking configuration
└── README.md
```

> `movies.pkl` and `similarity.pkl` are required by the application. The large `similarity.pkl` file is tracked with Git LFS.

## Run Locally

### 1. Clone the repository

Install [Git LFS](https://git-lfs.com/) before cloning so the large similarity file is downloaded correctly.

```bash
git lfs install
git clone https://github.com/rohanprajapat25/movie-recommender.git
cd movie-recommender
```

### 2. Create and activate a virtual environment

**Windows PowerShell:**

```powershell
python -m venv .venv
.\.venv\Scripts\Activate.ps1
```

If PowerShell blocks activation, you can run the app using the virtual environment's Python executable directly, as shown below, without activating it.

### 3. Install dependencies

```bash
python -m pip install -r requirements.txt
```

### 4. Configure the TMDB API key

Create a folder named `.streamlit` in the project root, then create a file named `secrets.toml` inside it:

```text
.streamlit/secrets.toml
```

Add your own TMDB API key:

```toml
TMDB_API_KEY = "YOUR_TMDB_API_KEY"
```

The application reads the key using `st.secrets["TMDB_API_KEY"]`. **Do not commit `secrets.toml` or expose your API key publicly.** The file is excluded through `.gitignore`.

### 5. Run the application

```bash
streamlit run app.py
```

Or, on Windows, run it directly through the virtual environment:

```powershell
.\.venv\Scripts\python.exe -m streamlit run app.py
```

Streamlit will provide a local address, usually `http://localhost:8501`.

## Deployment

The application is deployed on **Streamlit Community Cloud**:

[Open the live Movie Recommendation System]<https://movie-recommender-hftw7dlefiwwwxy3tet9yye.streamlit.app/>

For cloud deployment, add the following to the app's **Secrets** settings in Streamlit Community Cloud (use your own key):

```toml
TMDB_API_KEY = "YOUR_TMDB_API_KEY"
```

Do not upload your local `.streamlit/secrets.toml` file to GitHub.

## How to Use

1. Open the [live application]<https://movie-recommender-hftw7dlefiwwwxy3tet9yye.streamlit.app/>
2. Select or type a movie title in the dropdown.
3. Click **Recommend**.
4. Browse the recommended movie titles and poster images.

## Author

**[@rohanprajapat25](https://github.com/rohanprajapat25)**

---

If you find this project useful, consider giving the repository a star.
