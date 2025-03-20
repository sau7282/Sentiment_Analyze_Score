# Sentiment Analysis API

## 📌 Overview
The **Sentiment Analysis API** analyzes Reddit posts and comments to determine their sentiment as **positive, negative, or neutral**. It helps understand public opinion trends and provides insights into online discussions.

## 🚀 Features
- User-friendly **UI** to input a topic name and number of posts to analyze.
- Fetch Reddit posts and comments using **Redis**.
- Analyze the sentiment of Reddit posts and comments.
- Process large amounts of text data efficiently.
- Provide insights into trending sentiment.
- User sentiment dashboard for historical analysis.

## 🛠 Technologies Used
- **Python**
- **Flask** (for API development)
- **VADER (Valence Aware Dictionary and sEntiment Reasoner)** (for sentiment analysis)
- **NLTK** (for text preprocessing)
- **Redis** (for caching and storing fetched Reddit data)
- **PostgreSQL** (using Render database for storing sentiment results)
- **Render** (for deployment)
- **HTML, CSS** (for UI development)

## 📥 Installation

### Prerequisites:
- Python 3.8+
- pip
- Virtual environment (optional but recommended)
- Redis server (local or cloud-based)


# Create a virtual environment (optional but recommended)
python -m venv venv
source venv/bin/activate  # On Windows use `venv\Scripts\activate`

# Install dependencies
pip install -r requirements.txt
```

## ▶ Usage

### Running the API
```sh
python app.py
```
The API will be available at `http://127.0.0.1:5000`.

### API Endpoints
| Method | Endpoint | Description |
|--------|---------|-------------|
| `POST` | `/analyze` | Analyze sentiment of a given text using VADER |
| `GET` | `/fetch_reddit_data` | Fetch and cache Reddit posts and comments using Redis |
| `GET` | `/get_sentiment_scores?topic=TOPIC_NAME&num_posts=NUMBER` | Fetch and analyze sentiment for a specified topic and number of posts |
| `GET` | `/health` | Check API health status |

#### Example Request
```sh
curl -X GET "http://127.0.0.1:5000/get_sentiment_scores?topic=AI&num_posts=10"
```

#### Example Response
```json
{
  "topic": "AI",
  "total_posts": 10,
  "positive": 5,
  "negative": 3,
  "neutral": 2
}
```

## 🖥️ User Interface
The application includes a **web UI** where users can enter a **topic name** and specify the **number of Reddit posts** to analyze. The system then fetches the posts, analyzes sentiment, and displays a summary score.

## 📊 Sentiment Dashboard
A simple **dashboard** is integrated to visualize sentiment trends over time. Features include:
- Graphs showing sentiment distribution.
- User-specific insights.

## 🚀 Deployment on Render
This API is deployed on **Render** and uses **Render PostgreSQL Database**. To deploy:
1. Push your code to a GitHub repository.
2. Create a new **Web Service** on Render.
3. Connect your GitHub repository.
4. Set up a **Render PostgreSQL Database** and update your database configuration in the project.
5. Ensure Redis is set up and accessible for fetching and caching Reddit data.
6. Set the **Build Command** to:
   ```sh
   pip install -r requirements.txt
   ```
7. Set the **Start Command** to:
   ```sh
   python app.py
   ```
8. Deploy and get your API URL.

## 🤝 Contributing
Contributions are welcome! To contribute:
1. Fork the repository.
2. Create a new branch: `git checkout -b feature-branch`.
3. Commit your changes: `git commit -m "Added new feature"`.
4. Push to the branch: `git push origin feature-branch`.
5. Submit a pull request.

