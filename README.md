
# User Review Sentiment Analysis – Canva (ID)
This project is part of the final submission for the "Belajar Pengembangan Machine Learning" course. 

The primary objective is to classify user sentiments—positive, negative, or neutral—based on review texts by leveraging both Machine Learning and Deep Learning models. The project also aims to compare the performance of these models to identify the most effective approach for sentiment classification.


## Dataset
The dataset consists of user reviews for the Canva app, collected through web scraping using the google-play-scraper library. Each review is manually labeled with one of three sentiment categories: Positive, Negative, or Neutral.


## Languages and Libraries
- **Programming Language:** Python
- **Data Manipulation & Analysis**: Pandas & Numpy
- **Data Collection**: `google-play-scraper`
- **Text Preprocessing**: NLTK, Sastrawi
- **Feature Extraction**: TF-IDF, Bag of Words (BoW)
- **Visualization**: Matplotlib, Seaborn, Wordcloud
- **Modeling**: Logistic Regression, Random Forest, and LSTM


## Stages of Analysis
1. **Scraping Data** from Google Play Store
2. **Text Preprocessing** (cleansing, stopword removal, etc.)
3. **Feature Extraction** using TF-IDF and BoW
4. **Model Training** classification using:
   - Logistic Regression
   - Random Forest
   - LSTM (Long-Short Term Memory)
5. **Accuracy Evaluation and Comparison**


## Struktur Folder
dicoding_proyek_analisis_sentimen/

├── README.md

├── requirements.txt

├── Notebook_Pelatihan_Model.ipynb

├── Scraping.ipynb

└── ulasan_canva.csv


## Sentiment Analysis
### Sentiment Polarity on Data
![Sentiment Polarity on Data](/images/image.png)
> Based on the pie chart, the majority of reviews for the Canva application are positive (72.5%), indicating that most users had a good experience using the app. Additionally, there are negative sentiments (16.4%) and neutral sentiments (11.1%), suggesting that a small portion of users were dissatisfied, while others felt indifferent—neither unhappy nor particularly satisfied—with the service provided by the application.

![Distribution of Sentiment Polarity](/images/image-5.png)
>Based on the "Sentiment Class Distribution" visualization, the Positive sentiment dominates with 78,263 reviews, followed by the Negative sentiment with 17,741 reviews, and the Neutral sentiment with 11,996 reviews.

### Word Cloud of Reviews

#### All Reviews
![Word Cloud of All Review](/images/image-1.png)
>Based on the word cloud visualization for all reviews, positive sentiment clearly dominates, indicating that the majority of users feel satisfied and supported by the Canva application.

#### Negative Reviews
![Word Cloud of Negative Reviews](/images/image-2.png)
>Based on the word cloud visualization for negative reviews, words like "kesalahan" (error), "error", "lemot" (slow), "susah masuk" (hard to log in), and other technical issues are prominently featured as the main complaints. This suggests that many users experienced difficulties using Canva, likely due to technical problems, slow performance, or premium features. Expressions of disappointment are also evident in words such as "ribet" (complicated), "jelek" (bad), and "nyesel" (regret).

#### Positive Reviews
![Word Cloud of Positive Reviews](/images/image-3.png)
>Based on the word cloud visualization for positive reviews, words such as "membantu" (helpful), "bermanfaat" (useful), and "memudahkan" (makes things easier) are strongly represented, indicating the app's usefulness to users. As a form of appreciation, many users express praise using words like "bagus" (good), "keren" (cool), "mantap" (awesome), and "terima kasih" (thank you).

#### Neutral Reviews
![Word Cloud of Neutral Reviews](/images/image-4.png)
>Based on the word cloud visualization for neutral reviews, the word cloud shows that "canva" is the most dominant term, which may indicate that users frequently mention the brand explicitly. This reflects a high level of awareness and usage among users. Additionally, words like "keren" (cool) and "membantu" (helpful) are also present, suggesting that while users recognize the app's strengths, their feedback lacks strong emotional tones. Some users also include suggestions and expectations, indicating that neutral sentiment often includes constructive feedback aimed at improving the application's quality.

#### Most Frequent Words in Reviews
![Word Cloud of Neutral Reviews](/images/image-6.png)
>Based on the visualization that highlights the top 20 most commonly used words, the term "membantu" (helpful) appears most frequently, with approximately 12,000 occurrences. This suggests that a significant number of users perceive the application as highly beneficial in their daily activities. Other frequently appearing words include "bagus" (good), "aplikasi" (application), "banget" (very), and "mudah" (easy). These words collectively indicate a predominantly positive sentiment toward the app, reinforcing its reputation as an accessible and effective tool for users.

## Data Splitting and Feature Extraction
In this project, feature extraction was conducted using two common Natural Language Processing (NLP) techniques: **TF-IDF** (Term Frequency–Inverse Document Frequency) and **Bag of Words** (BoW). These methods transform textual data into numerical representations that machine learning models can understand. TF-IDF emphasizes important words in a document by considering their frequency in the document and rarity across all documents. In contrast, BoW creates a simple representation by counting the occurrence of each word, ignoring grammar and word order.

To evaluate the models effectively, the dataset was split into training and testing sets using different ratios, such as 80/20 and 70/30. The training set was used to teach the models to recognize patterns in the data, while the testing set was reserved for evaluating the models' generalization performance on unseen data. This approach helps ensure that the results are reliable and not just fitted to the training data.

## Modeling
After feature extraction, three models were trained for sentiment classification:
- **Logistic Regression**: A linear model suitable for text classification due to its efficiency and effectiveness with high-dimensional data like TF-IDF or BoW.
- **Random Forest**: An ensemble learning method that builds multiple decision trees and combines their outputs for robust classification, capable of capturing nonlinear relationships in the data.
- **Long Short-Term Memory (LSTM)**: A type of Recurrent Neural Network (RNN) ideal for sequential data such as text. LSTM models learn contextual patterns in word sequences, making them particularly effective for understanding sentiment from text.
Each model was evaluated using training and testing accuracy to compare their ability to generalize and predict sentiment accurately.

## Model Accuracy Comparison

| No | Model                            | Vectorizer | Train Accuracy | Test Accuracy |
|----|----------------------------------|------------|----------------|---------------|
| 1  | Long Short-Term Memory (80/20)   | -          | 0.988632       | 0.962357      |
| 2  | Logistic Regression (80/20)      | TF-IDF     | 0.947563       | 0.941672      |
| 3  | Random Forest (80/20)            | BoW        | 0.989517       | 0.925134      |
| 4  | Random Forest (70/30)            | TF-IDF     | 0.984266       | 0.922291      |

Among all models tested, the LSTM model with an 80/20 train-test split achieved the highest performance, reaching a testing accuracy of 96.23%. This highlights the effectiveness of deep learning methods in understanding and classifying sentiment in natural language text.
