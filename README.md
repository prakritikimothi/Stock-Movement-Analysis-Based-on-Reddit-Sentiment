# 📉 **Stock Movement Analysis Based on Reddit Sentiment** 📈

![Reddit Sentiment Analysis](https://img.shields.io/badge/Reddit%20Sentiment%20Analysis-Python-blue)  
*Analyzing stock movements based on Reddit sentiment using the Reddit API (PRAW)*
---
## 📝 **Project Overview**

This project performs **stock movement analysis** by extracting **sentiment data** from Reddit posts using the **PRAW** (Python Reddit API Wrapper). By analyzing user-generated content on subreddits like `r/stocks` and `r/investing`, we can derive insights about market sentiment towards specific stocks, which could help predict stock price movements.
### **Key Features**:
- Fetch **Reddit posts** from subreddits like `r/stocks`, `r/investing`
- Perform **sentiment analysis** on post titles and content
- Store **Reddit API credentials** securely using a `.env` file (no hardcoding)
- Interactive **Python script** to fetch and analyze Reddit data
---
## 🚀 **Installation Guide**
### Step 1: **Clone the Repository**
Clone this repository to your local machine:
```bash
git clone https://github.com/yourusername/stock-movement-reddit-sentiment.git
```
---
### Step 2: **Set Up Virtual Environment** (Optional but Recommended)
It’s recommended to use a virtual environment to avoid conflicts with other projects:
```bash
python -m venv venv
source venv/bin/activate  # For Windows use: venv\Scripts\activate
```
---
### Step 3: **Set Up Environment Variables**

To keep your **Reddit API credentials** secure, we use the **`.env`** file to store them. This will ensure your credentials are never hardcoded into the script.

1. Create a `.env` file in the root of the project.
2. Add your **Reddit API credentials** to the `.env` file:
```bash
client_id='YOUR_REDDIT_CLIENT_ID'
client_secret='YOUR_REDDIT_CLIENT_SECRET'
user_agent='YOUR_REDDIT_USER_AGENT'
```
> ⚠️ **Important:** Never commit your `.env` file to version control! Add it to `.gitignore` to keep it safe.
### Step 4: **Add `.env` to `.gitignore`**
Ensure your `.env` file is excluded from version control by adding it to `.gitignore`:
```bash
echo ".env" >> .gitignore
```
---
## 🔥 **Running the Project**
After setting up the environment, you can now run the script to interact with the Reddit API.
### Script Usage:
```python
import praw
from dotenv import load_dotenv
import os
# Load environment variables from the .env file
load_dotenv()
# Retrieve the values from environment variables
client_id = os.getenv('client_id')
client_secret = os.getenv('client_secret')
user_agent = os.getenv('user_agent')
# Initialize Reddit API client using PRAW
reddit = praw.Reddit(
    client_id=client_id,         # Your unique client ID
    client_secret=client_secret, # Your unique client secret
    user_agent=user_agent       # Your user agent string
)
# Fetch the top 5 posts from the 'learnpython' subreddit
posts = reddit.subreddit('learnpython').hot(limit=5)
for post in posts:
    print(post.title)
```
---

## 🧑‍💻 **Contributing**

We welcome contributions from the open-source community! Feel free to fork the repo, make changes, and submit a pull request.
### **How to Contribute:**
1. Fork the repository.
2. Create a new branch for your changes.
3. Make your changes and commit them.
4. Push your changes to your forked repository.
5. Open a pull request to the main repository.
---
## 📂 **Project Structure**

```
STOCK SENTIMENT PREDICTION
|   .env
|   reddit_sentiment_model_large.pkl
|   reddit_stock_analysis_large.csv
|   stock sentiment predictiont.ipynb
\---.ipynb_checkpoints
        reddit_stock_analysis_large-checkpoint.csv
        stock sentiment predictiont-checkpoint.ipynb
```
---
## 🎨 **Colors and Emojis for Fun!**
- 🌍 **Environment**: `.env` file for credentials storage
- 🚀 **Easy Setup**: Follow the steps to run the project
- 🔑 **Secure API Keys**: No more hardcoding, keep your keys safe!
- 📈 **Data Science**: Perform sentiment analysis on Reddit posts!
---
## 💡 **License**
This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.
---
## 📚 **Resources & Links**
- [PRAW Documentation](https://praw.readthedocs.io/) - Python Reddit API Wrapper
- [Reddit API Documentation](https://www.reddit.com/dev/api/) - Official Reddit API Guide
- [dotenv Documentation](https://pypi.org/project/python-dotenv/) - Secure storage of environment variables
---
## 📬 **Get in Touch**
If you have any questions, feel free to open an issue or contact me directly. Let's talk about stocks and sentiment analysis! 😄
---
